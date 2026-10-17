# 🍳 Cooking Journal

<div align="center">

![Cooking Journal — Good Food, Better Days](images/Cooking%20Journal_%20Good%20Food%2C%20Better%20Days.png?v=20261016)

**Good Food, Better Days.**

*A simple place to collect favorite meals, remember what worked, and build your own recipe collection.*

[🌐 Open Cooking Journal](https://romellbermundo.github.io/cookingjournal/) · [📦 Source Code](https://github.com/romellbermundo/cookingjournal)

</div>

---

## 📑 Table of Contents

- [About Cooking Journal](#-about-cooking-journal)
- [How It Works](#-how-it-works)
- [Key Features](#-key-features)
- [Recipe Photos](#-recipe-photos)
- [Getting Started](#-getting-started)
- [Saving and Backing Up Recipes](#-saving-and-backing-up-recipes)
- [Project Structure](#-project-structure)
- [Image Upload Automation](#-image-upload-automation)
- [Technology](#-technology)
- [Privacy and Limitations](#-privacy-and-limitations)
- [Credits](#-credits)
- [Version History](#-version-history)

---

## 📖 About Cooking Journal

**Cooking Journal** is a lightweight, mobile-first personal recipe collection. Save dishes you enjoy, record ingredients and instructions, and find recipes again without a complicated account or subscription.

It runs as a static website, so there is **no backend, database server, API key, or sign-in requirement**.

The app includes five starter recipe references to inspire your next meal. You can also create and manage your own entries.

---

## 🔄 How It Works

```text
OPEN COOKING JOURNAL
          │
          ▼
BROWSE OR SEARCH RECIPES
          │
          ├────────► EXPLORE STARTER RECIPES
          │
          ▼
ADD OR EDIT YOUR OWN RECIPE
          │
          ├────────► ADD A FOOD PHOTO
          │
          ▼
SAVE IN THIS BROWSER
          │
          ▼
EXPORT A JSON BACKUP
          │
          ▼
IMPORT ON ANOTHER BROWSER / DEVICE
```

Your own recipe data lives in your browser. The website files and starter images are hosted on GitHub Pages.

---

## ✨ Key Features

### 🔎 Find a Recipe

Browse your collection and search for the dish you want to make.

### 📝 Build Your Cookbook

Add, edit, and delete your own recipes. Record details that will help you cook the dish again.

### 📸 Keep Food Photos

Attach a photo to a recipe. The app compresses uploaded photos for browser storage, and includes them when exporting your recipe data.

### 🍽️ Explore Starter Ideas

Five starter references are provided:

- 🥑 Loaded Guacamole
- 🍗 Grilled Wings
- 🥪 Hot Chicken Sandwich
- 🍲 Taco Soup
- 🥩 Filet Mignon

These reference dishes link back to the original source article; the complete copyrighted recipes are not reproduced here.

### 📦 Take Your Recipes With You

Export your saved recipes as JSON, then import the backup in another browser or after changing devices.

### 📱 Made for Mobile

The responsive interface is designed to work on phones and desktop browsers. A web app manifest supports an install-like experience where the browser permits it.

---

## 🖼️ Recipe Photos

Starter recipe images live in the `images/` directory. User-added recipe photos are stored with recipe data in the browser, not uploaded to GitHub.

The README banner is also stored in `images/` and displayed above the project introduction.

---

## 🚀 Getting Started

### Option A — Use the live app

Open **[Cooking Journal](https://romellbermundo.github.io/cookingjournal/)** and start exploring.

### Option B — Run it locally

Clone the repository:

```bash
git clone https://github.com/romellbermundo/cookingjournal.git
cd cookingjournal
```

Open `index.html` in a modern browser. For a local web server, you can also use:

```bash
python -m http.server 8000
```

Then visit `http://localhost:8000`.

No dependency installation or API credentials are required.

---

## 💾 Saving and Backing Up Recipes

Cooking Journal uses **browser localStorage** for personal recipe data.

1. Add or edit recipes in the app.
2. Use the app's JSON export feature to save a backup file.
3. Keep that backup somewhere you control.
4. Use JSON import when you want to restore or transfer your recipes.

**Important:** Recipes do not automatically sync across phones, computers, browsers, or browser profiles. Export your data before clearing site data or changing devices.

---

## 🏗️ Project Structure

```text
cookingjournal/
├── index.html
├── manifest.webmanifest
├── README.md
├── images/
│   ├── Cooking Journal_ Good Food, Better Days.png
│   ├── loaded-guacamole.webp
│   ├── grilled-wings.webp
│   ├── hot-chicken-sandwich.webp
│   ├── taco-soup.webp
│   └── filet-mignon.webp
└── .github/
    └── workflows/
        └── import-recipe-photos.yml
```

The app is intentionally small: HTML, CSS, and JavaScript work together without a frontend framework or separate application server.

---

## 🤖 Image Upload Automation

GitHub Actions automatically organizes new image files committed to the **repository root**.

### Upload an individual image

1. Open the repository on GitHub.
2. Select **Add file → Upload files**.
3. Drop a PNG, JPG, JPEG, or WebP file into the root of the repository.
4. Commit the upload.

The workflow moves the file into `images/` and commits the organized result.

### Upload a ZIP of images

1. Name the ZIP **`recipe-photos.zip`**.
2. Upload it to the repository root.
3. Commit the upload.

GitHub Actions extracts the supported images into `images/` and removes the ZIP.

**Current safeguards:** Each imported image is limited to 10 MB, and ZIP imports accept 1–100 supported image files. Images with matching names may replace existing images, so choose filenames carefully.

Check progress under the repository's **Actions** tab. GitHub Pages deployment can take a few additional moments.

> **Note:** Adding a new image to the repository does not automatically insert it into the README or create a new recipe. Those are separate content changes.

---

## 🛠️ Technology

| Layer | Technology |
|---|---|
| Interface | HTML, CSS, JavaScript |
| Recipe persistence | Browser localStorage |
| Backup and restore | JSON import/export |
| Hosting | GitHub Pages |
| Image organization | GitHub Actions, Python |
| Version control | Git and GitHub |

---

## 🔒 Privacy and Limitations

- **No accounts or automatic cloud sync.** Personal recipes stay in the browser where they were entered.
- **No shared recipe database.** Adding a recipe does not publish it for other visitors.
- **Storage is limited.** Large numbers of photos may fill browser localStorage.
- **Clearing browser data can erase recipes.** Keep regular JSON backups.
- **Not secure storage.** Do not use the journal to store confidential or sensitive information.

---

## 🙏 Credits

The starter recipe ideas reference Matt Moore's article, **[5 Awesome Recipes for the Man's-Man](https://www.artofmanliness.com/culture/food-drink/5-awesome-recipes-for-the-mans-man/)**, published by *The Art of Manliness*. Original full recipe instructions are not reproduced.

Project development and maintenance: **Romell Bermundo**.

---

## 🏷️ Version History

### v1.1.0 — Documentation and image workflow

- Adopted a detailed, icon-led README structure with a navigation table of contents.
- Added the Cooking Journal banner to the README.
- Documented automated organization of root-level images and ZIP imports.
- Expanded setup, backup, privacy, and technical guidance.

### v1.0.0 — Initial Cooking Journal

- Released the mobile-first recipe journal.
- Added starter recipe references, personal recipe management, and search.
- Added local browser storage, photo attachments, and JSON import/export.
- Published as a static GitHub Pages application.
