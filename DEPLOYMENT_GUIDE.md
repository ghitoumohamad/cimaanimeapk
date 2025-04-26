# Guide de déploiement pour l'application "سيما انمي" (Cima Anime)

Ce guide vous explique comment déployer votre application "سيما انمي" (Cima Anime) sur Vercel, une plateforme d'hébergement gratuite et performante pour les applications Next.js.

## Prérequis

- Un compte GitHub, GitLab ou un compte email pour s'inscrire sur Vercel
- Le package de déploiement de l'application (fourni dans l'archive ZIP)

## Étapes de déploiement sur Vercel

### 1. Créer un compte Vercel

1. Visitez [vercel.com](https://vercel.com/signup)
2. Inscrivez-vous avec GitHub, GitLab, Bitbucket ou votre email
3. Suivez les instructions pour compléter votre inscription

### 2. Installer l'application Vercel CLI (optionnel)

Si vous préférez déployer via la ligne de commande :

```bash
npm install -g vercel
```

### 3. Déployer l'application

#### Option A: Via l'interface web (recommandée)

1. Connectez-vous à votre compte Vercel
2. Cliquez sur "New Project" (Nouveau Projet)
3. Importez le dossier de l'application depuis votre ordinateur ou depuis un dépôt Git
4. Configurez votre projet :
   - Framework Preset: Next.js
   - Root Directory: ./
   - Build Command: npm run build
   - Output Directory: .next
5. Cliquez sur "Deploy" (Déployer)

#### Option B: Via la ligne de commande

1. Ouvrez un terminal dans le dossier de l'application
2. Exécutez la commande suivante et suivez les instructions :
```bash
vercel
```

### 4. Accéder à votre application

Une fois le déploiement terminé, Vercel vous fournira une URL (par exemple, `cima-anime.vercel.app`) où votre application sera accessible.

## Configuration du domaine personnalisé (optionnel)

Si vous souhaitez utiliser votre propre nom de domaine :

1. Dans le tableau de bord Vercel, sélectionnez votre projet
2. Allez dans "Settings" > "Domains"
3. Ajoutez votre domaine et suivez les instructions pour configurer les DNS

## Mise à jour de l'application

Pour mettre à jour votre application après des modifications :

1. Modifiez les fichiers nécessaires
2. Redéployez en utilisant la même méthode que précédemment

## Besoin d'aide ?

Si vous rencontrez des difficultés lors du déploiement, consultez la [documentation officielle de Vercel](https://vercel.com/docs) ou contactez-moi pour obtenir de l'assistance.
