# Zandi Virology Lab — Website

Static website for Dr. Keivan Zandi's Virology Lab at Morehouse School of Medicine.
Built as plain HTML + CSS so anyone on the team can edit text without needing
to know how to code.

---

## Quick look

Four pages, navigation at the top of every page:

| Page | File | What's on it |
| --- | --- | --- |
| Home | `index.html` | Logo + lab name (landing page) |
| About | `about.html` | Lab synopsis, research focus, projects |
| Team | `team.html` | Dr. Zandi + all lab members |
| Contact | `contact.html` | Lab address, email, phone, and Google Form |

---

## Getting it online (first-time setup)

**One-time setup — takes about 10 minutes.**

1. Create a free GitHub account at [github.com](https://github.com) if you don't have one.
2. Create a new **public** repository. Name it whatever you want — e.g. `zandi-lab`.
3. Upload every file in this folder to the repository:
   - On your new repo page, click **Add file → Upload files**.
   - Drag the entire contents of the `zandi-lab` folder (not the folder itself —
     the files and sub-folders *inside* it) onto the page.
   - Click **Commit changes**.
4. Turn on GitHub Pages:
   - In the repository, go to **Settings → Pages** (left sidebar).
   - Under **Source**, pick **Deploy from a branch**.
   - Branch: `main`, folder: `/ (root)`. Click **Save**.
5. Wait 1–2 minutes. The site will be live at:

   ```
   https://YOUR-USERNAME.github.io/zandi-lab/
   ```

   (Replace `YOUR-USERNAME` with your GitHub username and `zandi-lab` with
   whatever you named the repo.)

**Custom domain later:** when you buy a domain, add it under
**Settings → Pages → Custom domain** and follow GitHub's DNS instructions.

---

## How to edit text (for lab members)

You do **not** need to install anything. GitHub lets you edit files directly
in the browser.

1. Go to the repository on GitHub.
2. Click the file you want to edit (e.g. `team.html`).
3. Click the pencil icon (✏️) in the top-right of the file view.
4. Change the text. Look for lines that start with `<!-- EDIT:` — those are
   comments telling you exactly what to replace.
5. Scroll to the bottom, write a short note in the commit message
   (e.g. *"Update Dr. Zandi's bio"*), and click **Commit changes**.
6. The site updates automatically in ~1 minute.

### What text lives where

| Want to change… | Edit this file | Look for… |
| --- | --- | --- |
| Lab name / tagline on homepage | `index.html` | Search for `hero-content` |
| Lab synopsis, research overview | `about.html` | Search for `Research overview` |
| Project / research area cards | `about.html` | Search for `project-card` |
| Dr. Zandi's bio | `team.html` | Search for `Principal Investigator` |
| Lab members | `team.html` | Search for `member-card` |
| Email, phone, mailing address | `contact.html` | Search for `contact-info` |
| Google Form embed | `contact.html` | Search for `HOW TO ADD YOUR GOOGLE FORM` |

### Adding a new team member

In `team.html`, find the `team-grid` section. Each member is a block that looks
like this:

```html
<article class="member-card">
  <div class="member-photo"><span>AB</span></div>
  <h3 class="member-name">Member Name</h3>
  <span class="member-role">Postdoctoral Fellow</span>
  <p class="member-bio">
    One to two sentences about their background and research interests.
  </p>
</article>
```

Copy that entire block, paste it in, and change the initials (`AB`), name,
role, and bio.

### Using a real photo instead of initials

Put a square photo (JPG or PNG) in the `assets/` folder — e.g. `assets/jane.jpg`.
Then replace the `<div class="member-photo">…</div>` line with:

```html
<img class="member-photo" src="assets/jane.jpg" alt="Jane Doe" />
```

The photo will automatically be cropped to a circle with the existing styling.

### Replacing the logo

When you have a real logo:
1. Save it as `logo.svg` (preferred) or `logo.png`.
2. Upload it to the `assets/` folder, replacing the placeholder.
3. That's it — every page will pick up the new logo.

### Adding the Google Form

1. Open your Google Form in a browser.
2. Click **Send** (top-right) → click the `<>` embed icon.
3. Copy the `<iframe ...>` tag Google gives you.
4. Open `contact.html`, find the comment that says
   *"HOW TO ADD YOUR GOOGLE FORM"*, and follow the instructions there.

---

## File structure

```
zandi-lab/
├── index.html         Home page
├── about.html         About page
├── team.html          Team page
├── contact.html       Contact page
├── css/
│   └── styles.css     All styling (edit only if changing look/colors)
├── assets/
│   └── logo.svg       Placeholder lab logo
├── .nojekyll          GitHub Pages config (do not delete)
└── README.md          This file
```

---

## Design notes (for reference)

- **Colors** are drawn from the official MSM Brand Identity Style Guide:
  MSM Blue (`#3C4F85`) as primary, a warm gold accent, and a cream background.
- **Fonts** are Instrument Serif (headings) + IBM Plex Sans (body), loaded
  from Google Fonts — nothing to install.
- The placeholder **logo** is a stylized virus particle with a "Z" monogram.
  Replace it with your official lab logo when available.
- The site is fully **responsive** — looks good on phones, tablets, and
  desktop.

If you want to change colors or fonts across the entire site, open
`css/styles.css` and look at the very top under `DESIGN TOKENS`. Every color
and font is set there exactly once.

---

## Questions?

If something breaks or you're not sure how to edit, ask whoever set this up
originally, or ping someone comfortable with HTML — everything on this site
is plain files, so it's easy to fix.
