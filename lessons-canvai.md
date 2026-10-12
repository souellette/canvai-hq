# Leçons Canvai

## Règles
1. Pubs FR et EN dans des ensembles de pubs distincts (« Canada français », « Canada anglais ») : jamais mélangées. Classer par le texte réel, pas par le nom.
2. Pubs Meta : toujours relire le brouillon après l'avoir créé (`ads_get_ad_entities`, mode `draft`). Ne jamais écrire « c'est créé » sur la seule réponse de l'outil.
3. Textes de pubs : versions courtes, une info par ligne, une ligne vide entre chaque, un emoji en tête, trois variantes, la première juste « Dernière chance ». Pas de FOMO ni de hype. Les montrer à Seb avant de les utiliser.

## Leçons
- **Saturation** : juger la saturation par la fréquence au niveau du COMPTE, jamais par la moyenne par publicité (compte à 5,06, moyenne par pub à 1,25).
- **Statut réel** : avant de proposer d'agir sur une pub, une campagne ou un budget, vérifier son `effective_status`. 8 des 13 pubs « à couper » étaient déjà éteintes.
- **Pubs à plusieurs textes** : le média et le lien vont dans `object_story_spec` ; seuls `bodies` et `titles` vont dans `asset_feed_spec`. Un ensemble créé par l'outil peut perdre son pixel ou revenir à 20 $/jour : relire.
- **Annonces de catalogue** : l'API ne peut pas les créer (permission de la page). Le groupe de produits d'un ensemble est immuable.
- **Optimisation** : le but VALUE est refusé sur une nouvelle campagne par l'API ; signaler à Seb quand un nouvel ensemble utilise un autre but.
- **Rapports Shopify** : les produits supprimés perdent leur nom dans les rapports ShopifyQL. Pour l'historique par produit, utiliser l'export groupé des commandes.
- **Servir Seb** : livrer le produit fini, pas la matière première ; regarder les créatifs existants avant de proposer un style.
