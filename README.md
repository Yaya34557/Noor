# NOOR — Boutique de kamis (site statique)

Boutique 100 % statique (HTML/CSS/JS), sans serveur ni build. Compatible GitHub Pages.

## Structure
```
index.html        page unique (navigation par #/ , compatible GitHub Pages)
css/style.css     styles
js/products.js    CATALOGUE, livraison et retours  <- à modifier
js/app.js         pages, panier, filtres, commande
.nojekyll         désactive Jekyll
```

## Mise en ligne sur GitHub Pages
1. Créez un compte sur github.com, puis un dépôt public (ex. `noor`).
2. Cliquez **Add file > Upload files**, glissez le CONTENU du dossier (index.html, css, js, .nojekyll, README.md) et validez avec **Commit changes**.
3. Allez dans **Settings > Pages**.
4. Sous **Build and deployment**, choisissez **Deploy from a branch**, branche `main`, dossier `/ (root)`, puis **Save**.
5. Après 1 à 2 minutes, le site est disponible sur `https://VOTRE-PSEUDO.github.io/noor/`.

## Modifier les produits
Éditez le tableau `P` dans `js/products.js` : `id` (unique, sans espaces), `ref`, `name`, `price`, `desc`, `colors` ([nom, code hex]), `sizes`, `stock`, `cat` (`classique` ou `premium`), `isNew`, `badge`.
Pour de vraies photos, ajoutez un champ `images:["img/xxx.jpg"]` et affichez-le à la place de `kami(...)` dans `js/app.js` (fonction `card` et `gal`). Ajoutez toujours un texte `alt`.

## Limites (site sans serveur)
- **Panier** : enregistré dans le navigateur (localStorage), propre à chaque visiteur.
- **Paiement** : la commande est simulée. Remplacez l'étape finale par un lien Stripe Payment Links, PayPal ou Snipcart.
- **Formulaire de contact** : non envoyé. Utilisez Formspree ou Web3Forms (modifiez le gestionnaire `submit` de `js/app.js`).
- **Pages légales** : à rédiger (mentions légales, CGV, confidentialité, cookies) avant ouverture au public.
- Les coordonnées et réseaux sociaux sont des placeholders (page Contact).
