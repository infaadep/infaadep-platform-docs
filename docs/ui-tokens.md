# @infaadep/ui

`@infaadep/ui` is the Single Source of Truth (SSoT) for the INFAADEP design system tokens, CSS custom properties, Sass themes, and Tailwind CSS presets.

---

## Installation

```bash
npm install @infaadep/ui
```

---

## Token Architecture

The token system is structured into three layers:
1. **Core Brand & Functional Colors:** Base palettes (Purple, Brand, Blue, Success, Warning, Error).
2. **Semantic Variables:** Abstracted tokens like `--bg-primary`, `--text-primary`, `--border-subtle`.
3. **Themes:** Pre-built palettes (`purple`, `aqua`, `cyan`, `green`, `orange`, `brand`).

---

## Sass Integration

In your main stylesheet (e.g. `src/styles.scss`):

```scss
// Import full design system styles
@use '@infaadep/ui' as ui;

// Example: Using CSS variables provided by the theme
body {
  background-color: var(--bg-primary);
  color: var(--text-primary);
  font-family: 'Inter', sans-serif;
}
```

---

## Tailwind CSS Integration

Import the preconfigured Tailwind stylesheet:

```scss
@import '@infaadep/ui/tailwind.css';
```

Or reference it in your build configuration to gain access to all semantic color utilities:
- `bg-primary`, `bg-hover`, `surface-bg`
- `text-primary`, `text-secondary`, `text-muted`
- `border-subtle`, `border-focus`

---

## Available Themes

You can activate predefined themes by applying theme classes or importing specific stylesheets:

| Theme | Primary Hex | Palette Style |
| :--- | :--- | :--- |
| **Purple (Default)** | `#763ebd` | Modern enterprise SaaS |
| **Brand (INFAADEP)** | `#0f172a` | Formal institutional |
| **Aqua** | `#0284c7` | High-contrast data analytics |
| **Green** | `#16a34a` | Environmental / Fiscal |

---

## Storybook Tokens Showcase

Explore color swatches, typography scales, and shadows in the live catalog:
👉 [https://storybook.infaadep.com.mx/?path=/docs/ui-themes](https://storybook.infaadep.com.mx)
