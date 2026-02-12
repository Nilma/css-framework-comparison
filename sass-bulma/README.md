# Sass + Bulma Dashboard (matched to your Bulma HTML)

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
