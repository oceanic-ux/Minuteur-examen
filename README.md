# Multi-Exam Timer

*Developed by Oceanic Software*

---

## Files

| File | Description |
|------|-------------|
| `minuteur-multi-examens.html` | Desktop version (single standalone file) |
| `pwa/index.html` | PWA version for iPad/iOS (with icons and service worker) |
| `pwa/manifest.json` | PWA manifest |
| `pwa/service-worker.js` | Service worker for iOS installation |
| `pwa/icons/` | Icons for the iOS home screen |

---

## How to Use

### Typical steps
1. **Settings** — Configure reading time, alerts, audio mode, and exams.
2. **Confirm** — Switch to the timer screen.
3. **Start all** — Launch all waiting exams simultaneously, or start each column individually.
4. **Pause** — Pause / resume all timers at any time.
5. **⚙ during the exam** — Side panel: adjust times, add an exam, change voice settings.
6. **Quit** — Return to settings without losing the configuration.

---

## Main Features

### 📖 Reading Time
Period before the exam: candidates may read the paper but not write. Configurable common duration, activatable per paper. At the end, the exam timer starts automatically and a voice announcement is made (if Voice mode is on).

### 🕐 Multiple Timers
Each exam card has its own animated SVG circles:
- **Principal** — always active, standard exam duration.
- **+25%** and **+50%** — if enabled, start at the same time as Principal and run proportionally longer. Displayed below the Principal timer in the same column.
- You can enter a **percentage** (e.g. `25%`), a **decimal proportion** (e.g. `0.5` = 50%), or a **fraction** (e.g. `1/3` for one-third extra time).
- Circles and voice announcements are independent for each timer.

### ➕ Adding Exams
The **＋ Add an exam** button adds a new paper card. While timers are running, use the ⚙ button (top right) → **Add an exam** tab to add a paper without interrupting the others. The IB selector fills all fields automatically.

### 🔔 Sound Alerts

**First alert** — default 30 minutes before the end. Change the duration or disable with the toggle. A `−30` marker appears on the circles at the corresponding position and updates if you change the duration.

**Second alert** — default 5 minutes before the end. Works identically to the first alert.

In **Sound** mode: a beep is played. In **Voice** mode: an announcement is read aloud.

### 🖼 Logo
A logo is displayed at the centre of each timer circle. Click **Change** to upload your own image (JPG, PNG, or SVG). The **↺** button restores the original logo. The custom logo is saved in the browser and reappears on the next visit.

### 🗣 Audio Mode
- **🔇 Silence** — No sound, no announcements.
- **🔔 Sound** — A beep is played at alerts and at the end of each timer.
- **🗣 Voice** — Voice announcements are read automatically. Additional options appear below.

### 🌐 Announcement Language
The announcement language (FR/EN) is **independent** of the interface language. Change it in Audio mode → Language. You can also choose a specific TTS voice from those available on your device.

### 📣 Official IB Announcements
When enabled, voice announcements use official IB Diploma Programme texts. Texts vary by paper type (structured, MCQ, listening comprehension, etc.). Disable to use custom announcements instead. Recommended for official IB examinations.

### ✏️ Customise Announcements
Edit the text of each voice announcement. Six events are customisable: reading start, reading end, exam start, 30-min alert, 5-min alert, exam end. Use dynamic tokens:
- `{duree}` — exam duration (e.g. "90 minutes")
- `{heure}` — current time
- `{restant}` — time remaining
- `{lecture}` — reading time duration

If multiple exams have different durations, announcements are automatically grouped and prefixed with the paper name.

### 📋 IB Schedule
The **📋 IB Schedule** button opens a schedule manager with the full IB 2027 timetable (146 papers).

**Filters**: date (with calendar), session (Morning/Afternoon), level (SL/HL), text search. Click a result to auto-fill the name, duration, IB type, and reading time.

**Manager**: editable table with CSV import/export. Smart merge (add/update). Multi-select rows for bulk deletion.

#### 💡 Creating Your Own Timetable with AI
1. Open **📋 IB Schedule** → **↓ Export CSV** to download the reference format.
2. Provide this CSV + your timetable PDF to an AI (Claude, ChatGPT…).
3. Ask: *"Create a CSV in this format for the exams in this timetable."*
4. Import the generated CSV with **↑ Import CSV**.

CSV format (columns):
```
date, session, subject_fr, subject_en, level, paper, group_fr, group_en, type_fr, type_en, duration_min, notes_fr, notes_en
```
Example: `23/04/2027, Afternoon, Physics, Physics, HL, 1 (1a and 1b), Sciences, Sciences, MCQ + Structured, MCQ + Structured, 120,,`

