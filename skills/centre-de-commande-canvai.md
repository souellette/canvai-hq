# Centre de commande Canvai : comment un agent y écrit

La page où Seb voit le travail des agents de Canvai, par département.

- **Page :** https://claude.ai/artifact/HmF6uPLwvnfscK78orNXTs
- **Source :** `canvai/centre-de-commande.html` (capacité `db`)
- **Rapport derrière ce choix :** `canvai/reports/Command center agents Canvai.md`
- **Outil :** `ArtifactData` (ToolSearch « select:ArtifactData »), toujours avec l'`url` de la page.

## Les quatre collections

**`agents`** — un document par agent (l'identifiant ne change pas : `vigie-meta`, `pouls-ventes`, `tri-service`, `bilan-finances`, `textes-pubs`, `calendrier-concours`, `resume-matin`, `soumissions-fournisseurs`).
Champs : `name`, `dept` (`executif`, `marketing`, `creatif`, `ecommerce`, `concours`, `sourcing`, `service`, `finances` ; les anciens `contenu` et `operations` sont lus comme `creatif` et `concours`), `description`, `schedule`, `mode`, `model`, `status` (`actif`, `a_venir`, `pause`), `lastResult` (`ok`, `alerte`, `erreur` ou `null`), `nextRun` (texte libre), `lastRunAt` (ISO).

**`journal`** — une entrée par exécution ou par événement.
Champs : `at` (ISO), `dept`, `agentId` (ou `""`), `by` (ex. « Claude (session) » si ce n'est pas un agent), `level` (`ok`, `alerte`, `erreur`), `kind` (`rapport`, `alerte`, `action`, `decision`), `title` (une phrase), `detail` (2-3 lignes max), `link` (URL https ou `""`).

**`approbations`** — ce qui attend l'OK de Seb.
Champs : `createdAt` (ISO), `dept`, `agentId`, `title`, `detail`, `impact` (ex. « +50 $/jour sur l'ensemble Canada français »), `status` (`en_attente`, `approuve`, `refuse`), `decidedAt`.

**`metriques`** — les chiffres de l'écran « Bureau ». Deux documents, écrits par `set` :
- `ventes` : `periodLabel`, `revenue`, `adSpend`, `orders`, `aov`, `newCustomers` (nombres), `deltas` (optionnel, en %, mêmes clés), `updatedAt` (ISO), `source`. Le MER est calculé par la page (`revenue / adSpend`).
- `concours` : `name`, `revenue`, `entries`, `goal`, `endsAt` (ISO).
Écrit par le Pouls des ventes (`ventes`) et le Calendrier des concours (`concours`). Jamais un chiffre deviné : une valeur inconnue reste `null`.

## À chaque exécution d'un agent

1. Faire le travail, en lecture seulement.
2. Écrire UNE entrée dans `journal` (`set`, nouvel identifiant du type `AAAA-MM-JJ-HHMM-<agent>`), avec `level: "alerte"` si quelque chose demande l'attention de Seb, `"erreur"` si le travail n'a pas pu se faire. Un statut vert de la routine ne prouve rien : c'est l'entrée du journal qui compte.
3. Mettre à jour son document dans `agents` (`update` avec le `version` lu) : `lastRunAt`, `lastResult`, `nextRun`.
4. S'il propose une action (budget, courriel, écriture dans un outil), créer un document dans `approbations` avec `status: "en_attente"`. **Ne jamais exécuter l'action soi-même.**

## Quand Seb approuve

La page marque la proposition `approuve` et ajoute une ligne au journal. L'action se fait ensuite dans une session que Seb lance, jamais dans la routine. Après l'avoir faite, écrire une entrée `kind: "action"` dans le journal.
