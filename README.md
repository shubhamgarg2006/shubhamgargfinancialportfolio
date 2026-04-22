# Time in the Market

A professional static portfolio site for original equity research, hosted on GitHub Pages.

---

## 📁 Folder Structure

```
/
├── index.html                    ← Main landing page (edit this to add company cards)
├── styles.css                    ← Shared styles — do not rename
├── README.md                     ← This file
└── companies/
    ├── company-template/         ← TEMPLATE — copy this for each new company
    │   └── index.html
    ├── apple/                    ← Example company folder
    │   ├── index.html
    │   ├── industry-report.pdf
    │   ├── one-pager.pdf
    │   ├── dcf-model.pdf
    │   └── presentation.pptx
    └── [your-company]/
        ├── index.html
        └── [your files...]
```

---

## ➕ Adding a New Company

### Step 1 — Create the company folder

Copy the `companies/company-template/` folder and rename it to the company's ticker or short name (lowercase, no spaces):

```
cp -r companies/company-template companies/msft
```

### Step 2 — Add your files

Drop your PDFs and PPTX files into the new folder:

```
companies/msft/
├── index.html
├── industry-report.pdf
├── one-pager.pdf
├── dcf-model.pdf
└── presentation.pptx
```

### Step 3 — Edit the company page

Open `companies/msft/index.html` and find every line marked with `✏️  EDIT:`. Update:

| Field | Where |
|---|---|
| `<title>` | Page tab title |
| Breadcrumb text | `company-breadcrumb` div |
| Ticker + sector | `card-ticker` + `card-sector` spans |
| Company name | `company-page-title` h1 |
| Company summary | `company-summary` paragraph |
| Key stats | `stats-bar` — update values, add/remove `stat-item` blocks |
| Investment thesis | `thesis-block` paragraph |
| Document descriptions | Each `doc-card-desc` div |
| Document `href` links | Each `doc-card-link` anchor |

### Step 4 — Add the card to the landing page

Open `index.html` and find the comment block:

```html
<!-- COMPANY CARD — Duplicate this block to add a new company -->
```

Copy the entire `<article class="company-card">` block and update:

- `card-ticker` → e.g. `MSFT`
- `card-sector` → e.g. `Technology · Cloud & Software`
- `card-company` → e.g. `Microsoft Corp.`
- `card-thesis` → one-sentence thesis
- All `href` links → point to `companies/msft/` files
- The "View Full Coverage" link → `companies/msft/index.html`

---

## 🚀 Deploying to GitHub Pages

1. Push the whole project to a GitHub repository (e.g. `your-username/research-portfolio`)
2. Go to **Settings → Pages**
3. Under **Source**, select `main` branch and `/ (root)`
4. Click **Save** — your site will be live at `https://your-username.github.io/research-portfolio/`

> **Tip:** Every time you push new files or edits to GitHub, the site auto-updates within ~1 minute.

---

## ✏️ Personalizing the Site

| What to change | Where |
|---|---|
| Your name / initials in "TITM" logo | `index.html` and `company-template/index.html` — search for `TITM` |
| Contact email | `index.html` → `contact-section` → `href="mailto:..."` |
| About text | `index.html` → `about-body` paragraphs |
| Color accent (gold) | `styles.css` → `--gold` and `--gold-light` variables |
| Font choices | `styles.css` → `--font-display`, `--font-mono`, `--font-sans` |

---

## ⚠️ Disclaimer

All content on this site is for **educational and informational purposes only** and does not constitute financial advice, investment recommendations, or solicitation of any kind.
