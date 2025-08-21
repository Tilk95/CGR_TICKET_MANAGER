# CGR Ticket Manager

Appli 100% client (Vanilla JS) pour gérer des billets CGR :
- Import PDF (pdf.js), extraction code *CIN…* + date de validité + code web
- Sauvegarde locale (localStorage), marquage *utilisé*
- “Pass” plein écran avec code-barres (JsBarcode) pour scanner au cinéma
- Mode sombre/clair (persistant)

## Utilisation locale
Ouvrir `index.html` dans un navigateur moderne (Chrome/Edge/Firefox mobile ou desktop).

## Déploiement
Pousser ce dépôt sur GitHub puis l’importer dans Vercel (framework = **Other**, pas de build).
