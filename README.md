# UI Comparison: Bootstrap 5 vs Bulma vs Tailwind CSS (Vanilla HTML)

This mini project contains **three simple UI demo pages** built using:

- **Bootstrap 5**
- **Bulma**
- **Tailwind CSS (CDN)**

Each page includes the same UI structure so you can compare them fairly:

 - Navbar  
 - Cards section  
 - Contact form  

The goal is to compare how the same layout is written using different CSS frameworks — without Next.js, React, or any other frontend framework.

---

## Project Structure

```
/css-framework-comparison
│
├── index.html
├── styles.css
├── bootstrap.html
├── bulma.html
├── tailwind.html
└── README.md
```

---

## Framework Comparison Table

| Category | Bootstrap 5 | Bulma | Tailwind (CDN) |
|---|---|---|---|
| Style approach | Component framework | Component framework | Utility-first |
| Speed to build UI | Very fast | Fast | Fast after learning utilities |
| Default look | “Bootstrap-ish” | Clean/minimal | Depends on your classes |
| Grid/layout | Excellent grid system | Flexbox-based columns | Utilities (flex/grid) |
| Components included | Many + JS behaviors | Many (CSS only) | None (you build them) |
| Interactivity (dropdown, modal) | Built-in JS bundle | You add your own JS | You add your own JS |
| Custom design flexibility | Medium | Medium | High |
| Best for | Prototypes, dashboards, quick UI | Simple clean sites, CSS-only | Custom design systems, modern UI |
| No-build / CDN friendly |  Yes |  Yes |  Yes (with CDN script) |

---

## How to Run the Files

### Option A (Recommended): Just open in browser
These files use CDN links, so you can run them instantly.

1. Download or clone the project folder
2. Open `index.html` in your browser
3. Click the demo you want:
   - Bootstrap
   - Bulma
   - Tailwind

---

### Option B: Run with a local server (better for development)

#### Option 1: VS Code Live Server
1. Open the folder in **Visual Studio Code**
2. Install the extension: **Live Server**
3. Right-click `index.html`
4. Click: **Open with Live Server**

---

## What Each File Contains

### `bootstrap.html`
- Uses Bootstrap 5 via CDN
- Includes Bootstrap’s built-in JS bundle for navbar collapse
- Best example of a “ready-to-use” component framework

### `bulma.html`
- Uses Bulma via CDN
- Bulma is CSS-only, so a small JavaScript snippet is included for mobile navbar toggle
- Very clean, minimal styling by default

### `tailwind.html`
- Uses Tailwind CSS via CDN
- Tailwind provides utilities (not ready-made components)
- The UI is built using utility classes like `flex`, `grid`, `rounded-xl`, etc.
- Includes a small JavaScript snippet for mobile navbar toggle

---

## Notes
- All pages are responsive
- No installation needed
- No build step required
- Works offline only if you download the framework files locally (currently uses CDN)

---

## License
Free to use for learning and educational purposes.
