# DevFolio — Developer Portfolio Template

A clean, fully-featured personal portfolio template built with **vanilla HTML, CSS, and JavaScript**. No frameworks, no build tools, no dependencies to install. Just clone and fill in your details.

**Live demo:** [alex-johnson-demo.github.io/devfolio](https://github.com) *(replace with your own link)*

---

## Features

- **Admin Panel** — browser-based CMS to edit all content without touching code
- **One-click publish** to GitHub Pages via the GitHub REST API
- **Maintenance mode** — take the site offline while you make changes
- **Dark / light theme** toggle
- **Animated hero** with typewriter role cycling
- **Stats bar** that auto-adjusts columns to match the number of items
- **Certificate gallery** with image upload support
- **Responsive** — mobile-first, works on all screen sizes
- **Zero server required** — works as static files on any host

---

## Quick Start

### 1 — Clone or download

```bash
git clone https://github.com/your-username/devfolio.git my-portfolio
cd my-portfolio
```

Or click **Use this template** on GitHub to create your own repo instantly.

### 2 — Open locally

Double-click `index.html`, or serve with any static file server:

```bash
# Python
python -m http.server 8080

# Node.js (npx)
npx serve .
```

> **Note:** When opened via `file://` the site uses built-in demo data so you can see it working right away. To load your own data from `content/data.json`, serve it over HTTP (even `localhost` is fine).

### 3 — Fill in your details (Admin Panel)

Open `admin/index.html` in your browser.

Fill in each section:

| Section | What to fill in |
|---|---|
| Personal Info | Name, title, bio, email, photo, LinkedIn, GitHub, CV URL |
| Stats Bar | Key numbers (years of experience, projects, etc.) |
| Skills | Categories and skill levels |
| Work Experience | Jobs with responsibilities and tech stack |
| Education | Degrees and institutions |
| Projects | Portfolio projects with descriptions and links |
| Certificates | Certifications with images |
| Contact | Email, address, availability message |
| SEO & Site Settings | Page title, description, keywords |
| GitHub Settings | Your GitHub username and repo name (for publishing) |

Click **Save Draft** to preview changes in `index.html` instantly.

### 4 — Publish to GitHub Pages

1. Go to the **GitHub Settings** section in the Admin Panel
2. Enter your GitHub username, repository name, and a [Personal Access Token](https://github.com/settings/tokens/new) with `repo` scope
3. Click **Publish to GitHub** — this commits `content/data.json` (and any uploaded images) directly to your repo
4. Enable GitHub Pages in your repo settings → **Pages** → Source: `main` / `/(root)`

Your portfolio will be live at `https://your-username.github.io/your-repo-name/`

---

## File Structure

```
portfolio/
├── index.html              # Main portfolio page
├── experience.html         # Full experience & education page
├── projects.html           # Full projects gallery page
├── content/
│   └── data.json           # All your portfolio data lives here
├── css/
│   └── style.css           # All styles
├── js/
│   └── main.js             # Rendering logic, animations, interactions
├── images/
│   ├── profile.jpg         # Your profile photo (optional)
│   ├── projects/           # Project screenshots
│   └── certificates/       # Certificate images
└── admin/
    ├── index.html          # Admin panel (CMS)
    └── login.html          # Admin login page
```

---

## Customising Content

### Option A — Admin Panel (recommended)
Use `admin/index.html`. Changes are saved to `localStorage` as a draft, then published to GitHub.

### Option B — Edit data.json directly
Open `content/data.json` and edit the fields. The structure is self-explanatory.

Key fields:

```json
{
  "personal": {
    "name": "Your Name",
    "title": "Your Job Title",
    "roles": ["Role 1", "Role 2"],
    "bio": "Your bio...",
    "email": "you@example.com",
    "linkedin": "https://linkedin.com/in/your-profile",
    "github": "https://github.com/your-username",
    "cvUrl": "https://link-to-your-cv.com",
    "expSummary": "X+ Years in Your Field",
    "availability": "Open to Opportunities"
  },
  "meta": {
    "siteTitle": "Your Name — Your Title",
    "githubOwner": "your-github-username",
    "githubRepo": "your-repo-name",
    "siteUrl": "https://your-github-username.github.io/your-repo-name/"
  }
}
```

### Profile photo
Drop your photo as `images/profile.jpg` (or any path) and set `personal.profileImage` to that path in `data.json`.

---

## Admin Panel Security

The Admin Panel is protected by a password stored in `localStorage`. On first use:

1. Open `admin/login.html`
2. Set your password
3. Log in

The token used for GitHub publishing is **only stored in your browser's `sessionStorage`** and is never committed to the repo.

> The admin folder is public in the repo. Anyone can open the login page, but they cannot publish without a valid GitHub token for *your* account.

---

## Deployment Options

| Platform | Steps |
|---|---|
| **GitHub Pages** | Use the built-in publish button in the Admin Panel |
| **Netlify / Vercel** | Drag-and-drop the folder, or connect your GitHub repo |
| **Any web host** | Upload all files via FTP / file manager |

---

## Data Flow

```
Admin Panel  →  Save Draft  →  localStorage (instant preview)
Admin Panel  →  Publish     →  GitHub REST API  →  content/data.json in repo
index.html   →  fetch()     →  content/data.json  →  renders portfolio
index.html   →  (offline)   →  localStorage draft OR built-in demo data
```

---

## Tech Stack

- Pure HTML5, CSS3, JavaScript (ES2020+)
- [Font Awesome 6](https://fontawesome.com) for icons
- [Google Fonts](https://fonts.google.com) (Inter, JetBrains Mono, Space Grotesk)
- GitHub REST API for one-click publishing

---

## License

MIT — free to use for personal and commercial projects. Attribution appreciated but not required.
