# Points à confirmer avant publication

## 1. Un visuel manque — Masque Curl Hair Care 1 000 ml

Confirmé par AF Lix Lox : **le masque Curl n'existe qu'en 1 000 ml**. La
référence est au catalogue dans ce format, au tarif de la grille suisse —
14,50 CHF HT — et elle est commandable.

Reste sa photographie. La seule disponible est celle du pot de 500 ml
(`masque-cheveux-boucles-curls-hair-care-500-ml.webp`), dont l'étiquette porte
« 500 ml » en clair, lisible sur la carte. Montrer un format qui n'est pas celui
qu'on commande tromperait le salon : la carte affiche donc la vignette
« Visuel à venir ».

**Pour la combler** : déposer une photographie du pot de 1 000 ml dans
`assets/img/p/`, puis remplacer `None` par son nom de fichier (sans `.webp`)
sur la ligne `"mas-cur-1000"` de `build/catalogue.py`, et régénérer.

Si vous préférez le pot de 500 ml en attendant, dites-le : c'est la même
ligne à changer.

## 2. Tarifs

Confirmé par AF Lix Lox : **les prix sont hors taxes**. La mention « HT »
figure sur chacun des 53 prix, sur le prix au tube des deux gammes de
coloration, dans l'ouverture (« Prix en CHF HT »), sur le bilan de chaque
nuancier, sur le total du panier et sur la ligne de total du message WhatsApp.

Chaque référence est payante à l'unité : aucune promotion, aucun palier,
aucune quantité offerte, aucun minimum de commande.

## 3. Références de la grille suisse volontairement écartées

La grille tarifaire comporte des produits et des formats absents du catalogue
Laly Cosmetics. Conformément à la consigne, aucun n'a été ajouté :

| Grille suisse | Motif |
|---|---|
| Gamme **Fluidaliss** entière (shampoing 300 / 1 000 ml, masque 500 / 1 000 ml) | gamme absente du catalogue |
| Activateur 150 ml | seul le 1 000 ml est au catalogue |
| Shampoing Greasy 300 ml | seul le 1 000 ml est au catalogue |
| Kit Botox 45 × 2 ml · 139,00 | référence absente du catalogue |
| Nano Repair : shampoing préparateur 500 g · 40,00 et traitement 500 g · 170,00 | références absentes du catalogue |
| Permanente Extra Wave 500 ml · 30,00 | seul le neutralisant est au catalogue |
| Shampoing No Yellow 500 ml | absent du catalogue : aucune confirmation à demander |

Les poudres décolorantes gardent leur fiche unique à trois puissances, aux prix
de la grille : 7 tons 27,00 · 9 tons 32,00 · 10 tons 39,00 CHF HT. Les couleurs
de sachet (bleue, grise, rose) sont celles de la grille ; la fiche n'affiche que
le pouvoir éclaircissant, comme dans le catalogue français.

## 4. Colorations

Les deux gammes appartiennent à Profesia Hair.

| Gamme | Tube 100 ml | Nuances |
|---|---|---|
| Profesia Hair | 8,50 CHF HT | 70 |
| Ekstra Color sans ammoniaque | 8,90 CHF HT | 41 |

Ces prix remplacent les 10,40 et 10,90 CHF de l'ancien catalogue suisse.

Le calcul est une simple multiplication, y compris lorsque le salon mélange les
deux gammes. Vérifié : 12 tubes Profesia = 102,00 · 24 = 204,00 · 48 = 408,00 ·
50 = 425,00 CHF HT. Ekstra : 12 = 106,80 · 24 = 213,60 · 48 = 427,20 ·
50 = 445,00 CHF HT.

## 5. Photographies à valider (11)

Reprises du catalogue français, où elles portent la même réserve : le visuel est
plausible mais n'a pas été confirmé référence par référence.

- Frequent Hair Care 10 L
- Crème volumisante Dry 200 ml
- Poudre décolorante 500 g (les trois puissances partagent une photographie)
- Soin express Botox 200 ml
- After Shave 400 ml
- Cire Aqua 100 ml
- Cire coiffante 100 ml
- Gel coiffant 500 ml
- Poudre volume 10 g

La liste complète, avec celle des références sans photographie, ressort à
chaque génération : `python3 build/generate.py`.

## 6. Ce qui n'a pas été touché

- **`~/Desktop/laly-cosmetics-catalogue`** — le catalogue français. Lu
  seulement ; aucun fichier modifié, aucun commit, aucune publication.
- **`~/Documents/GitHub/aflixlox-catalogue-suisse`** — l'ancien catalogue
  suisse AF Lix Lox, avec sa version italienne. Inspecté avant toute chose,
  puis laissé intact. Ses deux logos et son favicon ont été **copiés** dans le
  nouveau projet ; rien n'y a été écrit. Il reste en ligne tant que vous ne
  décidez pas de son sort.

Le nouveau catalogue n'a pas de dépôt distant : il n'est **pas publié**. La
marche à suivre est dans `README.md`.
