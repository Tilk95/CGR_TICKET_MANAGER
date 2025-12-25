# CGR Ticket Manager

Application PWA 100% client (Vanilla JS) pour gérer des billets CGR Cinémas avec une interface moderne et intuitive.

## 🎯 Fonctionnalités Principales

### 📥 ***Import & Gestion***
- **Import PDF automatique** : Drag & drop ou sélection de fichiers
- **Extraction intelligente** : Codes CIN, dates de validité, codes web
- **Détection automatique** : Types ICE vs Standard (basé sur "PLACE CGR ICE")
- **Gestion des doublons** : Mise à jour intelligente des tickets existants

### 🎟️ **Types de Billets**
- **Standard** : Billets classiques CGR
- **ICE** : Billets Premium ICE (détection automatique)
- **Détection robuste** : Multi-patterns pour une identification fiable

### 🗑️ **Gestion des Tickets**
- **Marquage utilisé** : Modal de saisie avec film, date/heure et notes
- **Édition des informations** : Modification des détails d'usage existants
- **Historique d'usage** : Suivi complet des séances regardées
- **Suppression manuelle** : Bouton de suppression avec confirmation
- **Statuts visuels** : Disponible, expiré, utilisé
- **Recherche** : Par code CIN ou code web

### 📱 **Interface Utilisateur**
- **Design responsive** : Mobile-first avec PWA
- **Thèmes dynamiques** : Mode sombre/clair persistant
- **Vues filtrées** : Disponibles uniquement ou tous les tickets
- **Codes-barres** : Génération pour scan au cinéma
- **Mode plein écran** : Optimisé pour les scanners

### 💾 **Données & Export**
- **Stockage local** : localStorage avec sauvegarde automatique
- **Export JSON** : Sauvegarde complète de la base
- **Import JSON** : Restauration des données
- **Accès console** : Gestion manuelle via F12 → Application

## 🚀 Installation & Utilisation

### **Utilisation Locale**
1. Ouvrir `index.html` dans un navigateur moderne
2. Compatible : Chrome, Edge, Firefox, Safari (mobile & desktop)

### **Déploiement Web**
1. Pousser ce dépôt sur GitHub
2. Importer dans Vercel (framework = **Other**, pas de build)
3. L'application sera accessible en ligne

## 🔧 Structure Technique

### **Technologies Utilisées**
- **Vanilla JavaScript** : 100% client-side
- **PDF.js** : Parsing des PDF CGR
- **Day.js** : Gestion des dates (locale française)
- **JsBarcode** : Génération de codes-barres
- **CSS Variables** : Système de thèmes dynamique
- **PWA** : Manifeste et icônes pour installation mobile

### **Structure des Données**
```javascript
{
  code: "CIN40819B83613F7",        // Code CIN complet
  codeweb: "D60235",               // Code web optionnel
  type: "ICE" | "Standard",        // Type détecté automatiquement
  validUntil: "2025-05-04",        // Date de validité
  used: false,                     // Statut d'utilisation
  usage: {                         // Informations d'usage (si utilisé)
    film: "Nom du film",           // Film regardé
    datetime: "2025-01-15T20:30", // Date et heure de la séance
    notes: "Salle 5, 3D",         // Notes optionnelles
    usedAt: "2025-01-15T20:25",   // Date/heure de marquage
    updatedAt: "2025-01-15T20:25" // Date/heure de dernière modification
  },
  prefix: "CIN40819",              // Préfixe extrait
  letter: "B",                     // Lettre extraite
  num: "83613",                    // Numéro extrait
  source: "nom_du_fichier.pdf"     // Source du PDF
}
```

## 📱 Fonctionnalités PWA

- **Installation** : Ajouter à l'écran d'accueil
- **Hors ligne** : Fonctionne sans connexion
- **Icônes** : Adaptatives pour tous les appareils
- **Thème** : Intégration avec le système d'exploitation

## 🎨 Personnalisation

### **Thèmes**
- **Mode sombre** : Interface sombre par défaut
- **Mode clair** : Interface claire pour la journée
- **Persistance** : Choix sauvegardé automatiquement

### **Interface**
- **Responsive** : S'adapte à tous les écrans
- **Accessibilité** : Navigation clavier et lecteurs d'écran
- **Internationalisation** : Interface en français

## 🔍 Dépannage

### **Accès aux Données**
- **Console** : F12 → Console → `localStorage.getItem('cgrTickets.v1')`
- **Application** : F12 → Application → Local Storage

### **Gestion Manuelle**
```javascript
// Voir tous les tickets
JSON.parse(localStorage.getItem('cgrTickets.v1'))

// Supprimer un ticket
const tickets = JSON.parse(localStorage.getItem('cgrTickets.v1'))
const filtered = tickets.filter(t => t.code !== 'CODE_A_SUPPRIMER')
localStorage.setItem('cgrTickets.v1', JSON.stringify(filtered))
```

## 📊 Métriques

- **Version** : 3.3 (mobile-first)
- **Lignes de code** : ~350 (HTML + CSS + JS)
- **Performance** : 100% client-side, chargement instantané
- **Compatibilité** : Tous navigateurs modernes

## 🤝 Contribution

L'application est conçue pour être maintenable et extensible. Toutes les fonctionnalités sont documentées et le code est structuré de manière modulaire.

---

**CGR Ticket Manager** - Gestion simple et efficace de vos billets CGR Cinémas 🎬🍿
