# Organisation des agents Canvai

Hiérarchie : PDG humain (Seb) → DOM (commandant IA) → directeurs de département → agents spécialisés → outils et données.

## Règles

- Seb parle à DOM. DOM décide quels départements et quels agents travaillent, et rassemble une seule réponse.
- Les agents ne se délèguent pas de travail entre eux. Chacun lit ses sources et écrit dans le Centre de commande (journal, approbations), sous son propre `agentId`.
- Un agent « à venir » n'existe pas encore. Ne jamais écrire qu'il a travaillé.
- Aucune action (dépense, envoi, publication, écriture comptable) sans l'OK de Seb dans la file d'approbation.
- Les identifiants dans la base ne changent pas, même si le nom change (ex. `vigie-meta` = Roman, `pouls-ventes` = Mia).

## Départements et agents

### Exécutif et stratégie (`executif`)

| Agent | Rôle | Id | Vague |
|---|---|---|---|
| DOM (commandant) | Commandant IA | `resume-matin` | vague 1 : cette semaine |
| Brian (directeur) | Directeur exécutif | `brian` | plus tard |
| Mia | Intelligence d'affaires | `pouls-ventes` | vague 1 : cette semaine |
| Vince | Projets et exécution | `vince` | plus tard |

### Croissance et marketing (`marketing`) — conçu et approuvé le 12 oct. 2026, voir `dept-02-croissance-marketing.md`

| Agent | Rôle | Id | Vague |
|---|---|---|---|
| Han (directeur) | Chef de la croissance | `han` | retiré pour l'instant (DOM fait le rôle) |
| Roman | Agent Meta Ads | `vigie-meta` | actif |
| Leon | Agent Google et YouTube | `leon` | retiré pour l'instant (pas de budget Google) |
| Gisèle | Agent CRM, courriel et SMS | `gisele` | vague 2 : avant la mi-novembre |
| Dex | Analytique de croissance | `dex` | retiré pour l'instant (chiffres dans Pouls des ventes) |

### Créatif et contenu (`creatif`)

| Agent | Rôle | Id | Vague |
|---|---|---|---|
| Suki (directeur) | Directrice créative | `suki` | plus tard |
| Jesse | Intelligence créative | `jesse` | plus tard |
| Sean | Agent rédaction | `textes-pubs` | plus tard |
| Neela | Vidéo et UGC | `neela` | plus tard |
| Monica | Réseaux sociaux organiques | `monica` | plus tard |

### E-commerce et conversion (`ecommerce`)

| Agent | Rôle | Id | Vague |
|---|---|---|---|
| Letty (directeur) | Directrice e-commerce | `letty` | plus tard |
| DK | Optimisation de la conversion | `dk` | plus tard |
| Twinkie | Marchandisage | `twinkie` | plus tard |
| Ramsey | Shopify et site web | `ramsey` | plus tard |

### Opérations des concours (`concours`)

| Agent | Rôle | Id | Vague |
|---|---|---|---|
| Toretto (directeur) | Directeur des concours | `toretto` | plus tard |
| Hector | Performance des concours | `calendrier-concours` | vague 1 : cette semaine |
| Santos | Opérations des concours | `santos` | plus tard |
| Carter | Conformité des concours | `carter` | vague 2 : avant la mi-novembre |

### Produit et marchandisage (`produit`)

| Agent | Rôle | Id | Vague |
|---|---|---|---|
| Takumi (directeur) | Directeur produit | `takumi` | plus tard |
| Keisuke | Développement produit | `keisuke` | plus tard |
| Bunta | Tendances et marché | `bunta` | plus tard |
| Ryosuke | Stratégie produit | `ryosuke` | plus tard |

### Sourcing et chaîne d'approvisionnement (`sourcing`)

| Agent | Rôle | Id | Vague |
|---|---|---|---|
| Earl (directeur) | Directeur sourcing | `earl` | plus tard |
| Leo | Recherche de fournisseurs | `leo` | plus tard |
| Slap Jack | Achats et négociation | `soumissions-fournisseurs` | plus tard |
| Orange Julius | Inventaire | `orange-julius` | plus tard |
| Morimoto | Logistique | `morimoto` | plus tard |

### Expérience client (`service`)

| Agent | Rôle | Id | Vague |
|---|---|---|---|
| Nathalie (directeur) | Directrice expérience client | `nathalie` | plus tard |
| Slap | Support client | `tri-service` | vague 2 : avant la mi-novembre |
| Rico | Retours et échanges | `rico` | plus tard |
| Tego | Sentiment des clients | `tego` | plus tard |
| Verone | VIP et rétention | `verone` | plus tard |

### Finances et intelligence d'affaires (`finances`)

| Agent | Rôle | Id | Vague |
|---|---|---|---|
| Mr. Nobody (directeur) | Directeur financier | `mr-nobody` | plus tard |
| Tej | Rentabilité | `bilan-finances` | plus tard |
| Cipher | Flux de trésorerie | `cipher` | plus tard |
| Elena | Comptabilité | `elena` | plus tard |

### Opérations IA et technologie (`ia`)

| Agent | Rôle | Id | Vague |
|---|---|---|---|
| Ludacris (directeur) | Directeur opérations IA | `ludacris` | plus tard |
| Taj | Automatisation | `taj` | plus tard |
| Link | Intégrations | `link` | plus tard |
| Scout | Surveillance des agents | `scout` | vague 1 : cette semaine |
| Quinn | Contrôle de la qualité IA | `quinn` | plus tard |