### ⚙️ Settings During Exam
The side panel (⚙ button, top right) allows during an exam:
- **Adjust times**: ±1 min / ±10 min per exam or per individual timer.
- **Add an exam**: with integrated IB selector.
- **Voice & alerts**: change audio mode, language, voice, and alert thresholds.

### 🖥 Fullscreen
Automatically adapts all element sizes (text, circles, clock) to the available screen.

---

## PWA Installation (iPad / iOS)

1. Open `oceanic-ux.github.io/Minuteur-examen/index.html` on a web server (GitHub Pages, local server, etc.).
2. In Safari, tap **Share → Add to Home Screen**.
3. The app installs as a native app, without a navigation bar.

---

## Persisted Data (localStorage)

| Key | Content |
|-----|---------|
| `hl-prefs` | Preferences: language, audio mode, alerts, reading time, IB mode |
| `hl-logo` | Custom logo (base64) |
| `hl-ib-rows` | Modified/imported IB database |
| `hl-templates` | Custom voice announcements |

---

## IB Paper Types and Announcements

| Type | ibType | Reading time | Announcements |
|------|--------|-------------|---------------|
| Unstructured | `ns` | ✓ | Reading start/end, alerts, end |
| Structured / Semi-structured | `ss` | ✓ | Reading start/end, alerts, end |
| MCQ + Structured | `ss` | ✓ | Reading start/end, alerts, end |
| MCQ only | `mcq` | ✗ | Direct start, alerts, end |
| Reading comprehension | `ss` | ✓ | Reading start/end, alerts, end |
| Listening comprehension | `acq` | ✓ | Reading start/end, end (no 30-min alert) |

---
---

# Minuteur Multi-Examens — Haut-Lac

*Développé par Oceanic Software*

---

## Fichiers

| Fichier | Description |
|---------|-------------|
| `minuteur-multi-examens.html` | Version desktop (fichier unique autonome) |
| `pwa/index.html` | Version PWA pour iPad/iOS (avec icônes et service worker) |
| `pwa/manifest.json` | Manifeste PWA |
| `pwa/service-worker.js` | Service worker pour installation sur iOS |
| `pwa/icons/` | Icônes pour l'écran d'accueil iOS |

---

## Comment utiliser

### Étapes typiques
1. **Réglages** — Configurez le temps de lecture, les alertes, le mode audio et les examens.
2. **Confirmer** — Passe à l'écran des minuteurs.
3. **Démarrer tous** — Lance tous les examens simultanément, ou chaque colonne individuellement.
4. **Pause** — Met en pause / reprend tous les minuteurs.
5. **⚙ pendant l'examen** — Panneau latéral : ajuster les temps, ajouter un examen, changer les réglages vocaux.
6. **Quitter** — Retourne aux réglages sans perdre la configuration.

---

## Fonctions principales

### 📖 Temps de lecture
Période avant l'examen : les candidats lisent le sujet mais n'écrivent pas encore. Durée commune configurable, activable par épreuve. À la fin, le minuteur démarre automatiquement et une annonce vocale est faite (si le mode Voix est activé).

### 🕐 Minuteurs multiples
Chaque carte d'épreuve a ses propres cercles SVG animés :
- **Principal** — toujours actif, durée standard.
- **+25%** et **+50%** — si activés, démarrent en même temps que le Principal et durent proportionnellement plus longtemps. Affichés sous le timer Principal.
- Vous pouvez entrer un **pourcentage** (`25%`), une **proportion décimale** (`0.5` = 50%) ou une **fraction** (`1/3` = tiers-temps).
- Cercles et annonces vocales sont indépendants pour chaque timer.

### ➕ Ajouter un examen
Le bouton **＋ Ajouter un examen** ajoute une nouvelle carte. Pendant que les minuteurs tournent, utilisez ⚙ → **Ajouter un examen** pour ajouter une épreuve sans interrompre les autres. Le sélecteur IB remplit tous les champs automatiquement.

### 🔔 Alertes sonores

**Première alerte** — 30 minutes avant la fin par défaut. Changez la durée ou désactivez. Un repère `−30` s'affiche sur les cercles et se met à jour si vous changez la durée.

**Deuxième alerte** — 5 minutes avant la fin par défaut. Fonctionne comme la première.

En mode **Son** : un bip. En mode **Voix** : une annonce est lue.

### 🖼 Logo
Un logo s'affiche au centre de chaque cercle. Cliquez **Changer** pour télécharger votre image (JPG, PNG, SVG). Le bouton **↺** rétablit le logo original. Le logo personnalisé est mémorisé dans le navigateur.

