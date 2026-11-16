# enquetesnaturistes.fr

Site vitrine de la série *Enquêtes naturistes* (Éditions Naturistes). HTML et CSS purs, sans framework ni étape de construction : chaque page est un fichier `.html` qu'on peut ouvrir et corriger directement.

## Organisation

```
index.html                     accueil (une : tome 1.5)
mystere-au-levant.html         tome 1
premier-noel-au-levant.html    tome 1.5
ete-explosif-au-levant.html    tome 2 (avril 2027)
auteur.html, librairies.html, evenements.html, presse.html
mentions-legales.html, merci.html, 404.html
css/style.css                  la seule feuille de style (couleurs de la charte en tête de fichier)
fonts/                         polices hébergées sur le site (aucun appel à Google)
img/                           images du site
presse/                        visuels haute définition à télécharger
vercel.json                    adresses sans « .html » (/auteur au lieu de /auteur.html)
sitemap.xml, robots.txt        référencement
```

L'en-tête, la newsletter et le pied de page sont recopiés dans chaque page : pour changer un lien du menu, il faut le changer partout.

## Mise en ligne (Vercel)

1. Sur vercel.com : **Add New → Project**, importer ce dépôt GitHub. Framework : *Other*. Aucun réglage de build.
2. **Settings → Domains** : ajouter `enquetesnaturistes.fr` et `www.enquetesnaturistes.fr` (puis `enquetes-naturistes.fr` en redirection). Vercel indique les enregistrements DNS à créer chez le registrar.
3. **Analytics** : activer *Web Analytics* (sans cookie, pas de bandeau à prévoir), puis ajouter avant `</body>` de chaque page :
   `<script defer src="/_vercel/insights/script.js"></script>`

Chaque modification envoyée sur la branche `main` est mise en ligne automatiquement.

## Newsletter (Brevo)

Le formulaire est prêt mais pas encore branché. Une fois le formulaire créé dans Brevo (double confirmation activée, redirection après inscription vers `https://enquetesnaturistes.fr/merci`) :

- remplacer `action=""` par l'adresse d'envoi du formulaire Brevo dans chaque page (rechercher `BREVO`) ;
- garder le champ `name="EMAIL"` (c'est le nom attendu par Brevo).

## Reste à compléter

- [x] Mentions légales : adresse et SIRET.
- [x] Adresse de contact : `contact@enquetesnaturistes.fr`, redirection OVH vers la boîte habituelle (MX chez OVH : ne pas les modifier en branchant Vercel).
- [ ] Lien Amazon direct du tome 1.5 (le site pointe pour l'instant vers une recherche Amazon).
- [ ] Logo des Éditions Naturistes (pas encore sur le site).
- [ ] Images en haute définition : scène de terrasse du tome 1 sans texte, couvertures définitives.
- [ ] Page Facebook, si elle doit apparaître.
- [ ] Événements : dupliquer le bloc modèle en commentaire dans `evenements.html`.
- [ ] Couverture définitive du tome 2.
