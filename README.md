# Petit Tonnerre Festival - Site Web

Site web pour le Petit Tonnerre Festival à Angers (Été 2026).

## 🎯 Structure du projet

```
Petittonnerre_Site/
├── index.html          # Page principale
├── css/
│   └── style.css       # Styles CSS
├── js/
│   └── script.js       # JavaScript
└── README.md           # Documentation
```

## 📋 Fonctionnalités V1

### Navigation
- Menu de navigation fixe avec liens d'ancrage
- Smooth scroll entre les sections
- Menu mobile responsive
- Mise en évidence de la section active au scroll

### Sections

1. **Accueil (Hero)**
   - Logo et titre du festival
   - Zone visuelle (placeholder pour image/affiche/vidéo)
   - Texte d'accroche
   - Boutons CTA (Call to Action)

2. **Le projet**
   - Description du projet
   - Présentation de l'association (mission et valeurs)

3. **Événement à venir**
   - Teaser pour les événements avant l'été 2026

4. **Contact**
   - Formulaire de partenariat
   - Informations de contact (email, réseaux sociaux)

5. **Footer**
   - Newsletter
   - Liens vers les réseaux sociaux
   - Mentions légales et politique de confidentialité

## 🚀 Utilisation

### Ouvrir le site localement

1. Ouvrir `index.html` dans un navigateur web
2. Ou utiliser un serveur local :
   ```bash
   # Avec Python
   python -m http.server 8000
   
   # Avec Node.js (si vous avez http-server installé)
   npx http-server
   ```

### Personnalisation

#### Couleurs
Les couleurs sont définies dans `css/style.css` via les variables CSS :
```css
:root {
    --color-primary: #ff6b35;
    --color-secondary: #f7931e;
    /* ... */
}
```

#### Contenu
- Modifier le texte directement dans `index.html`
- Ajouter vos images dans un dossier `images/` et mettre à jour les chemins
- Personnaliser les liens sociaux dans les sections Contact et Footer

## 🎨 Technologies utilisées

- **HTML5** : Structure sémantique
- **CSS3** : 
  - Variables CSS
  - Flexbox et Grid
  - Animations et transitions
  - Responsive design (mobile-first)
- **JavaScript (Vanilla)** :
  - Navigation smooth scroll
  - Gestion des formulaires
  - Animations au scroll (Intersection Observer)
  - Menu mobile

## 📱 Responsive Design

Le site est entièrement responsive et s'adapte à :
- Mobile (< 480px)
- Tablette (768px)
- Desktop (> 768px)

## 🔮 Prochaines étapes (V2+)

- Intégration d'un framework frontend (React, Vue, etc.)
- Page de programmation des artistes
- Page du village éphémère
- Système de billetterie
- Backend pour les formulaires
- Base de données pour la newsletter

## 📝 Notes pour l'apprentissage

### Concepts CSS utilisés
- **Variables CSS** : Pour une maintenance facile des couleurs
- **Flexbox** : Pour les layouts flexibles
- **Grid** : Pour les layouts en grille
- **Media queries** : Pour le responsive
- **Animations** : Pour les effets visuels
- **Backdrop-filter** : Pour les effets de flou

### Concepts JavaScript utilisés
- **DOM manipulation** : Sélection et modification d'éléments
- **Event listeners** : Gestion des événements
- **Smooth scroll** : Navigation fluide
- **Intersection Observer API** : Animations au scroll
- **FormData API** : Gestion des formulaires

## 🛠️ Améliorations possibles

- [ ] Ajouter un loader au chargement
- [ ] Implémenter un vrai backend pour les formulaires
- [ ] Ajouter des images réelles
- [ ] Optimiser les performances (lazy loading images)
- [ ] Ajouter un bouton "scroll to top"
- [ ] Améliorer l'accessibilité (ARIA labels, etc.)

## 📄 Licence

Projet privé - Petit Tonnerre Festival