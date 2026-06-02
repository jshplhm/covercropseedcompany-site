# Cover Crop Seed Co. — Website

Static website for [covercropseedcompany.com](https://www.covercropseedcompany.com), hosted free on GitHub Pages.

## Stack

- Plain HTML + CSS + vanilla JS — no build step, no dependencies, no framework
- One file: `index.html`
- Hosted on GitHub Pages (free)
- Contact form via [Formspree](https://formspree.io) (free tier, 50 submissions/month)

---

## Local development

Just open the file in a browser — no server needed:

```bash
open index.html
```

Or drag `index.html` into Chrome/Safari. All changes are visible immediately on save + refresh.

---

## Deploying changes

1. Edit `index.html` locally
2. Open **GitHub Desktop** → you'll see the changed file
3. Write a short commit message (e.g. "Update contact info") → **Commit to main**
4. Click **Push origin**
5. Changes are live at `www.covercropseedcompany.com` within ~60 seconds

---

## Swapping images

All three images are currently loaded from the old Squarespace CDN. Replace them with your own files when ready.

| Location in HTML | What it is | Recommended size |
|---|---|---|
| Hero `<img>` (first one) | Full-bleed background photo | 2400×1600px, JPG, <500 KB |
| About `<img>` (second one) | Portrait-orientation field/team photo | 900×1125px, JPG |
| Management `<img>` (third one) | Landscape field/planning photo | 1200×750px, JPG |

**Steps:**
1. Compress each photo at [squoosh.app](https://squoosh.app) before adding (keeps the site fast)
2. Drop the files into this repo folder (e.g. `images/hero.jpg`)
3. Update the `src=""` attribute in `index.html` to match (e.g. `src="images/hero.jpg"`)
4. Commit and push

---

## Setting up the contact form

The form uses [Formspree](https://formspree.io) — free, no server required.

1. Go to [formspree.io](https://formspree.io) and create a free account
2. Click **New Form** → give it a name → copy the **Form ID** (looks like `xkgnwpqz`)
3. In `index.html`, find this line:
   ```html
   action="https://formspree.io/f/YOUR_FORM_ID"
   ```
4. Replace `YOUR_FORM_ID` with your actual ID
5. Commit and push — forms will now land in your email inbox

---

## Custom domain setup

To point `www.covercropseedcompany.com` at this GitHub Pages site:

### In GitHub (one time)
1. Go to your repo → **Settings** → **Pages**
2. Source: **Deploy from a branch**, branch: `main`, folder: `/ (root)`
3. Under "Custom domain", enter: `www.covercropseedcompany.com`
4. Check **Enforce HTTPS** (available after DNS propagates)

### In your DNS registrar (one time)
Add a `CNAME` record:

| Type | Name | Value |
|------|------|-------|
| CNAME | `www` | `yourusername.github.io` |

DNS propagation takes 5–30 minutes. After that, the site is live at your domain with a free SSL certificate.

---

## File structure

```
covercropseedcompany.com/
├── index.html       ← the entire site
├── README.md        ← this file
└── images/          ← add your own photos here (create folder when ready)
```

---

## Content updates

Everything lives in `index.html`. Common edits:

- **Change text** → find it with Cmd+F, edit inline
- **Change phone/email** → search for `831` or `covercropseed`
- **Change address** → search for `Colfax`
- **Add a new section** → copy an existing `<section>` block and edit
