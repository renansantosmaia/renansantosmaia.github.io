# Renan Santos Maia — Personal Website

Bold editorial portfolio website with Decap CMS for browser-based content management.

---

## File Structure

```
renan-site/
├── index.html              ← English homepage (all sections)
├── pt/
│   └── index.html          ← Portuguese page (translate text nodes)
├── admin/
│   ├── index.html          ← Decap CMS admin panel
│   └── config.yml          ← CMS field definitions (edit to add fields)
├── _data/
│   ├── profile.json        ← Name, bio, contact, social links
│   ├── experience.json     ← Industry work experience
│   ├── research.json       ← Research projects
│   ├── teaching.json       ← Teaching roles
│   ├── publications.json   ← Journal publications
│   └── conferences.json    ← Conference presentations and posters
└── assets/
    └── images/             ← Upload images here (or via Admin)
```

---

## Deployment — GitHub Pages + Decap CMS (Free)

### Step 1 — Create GitHub repository
1. Go to github.com → New repository
2. Name it `YOUR_USERNAME.github.io` (for root domain) or any name (for subpath)
3. Set to **Public**
4. Upload all files from this folder

### Step 2 — Enable GitHub Pages
1. Repository → Settings → Pages
2. Source: Deploy from branch → `main` → `/ (root)`
3. Save. Your site is live at `https://YOUR_USERNAME.github.io`

### Step 3 — Enable GitHub OAuth for CMS
1. Go to github.com → Settings → Developer Settings → OAuth Apps → New OAuth App
2. Fill in:
   - Application name: `Renan Portfolio CMS`
   - Homepage URL: `https://YOUR_USERNAME.github.io`
   - Authorization callback URL: `https://YOUR_USERNAME.github.io/admin/`
3. Copy the **Client ID**

### Step 4 — Update admin/config.yml
Open `admin/config.yml` and replace:
```yaml
backend:
  name: github
  repo: YOUR_GITHUB_USERNAME/YOUR_REPO_NAME   ← replace this
  branch: main
```

### Step 5 — Access the admin panel
1. Go to `https://YOUR_USERNAME.github.io/admin/`
2. Log in with GitHub
3. Edit all content sections through the browser UI
4. Click **Publish** — changes go live automatically

---

## Updating Content (after setup)

### Via Admin Panel (recommended — no code)
- Go to `/admin/`
- Edit any section: Profile, Experience, Research, Teaching, Conferences, Publications
- Upload poster/slide images directly via the file uploader
- Publish changes

### Via JSON files (direct edit)
Edit files in `_data/` directly in GitHub's web editor or any text editor.
All content is plain JSON — structure is documented inline.

---

## Customization

### Change accent color
In `index.html`, find `:root` CSS block, change:
```css
--accent: #C8102E;   /* → any hex color */
```

### Add your real social links
In `_data/profile.json`, replace:
- `"linkedin": "https://linkedin.com/in/YOUR_HANDLE"`
- `"scholar": "https://scholar.google.com/YOUR_PROFILE"`
- `"researchgate": "https://researchgate.net/profile/YOUR_PROFILE"`

Also update the same links in `index.html` hero section and contact section.

### Add conference presentations
1. Go to `/admin/` → Conferences & Presentations → New
2. Fill in: title, event, year, type, description
3. Upload poster preview image and/or PDF file
4. Publish

### Complete the Portuguese page
Open `pt/index.html` — the structure mirrors the English page.
Replace all English text nodes with Portuguese translations.
The pullquote and contact section are already translated.

---

## Custom Domain (optional)

1. Buy a domain (e.g., `renanmaia.com`)
2. In your domain registrar: add CNAME record pointing to `YOUR_USERNAME.github.io`
3. In GitHub Pages settings: add custom domain
4. Enable "Enforce HTTPS"

---

## Notes

- The site is fully static — no server, no database, no monthly cost
- Admin panel uses GitHub OAuth — your GitHub account is the authentication
- Images uploaded via Admin go to `assets/images/` in your repository
- The Portuguese page (`pt/index.html`) is scaffolded — fill in translations section by section
