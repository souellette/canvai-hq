# Créatifs statics Canvai

Démarche pour produire des publicités statiques Canvai qui performent. À utiliser quand Seb demande des concepts de pub, des statics, ou du créatif pour un nouveau concours.

## Ce que les données disent — performance par angle (90 jours, sept. 2026)

| Angle | Dépense | Achats | CPA | CTR |
|---|---|---|---|---|
| Urgence / compte à rebours | 7 377 $ | 384 | **19,21 $** | 3,32 % |
| Événement / communauté | 1 431 $ | 74 | **19,34 $** | 3,88 % |
| Détail produit / le char | 3 359 $ | 159 | **21,13 $** | **3,92 %** |
| Preuve sociale / gagnant | 1 876 $ | 70 | 26,81 $ | 3,07 % |
| Générique / notoriété | 10 963 $ | 382 | 28,70 $ | 2,55 % |

**Le déséquilibre à corriger : 44 % du budget va dans l'angle le moins performant.** Réaffecter le budget générique vers les trois premiers angles vaudrait environ +166 achats pour le même argent.

## Le principe directeur

**La spécificité bat la beauté.**

Gagnants : gros plans concrets — `cles` (16-20 $ de CPA), `interieur` (15-18 $), `keyonthefloor` (7 $).
Perdants : belles images de véhicule — `DRIVE BY` (35 $), `Paint EN` (46 $), `FULL BODY` (25 $), `POV` (29 $).

Un gros plan dit « ça va être à toi ». Un plan large dit « regarde ce beau char ». Le premier fait acheter.

## Autres constats à respecter

- **Les duplicatas performent mieux que les originaux** (CPA 20,39 $ contre 24,58 $). Dupliquer systématiquement un gagnant.
- **Les annonces de gagnant ne convertissent pas en acquisition** — `GAGNANT EVO` (110 $), `GAGNANT R34` (0 achat), série `Carney` (0 achat). Les réserver au retargeting.
- **FR et EN performent de façon identique** (27,90 $ contre 28,12 $). Produire les deux langues par défaut.
- **L'audience est saturée** (fréquence compte : 5,06). Un nouveau créatif sert surtout à atteindre de NOUVELLES audiences, pas à re-marteler les mêmes 200 000 personnes.

## Le problème du cycle de 3 mois

Un concours dure environ 3 mois, donc une seule vraie date limite par trimestre. L'urgence ne peut pas être fabriquée en continu. Solution : empiler des cycles courts — instant wins, plafond de billets, paliers communautaires, early bird 48 h, promos weekend récurrentes, bonus de référencement. Détail complet dans `canvai/marketing/analyse-acquisition-2026-09.md`.

## Direction visuelle (corrigée le 21 sept. 2026)

**Le style sombre et dramatique (noir, éclairage rouge, look cinéma) a été rejeté par Seb : « beaucoup trop dramatique ».** Il ne correspond pas à la marque.

Le vrai style Canvai, visible dans les 15 statics CVA10 (`CVAxx/CVA10 - BMW M3 E92/Ads`) :
- Plein jour, lumière naturelle, couleurs vraies. L'auto est orange vif.
- Gros titres condensés blancs ou noirs, un mot en orange ou en rouge.
- Bandeau rouge ou bleu (« NEW GIVEAWAY / NOUVEAU CONCOURS »).
- Logo `CANVAI · ENTER · WIN · DRIVE` en bas.
- Formats : gros plan de détail, auto qui roule (« SPOTTED CANVAI »), auto devant une maison (« IMAGINE-LA DANS TON ENTRÉE »).

## Générer avec Higgsfield à partir de vraies photos

1. Partir des vraies photos du shooting (`Shoot/Photos Dimah`), redimensionnées à 2048 px max.
2. Les envoyer comme références (`image_references`), modèle `gpt_image_2_5`, ratio 4:5, qualité `high`, résolution `2k` (3 crédits l'image). La qualité par défaut (`low`) donne un rendu plastique.
3. Prompt type : « Edit the reference photo: keep the exact same orange BMW M3 unchanged (same paint, wheels, splitter, proportions). Place it [scène]. Realistic natural photograph, true-to-life colours, no dramatic lighting, no film grain, no cinematic look. No people, no text, no logos added anywhere. Keep the top 25 percent of the frame calm so a headline can be added later. »
4. **Ne jamais demander de texte dans l'image** : les accents français sautent. Mais **livrer des annonces complètes, pas des fonds d'image** : titre, angle de vente, offre, bandeau, logo `CANVAI · ENTER · WIN · DRIVE` et mention légale. Utiliser `canvai/marketing/creatifs-M3-higgsfield-2026-09-21/annonces-finies/build_ads.py` (polices DIN, logo blanc de Dropbox) : une entrée par annonce, FR et EN.
   - Chaque annonce = une étape TEEP + un angle vrai. Jamais de promesse de chances (« plus d’entrées = plus de chances ») : le règlement de Seb dit qu’un achat n’augmente pas les chances.
   - Mention légale en pied d’annonce : reprendre le texte du règlement en vigueur. Le document trouvé dans Dropbox (`NO PURCHASE NECESSARY…`) date de mars 2024 et contient des champs vides : à faire confirmer par l’avocate pour CVA10.
5. **Vérifier chaque image contre la vraie voiture.** Les détails fins sont peu fiables : plaque, texte de la bannière du pare-brise (souvent illisible), ruban des jantes. Les vraies photos restent la référence.
6. Ne jamais générer un gagnant, un visage, une remise de clés ou tout ce qui sert de preuve. Pour l'étape « Evaluation », utiliser uniquement de vrais gagnants (voir dossier).
7. Le calendrier compte : les scènes doivent correspondre à la fin du concours (automne pour un concours qui ferme le 11 octobre, pas de neige).

## Cadre TEEP (Thinking, Exploring, Evaluating, Purchasing)

| Étape | État d'esprit | Créatif |
|---|---|---|
| T | Il scrolle, il ne cherche rien | Gros plan de détail réel, auto dans un décor de vie (entrée, garage) |
| E | « C'est quoi Canvai? » | Merch réel, comment ça marche, site |
| E | « C'est vrai? » | Vrais gagnants, vrai tirage par le tiers indépendant |
| P | « Pourquoi maintenant? » | Compte à rebours, une offre, un seul appel à l'action |

Ne rien afficher qui ne soit pas vrai et vérifiable : nombre de concours, nom d'un gagnant, nombre d'entrées d'un pack, offres. Vérifier contre le site et les dossiers avant d'écrire.

## Après la génération

- Produire la version EN de chaque gagnant — les deux langues performent pareil.
- Dupliquer chaque gagnant dans Meta (la copie bat l'original).
- Nommer les publicités par angle, pas par sujet, pour que l'analyse par angle reste possible : `URG-cadran-FR`, `PROD-cles-EN`, `EVT-jdmfest-FR`.

## À mettre à jour

Refaire l'analyse par angle après chaque concours et corriger le tableau ci-dessus. Le prompt doit suivre les données, pas l'inverse.
