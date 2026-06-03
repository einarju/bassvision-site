# BassVision — Portfolio Site

Single-page portfolio for BassVision AI Visual Production Studio.  
Built with pure HTML, CSS, and JavaScript. Zero dependencies. GitHub Pages ready.

---

## Folder structure

```
bassvision-site/
├── index.html          ← Everything lives here
├── README.md
└── assets/
    ├── hero.mp4        ← Hero background video (replace)
    ├── hero-poster.jpg ← First frame / fallback image for video
    ├── work1.jpg       ← Jellyfish Dance thumbnail
    ├── work2.jpg       ← Dark Techno Loops thumbnail
    └── work3.jpg       ← Octopus Visuals thumbnail
```

---

## 1. Replace placeholder assets

### Hero video
- Drop your video file into `assets/` and name it `hero.mp4`
- Recommended: H.264 MP4, 1920×1080, under 10 MB for fast load
- Also add a `hero-poster.jpg` (screenshot of the first frame) — shown while video loads on mobile

### Work thumbnails
- Add `assets/work1.jpg`, `work2.jpg`, `work3.jpg`
- Recommended size: 1280×720 (16:9 ratio), JPG compressed to ~150KB

---

## 2. Replace placeholder links

Open `index.html` and search for these two strings:

| Placeholder | Replace with |
|---|---|
| `[YOUR_GUMROAD_LINK]` | Your $9.50 Gumroad product URL |
| `[PLACEHOLDER]` in the form action | Your Formspree endpoint (see section 3) |

---

## 3. Set up Formspree (contact form)

1. Go to [formspree.io](https://formspree.io) and create a free account
2. Create a new form — set the destination to your email address
3. Copy your endpoint — it looks like `https://formspree.io/f/xabcdefg`
4. In `index.html` find:
   ```html
   action="https://formspree.io/f/[PLACEHOLDER]"
   ```
   Replace `[PLACEHOLDER]` with your unique ID (e.g. `xabcdefg`)

The free Formspree tier allows 50 submissions/month. Enough to start.

---

## 4. Deploy to GitHub Pages

### First time
```bash
# Inside the bassvision-site folder
git init
git add .
git commit -m "Initial commit"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/YOUR_REPO.git
git push -u origin main
```

Then in GitHub: **Settings → Pages → Source → Deploy from branch → main → / (root) → Save**

Your site will be live at `https://YOUR_USERNAME.github.io/YOUR_REPO/` in ~60 seconds.

### Connect a custom domain (bassvision.store)

1. In GitHub: **Settings → Pages → Custom domain** → type `bassvision.store` → Save
2. GitHub will create a `CNAME` file automatically
3. At your domain registrar (wherever you bought `bassvision.store`), add these DNS records:

   **For apex domain (bassvision.store):**
   ```
   A    @    185.199.108.153
   A    @    185.199.109.153
   A    @    185.199.110.153
   A    @    185.199.111.153
   ```

   **For www subdomain:**
   ```
   CNAME    www    YOUR_USERNAME.github.io
   ```

4. Check **Enforce HTTPS** in GitHub Pages settings (available after DNS propagates — up to 24h)

---

## 5. Updates after going live

Any `git push` to `main` automatically redeploys the site via GitHub Pages.

```bash
git add .
git commit -m "Update work thumbnails"
git push
```
