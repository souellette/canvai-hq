# Département 03 — Créatif et contenu (approuvé par Seb le 12 oct. 2026)

## But
Que Canvai ait toujours des pubs fraîches et prêtes, sans que Seb les fabrique à la main dans Photoshop ou Illustrator. Le volume de créatifs est l'une des deux contraintes de croissance.

## Responsabilités
- Livrer des pubs FINIES (angle, titre, offre, logo), jamais un fond d'image.
- Rédiger les textes FR et EN (3 variantes par langue).
- Produire les statics, et les concepts vidéo et UGC (scripts, briefs).
- Préparer le lot de départ d'un nouveau concours (nouvelle voiture) et remplacer les pubs fatiguées.

## Agents (2 seulement)
| Agent | Id | Rôle |
|---|---|---|
| Sean | `textes-pubs` | Textes : 3 variantes par langue, courtes, sans FOMO |
| Neela | `neela` | Visuels : statics finis, concepts vidéo et UGC |

Retirés pour l'instant : Suki (directrice : DOM fait le rôle), Jesse (analyse des créatifs gagnants : Roman le fait côté Meta), Monica (réseaux organiques : pas demandé). Leurs fiches restent dans la base, marquées « retiré ».

## Volume visé
Environ 10 nouvelles pubs. Seb n'a donné qu'un seul chiffre pour « au début d'un concours » ET « par semaine » : à préciser. (Référence : CVA10 avait 15 statics ; `canvai/CLAUDE.md` marketing note 12 à 15 pièces par semaine à ce stade, 25 à 40 en cible.)

## Outils et données
- Images : l'API OpenAI par le script `canvai/marketing/outils/openai_image.py` (clé dans `~/.canvai/openai_key`, hors Dropbox ; fonctionne seulement sur le Mac de Seb, pas dans les routines nuage ; sorties dans `canvai/marketing/images-generees/`). Option `--ref` pour partir de vraies photos de la voiture. Test du 12 oct. : une image qualité basse, OK mais voiture générique sans référence.
- Higgsfield (connecté) pour vidéo et images ; modèles offerts non vérifiés.
- Pour ajouter titre, offre et logo : composition par script (les accents ont posé problème avant : composer le texte soi-même). Méthode exacte à fixer à la construction.
- Données : créatifs existants (Dropbox, dossiers Ads, `cva09-pubs-gagnantes`), tableau des pubs, rapports de Roman.

## Déclencheurs et fréquence
Pas d'horaire : sur demande, jamais en boucle.
- Tâche de Roman : fatigue créative, avec le constat (quelle pub, quelle fréquence).
- Calendrier du concours : un nouveau concours déclenche le lot de départ.
- Demande de Seb ou de DOM.

## Niveau d'automatisation et approbations
- Autonome : analyser les pubs existantes avant de créer.
- Brouillon, Seb approuve : textes, visuels, scripts.
- Approbation de Seb TOUJOURS : publication d'une pub.
- Génération d'images ou vidéos (coûte des crédits) : annoncer le nombre d'images AVANT, une exécution du script = 8 images maximum. Le solde prépayé du compte OpenAI est le plafond, recharge automatique désactivée.

## Règles acquises
- Pubs finies, pas des fonds d'images.
- Regarder d'abord les créatifs existants de la marque : plein jour, orange vif, titres condensés, logo en bas. Pas de style sombre ni dramatique.
- Textes courts, une info par ligne, une ligne vide entre chaque, un emoji en tête, trois variantes, la première « 🏁 Dernière chance ». Pas de FOMO ni de hype. Seb les voit avant qu'ils entrent dans une pub.
- Pubs FR et EN séparées ; classer par la langue du texte réel.
- Les deux anti-objections : les chances sont bien meilleures qu'une loterie, et un tiers choisit les gagnants.

## Mémoire
Accroches et angles qui ont marché, par concours ; ce qui a fatigué vite.

## Indicateurs
Part des brouillons acceptés sans retouche ; temps entre la demande et le brouillon ; durée de vie d'une pub avant fatigue ; part des pubs qui finissent parmi les meilleures ; coût par pub (crédits).

## Relations
Croissance et marketing (Roman : tâches de fatigue créative, résultats des pubs), Opérations des concours (calendrier, voiture), Produit et marchandisage (produits à mettre en avant).

## Interface
Bureaux de Sean et Neela ; chaque brouillon visible dans la file d'approbations avec un aperçu.

## Pas encore décidé
- Le volume exact (début de concours / par semaine).
- La méthode de composition du texte et du logo sur les images.
- Si la génération se fait un jour dans le nuage ou reste sur le Mac de Seb.