### 🗣 Mode audio
- **🔇 Silence** — Aucun son, aucune annonce.
- **🔔 Son** — Bips aux alertes et fins d'examen.
- **🗣 Voix** — Annonces vocales automatiques. Des options supplémentaires apparaissent.

### 🌐 Langue des annonces
La langue des annonces (FR/EN) est **indépendante** de la langue de l'interface. Changez-la dans Mode audio → Langue. Vous pouvez aussi choisir une voix spécifique parmi les voix disponibles sur votre appareil.

### 📣 Annonces IB officielles
Lorsque activé, les annonces utilisent les textes officiels du Baccalauréat International. Les textes varient selon le type d'épreuve. Désactivez pour utiliser les annonces personnalisées. Recommandé pour les examens IB officiels.

### ✏️ Personnaliser les annonces
Modifiez le texte de chaque annonce vocale. Six événements personnalisables : début lecture, fin lecture, début examen, alerte 30 min, alerte 5 min, fin examen. Tokens disponibles :
- `{duree}` — durée de l'examen
- `{heure}` — heure actuelle
- `{restant}` — temps restant
- `{lecture}` — durée du temps de lecture

Si plusieurs examens ont des durées différentes, les annonces sont groupées et préfixées du nom de l'épreuve.

### 📋 Programme IB
Le bouton **📋 Programme IB** ouvre un gestionnaire avec le calendrier IB 2027 complet (146 épreuves).

**Filtres** : date (avec calendrier), session (Matin/Après-midi), niveau (NM/NS), recherche textuelle. Cliquer sur un résultat remplit automatiquement le nom, la durée, le type IB et le temps de lecture.

**Gestionnaire** : tableau éditable avec import/export CSV. Fusion intelligente. Multi-sélection pour suppression groupée.

#### 💡 Créer votre propre calendrier avec l'IA
1. Ouvrez **📋 Programme IB** → **↓ Exporter CSV** pour le format de référence.
2. Fournissez ce CSV + votre PDF de calendrier à une IA (Claude, ChatGPT…).
3. Demandez : *"Crée un CSV dans ce format pour les examens de ce calendrier."*
4. Importez avec **↑ Importer CSV**.

Format CSV (colonnes) :
```
date, session, subject_fr, subject_en, level, paper, group_fr, group_en, type_fr, type_en, duration_min, notes_fr, notes_en
```
Exemple : `23/04/2027, Afternoon, Physique, Physics, NS, 1 (1a et 1b), Sciences, Sciences, QCM + Structuré, MCQ + Structured, 120,,`

### ⚙️ Réglages pendant l'examen
Le panneau latéral (bouton ⚙, en haut à droite) permet :
- **Ajuster les temps** : ±1 min / ±10 min par épreuve ou par timer individuel.
- **Ajouter un examen** : avec sélecteur IB intégré.
- **Voix & alertes** : changer le mode audio, la langue, la voix, et les seuils d'alerte.

### 🖥 Plein écran
Adapte automatiquement la taille de tous les éléments à l'écran disponible.

---

## Installation PWA (iPad / iOS)

1. Ouvrez `pwa/index.html` sur un serveur web (GitHub Pages, serveur local, etc.).
2. Dans Safari, tapez **Partager → Sur l'écran d'accueil**.
3. L'application s'installe comme une app native, sans barre de navigation.

---

## Données persistées (localStorage)

| Clé | Contenu |
|-----|---------|
| `hl-prefs` | Préférences : langue, mode audio, alertes, temps de lecture, mode IB |
| `hl-logo` | Logo personnalisé (base64) |
| `hl-ib-rows` | Base de données IB modifiée/importée |
| `hl-templates` | Annonces vocales personnalisées |

---

## Types d'épreuves IB et annonces

| Type | ibType | Temps de lecture | Annonces |
|------|--------|-----------------|----------|
| Non structuré | `ns` | ✓ | Lecture start/end, alertes, fin |
| Structuré / Semi-structuré | `ss` | ✓ | Lecture start/end, alertes, fin |
| QCM + Structuré | `ss` | ✓ | Lecture start/end, alertes, fin |
| QCM seul | `mcq` | ✗ | Début direct, alertes, fin |
| Compréhension écrite | `ss` | ✓ | Lecture start/end, alertes, fin |
| Compréhension orale | `acq` | ✓ | Lecture start/end, fin (pas d'alerte 30 min) |

---

*Pour toute question ou amélioration : Oceanic Software*
