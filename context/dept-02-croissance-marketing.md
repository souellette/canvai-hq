# Département 02 — Croissance et marketing (approuvé par Seb le 12 oct. 2026)

## But
Faire dépenser chaque dollar de pub là où il rapporte, et éviter que Seb surveille Meta lui-même.

## Responsabilités
- Surveiller Meta Ads (compte Canvai Ads 763277702499928 seulement) : dépense, retour, fréquence DU COMPTE, statut réel des pubs.
- Proposer : budgets, coupures, pubs à pousser.
- Gérer courriel et SMS (Klaviyo) : segments, relances, calendrier d'envois.
- Préparer le plan de fin de concours et ses jalons.
- Détecter la fatigue créative et créer une tâche au département Créatif.

## Agents (2 seulement)
| Agent | Id | Rôle | Statut |
|---|---|---|---|
| Roman | `vigie-meta` | Meta Ads | actif (routine nuage horaire) |
| Gisèle | `gisele` | Klaviyo : courriel, SMS | à bâtir avant la mi-novembre |

Retirés pour l'instant : Han (DOM fait le rôle de directeur), Leon (Google et YouTube : pas de budget Google, à reconfirmer), Dex (les chiffres sont déjà dans « Pouls des ventes »). Leurs fiches existent dans la base sous « à venir » : ne pas les activer sans nouvelle décision de Seb.

## Données et outils
Meta Ads (lecture), Klaviyo (lecture ; écriture seulement après approbation), Shopify (lecture : ventes, commandes), page Ventes et page Concours (données par concours).

## Déclencheurs et fréquence
- Horaire : Roman chaque heure (en place). Gisèle une fois par jour.
- Anomalie : voir les alertes.
- Calendrier : jalons J-7, J-3, J-1 et dernier jour (jours avant la fin du concours).
- Agent à agent : fatigue créative → tâche au Créatif ; audience de relance entre Gisèle et Roman.
- Demande de Seb ou de DOM.

## Jalons de fin de concours (référence CVA10 : 27 % des ventes dans les 7 derniers jours, 11 % le dernier jour)
| Jalon | Action préparée (brouillon, Seb approuve) |
|---|---|
| J-7 | Plan de fin prêt : budget par jour, pubs « dernière chance », SMS et courriels écrits et programmés |
| J-3 | Pousser le budget, relancer ceux qui n'ont jamais acheté |
| J-1 | Dernier rappel SMS et courriel ; plus aucun nouveau test de pub |
| Dernier jour | Roman vérifie chaque heure |

## Alertes (seuils de départ, tirés des 9 concours passés ; à réviser)
- Dépense : plus de 1,5 fois le plan du jour. (Le plan de dépense : qui le fixe est encore à décider avec Seb.)
- Retour sur pub : sous 4x sur 3 jours, sauf pendant les 3 derniers jours du concours (le retour baisse naturellement : CVA10 a fini à 3,5x la dernière semaine).
- Autres : coût par nouveau client +30 %, fréquence du compte en hausse anormale.
Une alerte = une entrée dans le journal et une notification SEULEMENT pour un nouveau problème (pas de répétition horaire).

## Niveau d'automatisation et approbations
- Autonome : lire, analyser, recommander.
- Brouillon, Seb approuve : textes de pubs, SMS, courriels, segments.
- Approbation de Seb TOUJOURS : toute dépense, hausse de budget, pause, publication, envoi.
Règles acquises : pubs FR et EN dans des ensembles séparés (« Canada français » / « Canada anglais ») ; textes de pubs courts, une info par ligne, sans FOMO ni hype, montrés à Seb avant ; aucun coût de SMS annoncé sans l'écran de facturation Klaviyo ; relire chaque brouillon de pub après création (`Skills/campagne-meta-canvai.md`).

## Mémoire
Expériences : hypothèse, résultat, leçon (ex. « 10X en dernière fenêtre »). Historique des concours : page Concours Canvai.

## Indicateurs
Retour sur pub (CVA10 : 5,9x contre 7,1x en moyenne), coût par nouveau client, fréquence du compte, respect du plan de dépense, part des propositions acceptées par Seb.

## Relations
Créatif (reçoit les tâches de fatigue créative), Opérations des concours (calendrier et jalons), Finance et BI (retour, marges), E-commerce et CRO (pages d'atterrissage).

## Interface
Bureaux de Roman et Gisèle dans « Marketing » ; file d'approbations ; carte « plan du concours » avec les jalons.

## Pas encore décidé
- Qui fixe le plan de dépense quotidien, et son format.
- Leon : à rouvrir si Seb ajoute du budget Google.
