# Points à confirmer avant publication

## 1. Un tarif manque — Masque Curl Hair Care 500 ml

La grille tarifaire suisse donne, pour la gamme Curl :

| Produit | Format | Prix |
|---|---|---|
| Masque | **1 000 ml** | 14,50 CHF |

Or le catalogue ne propose le masque Curl **qu'en 500 ml** — c'est le format de
Laly Cosmetics, et la consigne est de ne pas changer les formats.

Les deux lectures possibles s'excluent :

- la grille vise bien un 1 000 ml, absent du catalogue : le 500 ml n'a alors
  aucun prix suisse ;
- la grille s'est trompée de contenance et vise le 500 ml à 14,50 CHF — ce que
  rendrait plausible le fait que **tous** les autres masques 500 ml de la
  grille sont à 14,50 CHF (Dry, Color, Fluidaliss), quand les 1 000 ml sont à
  20,90 CHF.

Rien n'a été inventé. La référence paraît au catalogue, à sa place dans la
gamme, avec la mention « Tarif à confirmer » et « Nous consulter » ; elle n'est
pas commandable. **Un mot de votre part suffit à la débloquer** : il n'y a
qu'une ligne à changer dans `build/catalogue.py`.

## 2. TVA — ni HT ni TTC

Le catalogue n'indique rien : il affiche « Prix en CHF ». L'ancien catalogue
suisse AF Lix Lox laissait déjà la question ouverte, faute d'information.

Le catalogue français, lui, affiche « HT » partout, parce que la mention y
était confirmée.

À trancher. Si les tarifs suisses sont hors TVA, la mention se rajoute en une
fois dans `build/generate.py`.

## 3. Références de la grille suisse volontairement écartées

La grille tarifaire comporte des produits et des formats absents du catalogue
Laly Cosmetics. Conformément à la consigne, aucun n'a été ajouté :

| Grille suisse | Motif |
|---|---|
| Gamme **Fluidaliss** entière (shampoing 300 / 1 000 ml, masque 500 / 1 000 ml) | gamme absente du catalogue |
| Activateur 150 ml | seul le 1 000 ml est au catalogue |
| Shampoing Greasy 300 ml | seul le 1 000 ml est au catalogue |
| Masque Curl 1 000 ml | seul le 500 ml est au catalogue — voir point 1 |
| Kit Botox 45 × 2 ml · 139,00 | référence absente du catalogue |
| Nano Repair : shampoing préparateur 500 g · 40,00 et traitement 500 g · 170,00 | références absentes du catalogue |
| Permanente Extra Wave 500 ml · 30,00 | seul le neutralisant est au catalogue |
| Shampoing No Yellow 500 ml | absent du catalogue : aucune confirmation à demander |

Les poudres décolorantes gardent leur fiche unique à trois puissances, aux prix
de la grille : 7 tons 27,00 · 9 tons 32,00 · 10 tons 39,00 CHF. Les couleurs de
sachet (bleue, grise, rose) sont celles de la grille ; la fiche n'affiche que le
pouvoir éclaircissant, comme dans le catalogue français.

## 4. Colorations

Les deux gammes appartiennent à Profesia Hair.

| Gamme | Tube 100 ml | Nuances |
|---|---|---|
| Profesia Hair | 8,50 CHF | 70 |
| Ekstra Color sans ammoniaque | 8,90 CHF | 41 |

Ces prix remplacent les 10,40 et 10,90 CHF de l'ancien catalogue suisse.

Le calcul est une simple multiplication, y compris lorsque le salon mélange les
deux gammes. Vérifié : 12 tubes Profesia = 102,00 · 24 = 204,00 · 48 = 408,00 ·
50 = 425,00 CHF. Ekstra : 12 = 106,80 · 24 = 213,60 · 48 = 427,20 · 50 =
445,00 CHF.

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

La liste complète ressort à chaque génération :
`python3 build/generate.py`.

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
