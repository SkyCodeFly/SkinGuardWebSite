# DermaScan — Eczema Severity Analyzer

A static web app that analyzes eczema severity from skin images using the Claude Vision API.
Deployable to GitHub Pages in under 2 minutes — no server, no backend, no build step.

---

## Live Demo

After deployment your URL will be:
```
https://<your-github-username>.github.io/<repo-name>/
```

---

## Deploy to GitHub Pages (Step-by-Step)

### Step 1 — Create a new GitHub repository

1. Go to https://github.com/new
2. Repository name: `dermascan` (or any name you like)
3. Set to **Public**
4. Click **Create repository**

### Step 2 — Upload the file

Option A — via GitHub web UI (easiest):
1. Open your new repo
2. Click **"Add file" → "Upload files"**
3. Drag `index.html` into the upload area
4. Click **"Commit changes"**

Option B — via command line:
```bash
git init
git add index.html
git commit -m "Initial commit"
git branch -M main
git remote add origin https://github.com/<you>/<repo>.git
git push -u origin main
```

### Step 3 — Enable GitHub Pages

1. Go to your repo **Settings → Pages**
2. Under **Source**, select `Deploy from a branch`
3. Branch: `main`, folder: `/ (root)`
4. Click **Save**
5. Wait ~60 seconds, then visit your URL

---

## How to Use the App

1. Open the deployed URL in any browser
2. Enter your **Anthropic API key** (`sk-ant-api03-...`)
   - Get one free at https://console.anthropic.com
   - The key is used only in your browser — never stored or transmitted to any server
3. Upload a skin image (JPG / PNG / WEBP, max 10 MB)
4. Click **Analyze Image**
5. View the results:
   - Severity group (Minimal / Mild / Moderate / Severe / Extreme)
   - EASI-based score (0–20)
   - Confidence level
   - Per-class probability distribution bars
   - Key morphological features
   - Clinical recommendation
   - Differential diagnosis note

---

## What the App Does

- Sends the image directly to the Claude API (`claude-opus-4-6`) from your browser
- Uses a clinical system prompt based on the simplified EASI scale
- Parses structured JSON output from Claude
- Renders an interactive results dashboard

---

## Privacy

- Images are sent directly from your browser to the Anthropic API
- Nothing is stored on any server or database
- Your API key is held in memory only, never persisted

---

## Disclaimer

This tool is for **research and educational purposes only**.
It does not constitute medical advice.
Always consult a qualified dermatologist for diagnosis and treatment.

---

## Repository Structure

```
dermascan/
└── index.html    # Complete single-file web app (HTML + CSS + JS)
```

No dependencies, no build tools, no npm — just one HTML file.
