# Campagne Meta Canvai (brouillon via le connecteur Meta Ads)

Démarche pour monter une campagne Canvai dans Ads Manager à partir des médias déjà téléversés, en brouillon, avec plusieurs textes par pub. À utiliser quand Seb demande de « préparer une campagne », des pubs pour la fin d'un giveaway, ou de recréer une campagne.

Modèle éprouvé : « CVA10 - Derniers jours V3 » (30 sept. 2026).

## Les faits à connaître

- **Compte publicitaire :** Canvai Ads, `763277702499928`. **Page :** Canvai `118150338051489`. **Compte Instagram :** `6352286111536617` (il est apparu dans les brouillons, mais `ads_get_ig_accounts` renvoie vide). **Pixel :** `2658307334564463`. **Lien :** `https://canvai.ca` (même lien FR et EN, aucune adresse française distincte trouvée).
- **Campagne modèle :** « CVA10 - Sales Campaign » (`120250962548020594`). Ensembles modèles : « CANADA - FR » `120250962548000594` (langues 9 et 44), « CANADA - EN » `120251039101040594` (langues 6 et 24).
- **Tout se crée en brouillon.** Rien ne diffuse tant qu'on n'appelle pas `ads_activate_entity`. Ne jamais activer sans que Seb le demande.
- **Les médias sont déjà dans Meta.** `ads_get_ad_images` (hash) et `ads_get_ad_videos` (id, avec `video_ids` pour avoir la miniature). Les médias du jour ont un `created_time` récent.

## Étapes

1. **Lire les médias** (images et vidéos téléversés aujourd'hui). Les regarder pour classer FR / EN par le texte réel de l'image. Vérifier les fautes de français (ex. « DERNIER JOURS » au lieu de « DERNIERS »). Les fichiers sources sont dans `~/Dropbox/Canvai/CVAxx/<concours>/Ads/`.
2. **Une seule campagne**, pas une par type de média. Deux ensembles de pubs : « Canada français » et « Canada anglais ». Séparer les langues (règle 5 de LESSONS). Les vidéos FR vont seulement dans l'ensemble FR.
3. **Copier les réglages du modèle** :
   - `ads_create_campaign` avec `source_campaign_id`.
   - `ads_create_ad_set` avec `source_adset_id`, `optimization_goal: VALUE`, `promoted_object` `{"pixel_id":"2658307334564463","custom_event_type":"PURCHASE"}`, `end_time`, budget, `targeting` FR ou EN.
   - Puis `ads_update_entity` (ad_set) avec le ciblage `{"geo_locations":{"countries":["CA"],"location_types":["home","recent","frequently_in"]},"age_min":18,"age_max":65,"locales":[9,44],"targeting_optimization":"expansion_all","targeting_automation":{"advantage_audience":1}}` pour avoir l'audience Advantage+ comme la campagne active. Langues EN : `[6,24]`.
   - `destination_type` : ne rien mettre (Advantage+ par défaut quand on copie le modèle).
4. **Une pub par média**, dans le format natif de Meta (voir ci-dessous).
5. **Relire le brouillon** avec `ads_get_ad_entities` (`object_state: "draft"`, `object_ids: [campagne]`, `level: "ad"`). Compter : 18 pubs actives, 0 « supprimée ». Le fichier est gros : le lire avec Python, pas avec Read.
6. **Seb ouvre une pub dans Ads Manager** pour confirmer que le média et les textes s'affichent. La relecture de l'API ne suffit pas.

## Le format des pubs à plusieurs textes (la seule version qui s'affiche)

Le média, le lien et le bouton restent dans `object_story_spec` (partie standard). Les versions de texte et de titre vont dans `asset_feed_spec` avec `optimization_type: "DEGREES_OF_FREEDOM"`. **Ne jamais mettre `images`, `videos` ou `link_urls` dans `asset_feed_spec`** : Ads Manager affiche alors « Add media » vide.

Image :

```json
{"object_story_spec":{"page_id":"118150338051489","instagram_actor_id":"6352286111536617",
 "link_data":{"link":"https://canvai.ca","image_hash":"<HASH>",
  "call_to_action":{"type":"SHOP_NOW","value":{"link":"https://canvai.ca"}}}},
 "contextual_multi_ads":{"enroll_status":"OPT_IN"},
 "asset_feed_spec":{"optimization_type":"DEGREES_OF_FREEDOM",
  "bodies":[{"text":"..."},{"text":"..."}],
  "titles":[{"text":"..."},{"text":"..."}]}}
```

Vidéo : même chose avec `video_data` `{"video_id":"<ID>","image_url":"<miniature>","call_to_action":{...}}` à la place de `link_data`. La miniature est obligatoire (sinon « Your ad needs a video thumbnail ») : prendre `picture` de `ads_get_ad_videos`.

## Règles

- **Multi-annonceurs :** `contextual_multi_ads` à `OPT_IN` seulement parce que Seb l'a demandé. Le défaut de l'outil est `OPT_OUT`. Le dire à Seb.
- **Les créatifs ne se modifient pas.** Pour changer un texte, créer la pub de nouveau puis supprimer l'ancienne (`ads_update_entity` avec `{"status":"DELETED"}`).
- **Seb ne réédite pas les créatifs dans Ads Manager avant l'activation.** Les modifications faites dans l'éditeur ont déjà vidé des pubs. Il dit ce qu'il veut changer, et on le fait par l'outil.
- **Les pubs « supprimées » restent visibles** dans la liste d'Ads Manager (marquées supprimées, mais encore affichées). Éviter de tout recréer plusieurs fois dans la même campagne. Si on recommence, créer une nouvelle campagne (V2, V3), renommer l'ancienne « SUPPRIMÉ - à discard », et demander à Seb de la discard.
- **Les campagnes en brouillon ne s'archivent pas** (`ARCHIVED` refusé). Le statut `DELETED` est accepté avec un avertissement, et elle reste dans la liste jusqu'à ce que Seb la discard.
- **Le but d'optimisation VALUE** a été refusé par l'API le 21 sept. sur une nouvelle campagne, mais passe en copiant un ensemble modèle avec `promoted_object` fourni.
- **Budget :** ne jamais l'inventer. Demander le montant par ensemble. Les ensembles copiés peuvent revenir à 20 $/j dans le brouillon : relire après coup.

## Textes (ton et format)

- **Fin de giveaway :** urgence juste, pas de hype ni de « ne manquez pas ça ». Date, « 1 $ = 5 participations » (ou le multiplicateur du moment, à demander à Seb), tierce partie qui choisit le gagnant. Détails dans `canvai/marketing/CLAUDE.md`.
- **Format que Seb préfère (30 sept. 2026) :** court, une info par ligne, une ligne vide entre chaque ligne, un emoji en tête de ligne. Première variante : juste « 🏁 Dernière chance ». Trois variantes par langue.
- **Toujours montrer les textes à Seb avant de les mettre dans les pubs.**
- **Vérifier les faits avec Seb** : multiplicateur de participations, « manuelle, V8 », « derniers jours » contre « dernier jour ».

## Ce qu'on ne peut pas faire avec ce connecteur

- Créer une annonce de catalogue (permission de la Page, voir LESSONS du 21 sept.).
- Activer sans demande de Seb, publier des publications de la Page, ou voir ce qu'Ads Manager affiche.
- Reprendre le format « publication de la Page » de la campagne active (mon outil crée des pubs avec lien, pas des publications).
