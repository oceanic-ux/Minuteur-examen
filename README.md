# Minuteurs d'examen — Haut-Lac

Application web progressive (PWA) de minuteurs multi-examens pour Haut-Lac International School.

## Installation sur GitHub Pages

### 1. Créer un dépôt GitHub

1. Allez sur [github.com](https://github.com) et connectez-vous (ou créez un compte gratuit)
2. Cliquez **New repository** (bouton vert en haut à droite)
3. Nommez-le `minuteurs-haut-lac` (ou autre nom de votre choix)
4. Laissez-le **Public**
5. Cliquez **Create repository**

### 2. Déposer les fichiers

**Option A — Interface web (plus simple) :**
1. Dans votre nouveau dépôt, cliquez **uploading an existing file**
2. Glissez-déposez TOUS les fichiers de ce dossier :
   - `index.html`
   - `manifest.json`
   - `service-worker.js`
   - `Haut-Lac-logo.svg` ← **à copier depuis votre dossier de travail**
   - Le dossier `icons/` avec ses 3 fichiers PNG
3. Cliquez **Commit changes**

**Option B — GitHub Desktop ou ligne de commande :**
```bash
git init
git add .
git commit -m "Initial commit"
git remote add origin https://github.com/VOTRE-NOM/minuteurs-haut-lac.git
git push -u origin main
```

### 3. Activer GitHub Pages

1. Dans votre dépôt, allez dans **Settings** → **Pages**
2. Sous *Source*, choisissez **Deploy from a branch**
3. Choisissez la branche **main** et le dossier **/ (root)**
4. Cliquez **Save**
5. Après ~1 minute, l'URL apparaît : `https://VOTRE-NOM.github.io/minuteurs-haut-lac/`

### 4. Installer sur iPad / iPhone

1. Ouvrez l'URL dans **Safari** (pas Chrome — seul Safari permet l'installation sur iOS)
2. Appuyez sur le bouton **Partager** (carré avec flèche vers le haut)
3. Faites défiler et appuyez **Sur l'écran d'accueil**
4. Appuyez **Ajouter**

L'app apparaît sur l'écran d'accueil comme une vraie application, s'ouvre en plein écran sans barre Safari, et fonctionne hors ligne.

### Mettre à jour l'app

Pour mettre à jour, re-déposez le fichier `index.html` modifié sur GitHub.
Incrémentez le numéro de cache dans `service-worker.js` (`minuteurs-v2`, etc.)
pour forcer le rechargement sur les appareils existants.

## Fichiers requis dans le même dossier

| Fichier | Description |
|---------|-------------|
| `index.html` | L'application principale |
| `manifest.json` | Configuration PWA |
| `service-worker.js` | Cache hors ligne |
| `Haut-Lac-logo.svg` | Logo affiché dans les cercles |
| `icons/icon-192.png` | Icône app (petite) |
| `icons/icon-512.png` | Icône app (grande) |
| `icons/apple-touch-icon.png` | Icône pour iOS |
