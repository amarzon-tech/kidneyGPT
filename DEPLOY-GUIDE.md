# 🫘 Kidney GPT — GitHub Pages Deployment Guide

## What You're Deploying
A fully self-contained nephrology AI assistant at a URL like:
`https://YOUR-USERNAME.github.io/kidney-gpt/`

---

## STEP 1 — Create a GitHub Account (skip if you have one)
1. Go to **https://github.com** → click **Sign up**
2. Use your email, create a username (e.g. `dr-amar-nephro`)
3. Verify your email

---

## STEP 2 — Create a New Repository
1. Click the **+** button (top right) → **New repository**
2. Set:
   - **Repository name:** `kidney-gpt`
   - **Visibility:** Public ✅ (required for free GitHub Pages)
   - Check **"Add a README file"**
3. Click **Create repository**

---

## STEP 3 — Upload the HTML File
1. In your new repo, click **Add file → Upload files**
2. Upload the file: `kidney-gpt.html`
3. **IMPORTANT:** Rename it to `index.html` before uploading
   - On Mac/Windows, right-click → rename before dragging in
4. Scroll down, add commit message: `Add Kidney GPT app`
5. Click **Commit changes**

---

## STEP 4 — Enable GitHub Pages
1. Go to your repo → click **Settings** tab
2. In the left sidebar, click **Pages**
3. Under **Source**, select **Deploy from a branch**
4. Under **Branch**, select **main** and **/ (root)**
5. Click **Save**

---

## STEP 5 — Wait & Access Your Site
- GitHub takes **1–3 minutes** to build
- Your URL will be: `https://YOUR-USERNAME.github.io/kidney-gpt/`
- You'll see it confirmed in Settings → Pages

---

## STEP 6 — Add the Anthropic API Key (REQUIRED for AI to work)

The app calls the Claude API. You need an API key from Anthropic.

1. Get your key at: **https://console.anthropic.com** → API Keys → Create Key
2. Open `index.html` in any text editor
3. Find **every occurrence** of this line:
   ```
   headers: { 'Content-Type': 'application/json' },
   ```
4. Replace each one with:
   ```javascript
   headers: {
     'Content-Type': 'application/json',
     'x-api-key': 'sk-ant-YOUR-KEY-HERE',
     'anthropic-version': '2023-06-01',
     'anthropic-dangerous-direct-browser-access': 'true'
   },
   ```
5. Save and re-upload to GitHub

**There are 2 fetch calls** in the app (main chat + case template generator) — update both.

⚠️ Keep the repo **Private** if embedding your key, or use a backend proxy (ask me to build one).

---

## Recommended: Keep Repo Private
- Go to Settings → scroll to **Danger Zone** → Change visibility → **Private**
- GitHub Pages still works with private repos on free accounts ✅
- This protects your embedded API key from being publicly visible

---

## Custom Domain (Optional)
To use `kidneyapp.com` or `nephrogpt.com`:
1. Buy domain at Namecheap (~$12/yr)
2. Repo → Settings → Pages → Custom domain → enter your domain
3. At your registrar, add CNAME record: `www` → `YOUR-USERNAME.github.io`

---

## Updating the App
1. Edit `index.html` on your computer
2. Go to your GitHub repo → click `index.html` → pencil (Edit) icon
3. Paste updated content → Commit changes
4. Live in ~1 minute

---

## Quick Reference

| Item | Value |
|------|-------|
| Repo URL | `github.com/YOUR-USERNAME/kidney-gpt` |
| Live URL | `YOUR-USERNAME.github.io/kidney-gpt` |
| Main file | `index.html` |
| Redeploy time | ~1 min |
| Cost | Free |
| API key source | console.anthropic.com |

---

*Built for Dr. Amar · Nephrology Clinical Decision Support · Powered by Claude*
