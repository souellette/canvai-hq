# Département 05 — Opérations des concours (approuvé par Seb le 12 oct. 2026)

## But
Que chaque concours soit mené proprement de bout en bout (lancement conforme, suivi, tirage, gagnant, remise du véhicule) et que Seb n'ait pas à gérer ces étapes lui-même.

## Responsabilités
- Suivre le concours en cours : ventes, rythme, projection, date de clôture, cible.
- Tenir le calendrier et ses jalons (J-7, J-3, J-1, dernier jour = jours avant la fin) : ils alimentent le département 02.
- Vérifier la conformité avant un lancement : règlement, admissibilité, participation sans achat, dossier RACJ.
- Suivre le processus du tirage et du gagnant (liste de contrôle).
- Signaler les trous entre deux concours.

## Agents (2 seulement)
| Agent | Id | Rôle | Statut |
|---|---|---|---|
| Hector | `calendrier-concours` | Performance, projections, calendrier | vague 1 |
| Carter | `carter` | Conformité ET processus du tirage et du gagnant | vague 2, avant la mi-novembre |

Retirés pour l'instant : Toretto (directeur : DOM fait le rôle), Santos (opérations du tirage : son travail est absorbé par Carter). Leurs fiches restent dans la base, marquées « retiré ».

## Le processus du gagnant (décrit par Seb le 12 oct. 2026)
1. Raymond Chabot (le tiers qui choisit) donne le nom du gagnant.
2. Canvai organise un live Instagram/Facebook pour le contacter.
3. On établit ensuite une date pour la remise du véhicule.
Carter tient la liste de contrôle de ces étapes et prépare des BROUILLONS (plan du live, message, formulaire de publicité du gagnant : les modèles sont dans `~/Dropbox/Canvai/docs`). Il ne contacte personne et ne publie rien.

## État au 12 oct. 2026
CVA10 a fini le 11 octobre. Les dates de CVA11 ne sont pas fixées : Seb veut d'abord « remettre la business droite » (comme le portail AI). Il n'y a donc pas de concours actif pour l'instant. Conséquences :
- L'alerte « trou » (voir plus bas) est suspendue tant qu'aucune date de CVA11 n'existe. En attendant, Hector écrit dans son rapport quotidien « aucun concours actif depuis le 12 oct. ».
- Rappel de l'historique : mars 2026 sans concours = 37 commandes et 1 852 $. Les concours précédents s'enchaînaient presque toujours (14 jours de pause entre CVA09 et CVA10). C'est un choix de Seb, noté sans jugement.

## Outils et données
Shopify (lecture), page Concours Canvai et page Ventes (données par concours), `metriques/concours` du Centre de commande, dossier `~/Dropbox/Canvai/docs` (règlement, RACJ, formulaires, politique de confidentialité).

## Déclencheurs et fréquence
- Hector : une fois par jour, plus à chaque jalon.
- Carter, sur événement : nouveau concours annoncé (vérification de conformité avant lancement) ; fin qui approche (liste de contrôle du tirage) ; tirage fait (liste de contrôle du gagnant).
- Alerte « trou » : pas de concours suivant planifié à moins de 21 jours de la fin du courant (seuil proposé par Claude, à réviser). Suspendue pour l'instant.

## Niveau d'automatisation et approbations
- Autonome : lire, analyser, projeter, vérifier une liste de contrôle.
- Brouillon, Seb approuve : messages au gagnant, plan du live, calendrier.
- JAMAIS sans demande de Seb : modifier le règlement, l'admissibilité ou la mécanique du tirage (révision par l'avocate quand ça compte). Une idée marketing qui touche à la mécanique = question de conformité, pas du texte à assouplir.
- Approbation de Seb TOUJOURS : contacter un gagnant, publier un résultat, annoncer une date de remise.

## Mémoire
Historique des concours (page Concours), dossiers de conformité, gagnants et leurs documents.

## Indicateurs
Ventes par jour contre la cible ; nombre de jours sans concours actif ; liste de conformité complète avant chaque lancement ; délai entre la fin du concours et le gagnant contacté.

## Relations
Croissance et marketing (jalons, calendrier), Créatif (voiture et lot de départ d'un concours), Finance et BI (ventes par concours), Expérience client (gagnant, remise).

## Interface
Bureaux de Hector et Carter, carte du concours, calendrier avec jalons et liste de contrôle du gagnant.

## Pas encore décidé
- La date de CVA11 (Seb).
- Le moment où l'alerte « trou » est réactivée.
- Qui prépare la remise du véhicule (logistique) : pas décrit.
