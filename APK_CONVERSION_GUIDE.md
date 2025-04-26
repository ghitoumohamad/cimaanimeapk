# Guide de conversion en APK Android pour l'application "سيما انمي" (Cima Anime)

Ce guide vous explique comment convertir votre application web "سيما انمي" (Cima Anime) en application Android (APK) que vous pourrez installer directement sur votre appareil.

## Prérequis

- Un ordinateur avec Node.js installé (version 14 ou supérieure)
- Java Development Kit (JDK) 11 ou supérieur
- Android SDK installé
- Le package de l'application (fourni dans l'archive ZIP)

## Étapes de conversion en APK Android

### 1. Transformer l'application en Progressive Web App (PWA)

1. Installez les dépendances nécessaires :
```bash
cd cima-anime
npm install next-pwa
```

2. Créez un fichier `next.config.js` à la racine du projet avec le contenu suivant :
```javascript
const withPWA = require('next-pwa')({
  dest: 'public',
  register: true,
  skipWaiting: true,
});

module.exports = withPWA({
  reactStrictMode: true,
});
```

3. Créez un fichier `manifest.json` dans le dossier `public` :
```json
{
  "name": "سيما انمي - Cima Anime",
  "short_name": "سيما انمي",
  "description": "منصة لمشاهدة الانمي",
  "start_url": "/",
  "display": "standalone",
  "background_color": "#000000",
  "theme_color": "#E50914",
  "orientation": "portrait",
  "icons": [
    {
      "src": "/icons/icon-192x192.png",
      "sizes": "192x192",
      "type": "image/png"
    },
    {
      "src": "/icons/icon-512x512.png",
      "sizes": "512x512",
      "type": "image/png"
    }
  ]
}
```

4. Créez des icônes pour votre application dans le dossier `public/icons`

5. Reconstruisez l'application :
```bash
npm run build
```

### 2. Installer Bubblewrap CLI

```bash
npm install -g @bubblewrap/cli
```

### 3. Initialiser le projet Bubblewrap

```bash
bubblewrap init --manifest="https://votre-site-deploye.vercel.app/manifest.json"
```

Remplacez `https://votre-site-deploye.vercel.app` par l'URL de votre application déployée sur Vercel.

### 4. Configurer le projet

Modifiez le fichier `twa-manifest.json` généré pour personnaliser votre application :

```json
{
  "packageId": "com.cimaanime.app",
  "host": "votre-site-deploye.vercel.app",
  "name": "سيما انمي - Cima Anime",
  "launcherName": "سيما انمي",
  "display": "standalone",
  "themeColor": "#E50914",
  "navigationColor": "#000000",
  "backgroundColor": "#000000",
  "enableNotifications": true,
  "shortcuts": []
}
```

### 5. Générer une clé de signature

```bash
bubblewrap genkey
```

Suivez les instructions pour créer une clé de signature pour votre application.

### 6. Construire l'APK

```bash
bubblewrap build
```

Cette commande générera un fichier APK dans le dossier `app/build/outputs/apk/release/`.

### 7. Installer l'APK sur votre appareil Android

1. Transférez le fichier APK sur votre appareil Android
2. Sur votre appareil, accédez au fichier APK et touchez-le pour l'installer
3. Vous devrez peut-être autoriser l'installation d'applications provenant de sources inconnues dans les paramètres de sécurité de votre appareil

## Résolution des problèmes courants

### L'application ne s'installe pas
- Vérifiez que vous avez autorisé l'installation d'applications provenant de sources inconnues
- Assurez-vous que l'APK est correctement signé

### L'application s'ouvre mais affiche une page blanche
- Vérifiez que votre application web est correctement déployée et accessible
- Assurez-vous que le fichier manifest.json est correctement configuré

### L'application ne fonctionne pas hors ligne
- Vérifiez que vous avez correctement configuré le service worker dans votre PWA

## Besoin d'aide ?

Si vous rencontrez des difficultés lors de la conversion en APK, consultez la [documentation officielle de Bubblewrap](https://github.com/GoogleChromeLabs/bubblewrap/tree/main/packages/cli) ou contactez-moi pour obtenir de l'assistance.
