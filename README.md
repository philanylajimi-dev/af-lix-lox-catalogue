# AF Lix Lox — Catalogue professionnel Suisse

Catalogue de prix destiné aux salons de coiffure suisses, partagé par WhatsApp.
Page statique : pas de compte, pas de paiement en ligne. Le salon compose sa
commande, le catalogue calcule le montant en francs suisses hors taxes, et le
bouton WhatsApp ouvre une conversation avec le message déjà rédigé.

Projet autonome. Il reprend l'organisation, les photographies, les produits et
le fonctionnement du catalogue français Laly Cosmetics ; ses prix, son identité
et ses conditions lui sont propres.

**Aucune promotion.** Pas de palier, pas de quantité offerte, pas de minimum de
commande : chaque référence est payante, du premier au dernier article.

**Aucune coordonnée affichée.** Ni téléphone, ni adresse, ni courriel. Le numéro
WhatsApp destinataire ne sert qu'à construire le lien du bouton de commande.

## Structure

```
index.html                 page générée — ne pas éditer à la main
assets/aflixlox.css        direction artistique
assets/aflixlox.js         commande, calculs, message WhatsApp
assets/img/aflixlox-*      logo sombre, logo clair, icône
assets/img/favicon.svg     monogramme AF
assets/img/p/              packshots produit
build/catalogue.py         produits, prix, sections
build/nuancier.py          nuances de coloration
build/generate.py          générateur
```

## Régénérer la page

```sh
python3 build/generate.py
```

Aucune dépendance : Python 3 seul suffit. Le script affiche les références sans
photographie, celles dont le visuel reste à valider et celles qui ne sont pas
commandables.

## Modifier le catalogue

Tout se passe dans `build/catalogue.py`, puis on régénère.

- **Un prix** — la valeur est en **centimes de franc suisse**, entière : `1780`
  vaut 17,80 CHF. Tous les calculs se font en centimes, jamais en virgule
  flottante. Les tarifs sont hors taxes : `TAXES` porte la mention affichée.
- **Un prix non confirmé** — laisser `None` et renseigner `attente="…"`. La
  carte affiche « Tarif à confirmer » puis « Nous consulter », et la référence
  reste hors du panier. Ne jamais inventer un montant.
- **Une photographie** — remplacer `None` par le nom du fichier déposé dans
  `assets/img/p/`, sans l'extension `.webp`.
- **Rendre une référence commandable** — lui donner un prix et supprimer son
  `attente="…"`. Elle gagne aussitôt son sélecteur de quantité et son bouton
  d'ajout.
- **Ajouter ou retirer une référence** — ajouter ou retirer une ligne `P(...)`
  dans la bonne section. Le `ref` est l'identifiant du panier : une fois le
  catalogue diffusé, ne plus le changer, sinon les commandes en cours chez les
  salons perdent la ligne concernée.
- **Le numéro WhatsApp** — `TELEPHONE_WHATSAPP`, au format international sans
  signe ni espace : `41767262088`.

Les nuances vivent dans `build/nuancier.py`. Pour retirer une nuance
indisponible, supprimer sa ligne ; pour en ajouter une, l'insérer dans sa
famille avec son code exact.

### La liste des produits est fermée

Le catalogue Laly Cosmetics fixe les références autorisées : mêmes produits,
mêmes formats, mêmes visuels. La grille tarifaire suisse ne sert qu'à fixer les
prix de ces références. Une référence qui figure sur la grille suisse mais pas
dans Laly Cosmetics n'entre pas au catalogue — voir `NOTES.md` pour la liste de
celles qui ont été écartées, et pourquoi.

## Mettre en ligne — GitHub Pages

Le catalogue est entièrement statique : il n'a besoin d'aucun serveur et
fonctionne Mac éteint.

Le dépôt local est initialisé et le premier commit est fait. Il reste à créer
le dépôt `af-lix-lox-catalogue` sur GitHub, puis :

```sh
git remote add origin https://github.com/philanylajimi-dev/af-lix-lox-catalogue.git
git push -u origin main
```

Puis, sur GitHub : **Settings → Pages → Source : Deploy from a branch →
`main` / `/ (root)`**. L'adresse publique sera
`https://philanylajimi-dev.github.io/af-lix-lox-catalogue/`.

Cette adresse ne change plus. Pour mettre à jour les produits ou les prix :
modifier `build/catalogue.py`, relancer `python3 build/generate.py`, puis
`git add . && git commit -m "…" && git push`. Le site se met à jour seul en une
minute environ.

`.nojekyll` évite que GitHub Pages n'essaie d'interpréter le dossier comme un
site Jekyll.

## Prévisualiser sur le Mac

Ouvrir `index.html` directement dans le navigateur suffit pour relire la page.
Pour être dans les mêmes conditions que GitHub Pages :

```sh
cd ~/af-lix-lox-catalogue
python3 -m http.server 8000
```

puis `http://localhost:8000` dans le navigateur. `Ctrl+C` arrête le serveur.

## Les deux catalogues

Ils sont indépendants et ne partagent aucun fichier.

| | Laly Cosmetics — France | AF Lix Lox — Suisse |
|---|---|---|
| Dépôt | `laly-cosmetics` | `af-lix-lox-catalogue` |
| Dossier | `~/Desktop/laly-cosmetics-catalogue` | `~/af-lix-lox-catalogue` |
| Prix | euros | francs suisses |
| Promotions | oui | aucune |
| Produits | la liste de référence | strictement la même |

Un troisième dépôt, `aflixlox-catalogue-suisse`
(`~/Documents/GitHub/`), contient l'ancien catalogue suisse : une simple liste
de prix, sans panier. Il n'a pas été touché.

## Points ouverts

Voir `NOTES.md`.
