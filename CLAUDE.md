# Cheirobom — catalogue

Le catalogue produits vit dans `index.html`, dans l'objet JS `const CATALOGUE = {...}` (un seul fichier, pas de backend). Chaque clé est un tableau de produits pour un onglet du site :

- `femme` — parfums femme (variations typiques : 30ml / 70ml)
- `homme` — parfums homme (variations typiques : 30ml / 70ml)
- `mixte` — parfums mixtes (variations typiques : 30ml / 70ml)
- `ambiance` — parfums d'intérieur, deux sous-types distingués par le champ `img` :
  - bouteilles en verre avec bâtonnets (`img: "purfums-interieur.webp"`) : tailles 100 ml / 200 ml / 500 ml / 1,5 L / 3 L
  - sprays noirs (`img` = data URI, image dédiée par produit) : taille unique 500 ml
- `soin` — produits de soin
- `brume` — brumes corps/cheveux

## Règle importante

**Ne jamais modifier les prix des catégories `ambiance` ou `brume` sans demande explicite de l'utilisateur.** Ces catégories ont des grilles de prix spécifiques par sous-type de produit (pas le même barème que les parfums classiques femme/homme/mixte). Un incident précédent a vu les prix `ambiance` écrasés par erreur avec le barème générique parfum (30ml/70ml) lors d'un ajout en masse de produits — toujours vérifier les prix `ambiance`/`brume` restent inchangés après toute modification en masse du catalogue.

Avant tout remplacement massif du fichier `index.html` (ex. depuis un fichier généré ailleurs), comparer catégorie par catégorie avec le fichier actuel pour confirmer qu'aucune catégorie non concernée par la demande n'a été altérée.
