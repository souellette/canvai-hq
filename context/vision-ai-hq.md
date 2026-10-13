# Canvai AI HQ — vision et principes (donnés par Seb le 12 oct. 2026)

Document de référence. Rien n'est à implémenter à partir de lui : on conçoit UN département à la fois avec Seb.

## Vision
Un système d'exploitation IA pour Canvai : une entreprise virtuelle de départements et d'employés IA qui surveillent, analysent, collaborent, créent des tâches, exécutent et rapportent. « 24/7 » = infrastructure toujours disponible, agents réveillés par : un horaire, un événement, une nouvelle information, une anomalie, une tâche d'un autre agent, une mission de DOM, ou une demande de Seb. Pas de modèle qui « pense » en continu.

## Hiérarchie
Seb (CEO humain) → DOM (commandant IA, au-dessus des départements) → directeurs de département → agents spécialisés → outils / workflows / API.
DOM = chef d'état-major : comprend la demande, découpe en missions, choisit les départements, délègue, suit, résout les dépendances, consolide, escalade, résume. Il ne fait pas tout lui-même.

## Départements prévus (NON finalisés, pas de structure présumée)
01 Exécutif et stratégie · 02 Croissance et marketing · 03 Créatif et contenu · 04 E-commerce et CRO · 05 Opérations des concours · 06 Produit et marchandisage · 07 Sourcing et chaîne d'approvisionnement · 08 Expérience client · 09 Finance et intelligence d'affaires · 10 Opérations IA et technologie.

## Méthode (un département à la fois)
Pour chacun, définir : 1 but · 2 responsabilités · 3 agents réellement nécessaires · 4 rôle de chaque agent · 5 données d'entrée · 6 outils · 7 déclencheurs · 8 fréquence (temps réel / horaire / quotidien / hebdo / sur demande) · 9 livrables · 10 niveau d'automatisation · 11 approbations · 12 liens avec les autres départements · 13 mémoire · 14 indicateurs · 15 représentation dans l'interface. Ensuite seulement : figer l'architecture, documenter, implémenter.
Questions de départ : qu'est-ce que Seb a vraiment besoin de ce département ? quelles décisions aide-t-il à prendre ? quel travail répétitif élimine-t-il ? qu'est-ce qui reste humain ? quelles données ? quels autres départements en dépendent ? Proposer le MINIMUM utile d'agents ; un agent capable plutôt que trois proches.

## Technologie (peut évoluer si mieux)
Claude = raisonnement · n8n = workflows, déclencheurs · Supabase = base persistante, mémoire, source de vérité · Canvai AI HQ = interface · API externes = outils · DOM = orchestration. Ne pas ajouter de complexité inutile. L'interface ne doit jamais inventer l'état : si elle montre « Roman travaille », une vraie tâche existe.
(État réel au 12 oct. 2026 : la base est celle de la page Centre de commande, les agents sont des routines nuage horaires. Le choix Supabase/n8n reste à trancher.)
Tables envisagées : departments, agents, tasks, events, results, approvals, memory ; plus tard experiments, campaigns, business_metrics, agent_messages, integrations, products, suppliers, inventory, customers, notifications.

## Boucle d'un agent
Déclencheur → reçoit la tâche → charge contexte et mémoire → utilise les outils → analyse → produit un résultat → le stocke → crée des tâches de suivi → demande une approbation si nécessaire → met à jour son statut → retour au repos.

## Collaboration
Pas de silos : un agent crée des tâches structurées pour un autre (ex. Croissance détecte la fatigue créative → tâche au Créatif → concepts → Croissance les teste). Chaque département reste spécialisé.

## Piloté par les événements
Quatre types : planifié (Meta chaque heure), événement (nouvelle commande Shopify), anomalie (conversion −30 %), agent-à-agent. Certains processus = simple automatisation déterministe (déclencheur → automatisation → base) sans IA. Claude seulement quand le raisonnement vaut la peine.

## Contrôle humain — échelle de permissions
1 Lire · 2 Analyser · 3 Recommander · 4 Rédiger · 5 Exécuter avec approbation · 6 Exécuter seul. Approbation obligatoire au début : hausse de budget pub, publication de campagne, envoi massif de courriels, changement de prix, commande d'inventaire, paiement de fournisseur, remboursement important, changement important du site.

## Mémoire organisationnelle
Retenir : ce qu'on a essayé, pourquoi, ce qui s'est passé, ce qu'on a appris, quoi faire autrement. Exemple : « 10X Entries — 48 dernières heures » : revenus +37 %, conversion +22 %, marge −8 % → bonne stratégie pour le dernier push. Les agents retrouvent ces leçons au lieu de les redécouvrir.

## Performance des agents
Tâches faites, taux de réussite, temps moyen, coût par tâche, corrections humaines, recommandations acceptées, erreurs, valeur générée, fiabilité.

## Interface
Départements visibles, agents identifiables. États : IDLE, WORKING, THINKING, RESEARCHING, MEETING, WAITING, NEEDS_APPROVAL, ERROR, OFFLINE (reflet de l'état réel). Clic sur un agent : nom, rôle, département, statut, tâche, progression, activité, résultats, outils, permissions, mémoire, performance, chat.

## Fiche d'un département approuvé
But · agents · responsabilités · outils · sources de données · déclencheurs · workflows · horaires · permissions · règles d'approbation · mémoire · indicateurs · relations · comportement dans l'interface.

## État final visé
Seb ouvre AI HQ et voit : ce que fait l'entreprise, ce que chaque département fait, les problèmes, les occasions, les tâches faites la nuit, les décisions en attente, la performance, et ce que DOM recommande. « DOM, qu'est-ce qui demande mon attention ? » → réponse concise.
