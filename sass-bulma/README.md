# Sass + Bulma Dashboard

This project takes your `bulma.html` dashboard (navbar + cards + form) and compiles Bulma + your custom styles via Sass.

## Install
```bash
npm install
```

## Run (watch Sass + serve)
```bash
npm run dev
```

Open:
- http://127.0.0.1:5173

## Build CSS once
```bash
npm run build:css
```

## Sass structure
- `scss/_tokens.scss` → variables (colors, radius, shadows, font)
- `scss/_mixins.scss` → mixins (card, pill)
- `scss/_base.scss` → global styles
- `scss/components/_cards.scss` → card overrides to match your screenshot
- `scss/components/_forms.scss` → input/button rounding

----

# Bulma + Sass – Demo

## Goal
Understand:
- What Bulma (CSS framework) does
- What Sass does
- How to customize Bulma using Sass variables

---

# Part 1 – CDN Version (Fast & Simple)

## Step 1: Create `index.html`

```html
<!DOCTYPE html>
<html>
<head>
  <meta charset="UTF-8">
  <title>Bulma Demo</title>
  <link rel="stylesheet"
        href="https://cdn.jsdelivr.net/npm/bulma@1.0.2/css/bulma.min.css">
</head>
<body>
  <section class="section">
    <div class="container">
      <h1 class="title">Hello Bulma</h1>
      <button class="button is-primary">Click me</button>
    </div>
  </section>
</body>
</html>
```

### Question for students:
Where does the button color come from?

Answer: From Bulma's default theme.

---

# Part 2 – Switch to Sass Version

## Step 2: Initialize project

```bash
npm init -y
npm install -D sass bulma
```

Create folders:

```
scss/main.scss
css/main.css
```

---

## Step 3: Add build script to `package.json`

```json
"scripts": {
  "build:css": "sass --load-path=node_modules scss/main.scss css/main.css"
}
```

Run:

```bash
npm run build:css
```

---

# Part 3 – Add Sass Theme Override

## Step 4: Edit `scss/main.scss`

```scss
$primary: #41c7a2;

@use "bulma/sass" with (
  $primary: $primary
);
```

Rebuild:

```bash
npm run build:css
```

Replace CDN link in HTML with:

```html
<link rel="stylesheet" href="./css/main.css">
```

Refresh browser → Button color changes 🎉

---

# Show the Power

Change:

```scss
$primary: #ff3860;
```

Rebuild.

Everything using `is-primary` updates instantly.

Key concept:
One variable → entire theme updates.

---

# Add Custom Styling

Add to `main.scss`:

```scss
.page-title {
  letter-spacing: -0.02em;
  font-weight: 800;
}
```

Update HTML:

```html
<h1 class="title page-title">Hello Bulma</h1>
```

---

# How It Works

```
SCSS (Bulma + variables)
        ↓
Sass compiler
        ↓
Generated CSS
        ↓
Browser renders styled UI
```

---

---

---

## Copyright & Educational Use

© 2026 Nilma Abbas

This material was created for educational purposes only.

Permission is granted to use, copy, and modify this content for teaching, classroom use, and non-commercial educational activities.

Commercial redistribution or resale is not permitted without written permission from the author.