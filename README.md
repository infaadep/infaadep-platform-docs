# INFAADEP Frontend Platform Documentation

[![Storybook Live](https://img.shields.io/badge/Storybook-Live_Catalog-FF4785?logo=storybook&logoColor=white)](https://storybook.infaadep.com.mx)
[![Angular](https://img.shields.io/badge/Angular-21%20%7C%2022-DD0031?logo=angular&logoColor=white)](https://angular.dev)
[![GitHub Packages](https://img.shields.io/badge/GitHub%20Packages-@infaadep-blue?logo=github)](https://github.com/orgs/infaadep/packages)

Public integration guides, component API references, and token specifications for the **INFAADEP Frontend Platform** packages.

Explore interactive component previews, theme switchers, and chart configurations directly in the live Storybook:
👉 **[storybook.infaadep.com.mx](https://storybook.infaadep.com.mx)**

---

## Published Packages

| Package | Version | Description |
| :--- | :--- | :--- |
| **[`@infaadep/charts`](docs/charts.md)** | `^2.1.2` | High-performance enterprise ECharts wrappers for Angular. |
| **[`@infaadep/shared`](docs/shared.md)** | `^2.1.2` | Navigation shell (Sidebar, Navbar), headers, and utility components. |
| **[`@infaadep/ui`](docs/ui-tokens.md)** | `^2.1.2` | Brand design tokens, multi-theme Sass variables, and Tailwind CSS preset. |

---

## Quick Setup

All `@infaadep` packages are publicly published to the GitHub Packages registry.

### 1. Configure npm Registry Scope

Add an `.npmrc` file to the root of your project:

```ini
@infaadep:registry=https://npm.pkg.github.com
```

> **Note:** Because the packages are public, **no authentication token** or login is required to download or install them.

### 2. Install Packages

```bash
# Using npm
npm install @infaadep/shared @infaadep/charts @infaadep/ui

# Using Yarn
yarn add @infaadep/shared @infaadep/charts @infaadep/ui

# Using pnpm
pnpm add @infaadep/shared @infaadep/charts @infaadep/ui
```

---

## Documentation Guides

- 🚀 **[Quickstart & Project Integration](docs/quickstart.md)** — Step-by-step setup in an Angular 21/22 application.
- 📊 **[Charts Guide (@infaadep/charts)](docs/charts.md)** — Area, Bar, Combo, Donut, Gauge, Heatmap, Line, Pie, Radar, and Sparkline components.
- 🧭 **[Shared Components Guide (@infaadep/shared)](docs/shared.md)** — `SidebarComponent` (Shell, Sidebar, Navbar modes), `BrandHeaderComponent`, `FieldHelpComponent`, `InfoPopoverComponent`.
- 🎨 **[Design Tokens & Themes (@infaadep/ui)](docs/ui-tokens.md)** — Using Sass variables, Material themes (Purple, Brand, etc.), and Tailwind CSS utilities.

---

## Micro Frontend Architecture

The platform packages are optimized for Angular standalone components and Native Federation architectures (Micro Frontends):
- **Peer-dependency agnostic:** Supports both Angular `^21.0.0` and `^22.0.0`.
- **Zero code duplication:** Design tokens and layout engines are shared across host shells and remote MFEs.
- **Tree-shakeable:** Partial compilation mode preserves Angular FESM and DTS bundles.

---

## Resources

- **Interactive Catalog:** [https://storybook.infaadep.com.mx](https://storybook.infaadep.com.mx)
- **Organization Packages:** [https://github.com/orgs/infaadep/packages](https://github.com/orgs/infaadep/packages)
