# Quickstart: Integrating INFAADEP Platform Packages

This guide covers setting up an Angular application (standalone components, v21 or v22) with `@infaadep/shared`, `@infaadep/charts`, and `@infaadep/ui`.

---

## 1. Configure the Registry

Create or edit `.npmrc` in your project root:

```ini
@infaadep:registry=https://npm.pkg.github.com
```

---

## 2. Install Packages & Dependencies

Install the platform packages along with required peer dependencies:

```bash
npm install @infaadep/shared @infaadep/charts @infaadep/ui \
  @angular/cdk @angular/material \
  echarts ngx-echarts
```

---

## 3. Configure Styles and Fonts

### A. Material Symbols Font
Add Google Material Symbols to your `index.html` inside `<head>`:

```html
<link
  rel="stylesheet"
  href="https://fonts.googleapis.com/css2?family=Material+Symbols+Outlined:opsz,wght,FILL,GRAD@20..48,100..700,0..1,-50..200&display=swap"
/>
```

### B. Global Styles
In your global stylesheet (`src/styles.scss`):

```scss
// Import base design tokens and theme from @infaadep/ui
@use '@infaadep/ui' as ui;

// Optional: if using Tailwind CSS
@import '@infaadep/ui/tailwind.css';
```

Or reference prebuilt CSS in `angular.json`:

```json
"styles": [
  "node_modules/@infaadep/ui/index.css",
  "src/styles.scss"
]
```

---

## 4. Setup Application Shell

Use `SidebarComponent` in `shell` mode to render the standard enterprise layout (top navbar + collapsible sidebar):

```typescript
import { Component } from '@angular/core';
import { SidebarComponent, SidebarConfig } from '@infaadep/shared';

@Component({
  selector: 'app-root',
  standalone: true,
  imports: [SidebarComponent],
  template: `
    <app-sidebar [config]="shellConfig">
      <!-- Custom actions projected into navbar right slot -->
      <div shell-navbar-actions>
        <button class="action-btn">Help</button>
      </div>

      <!-- Main router or content outlet -->
      <router-outlet></router-outlet>
    </app-sidebar>
  `
})
export class AppComponent {
  shellConfig: SidebarConfig = {
    layout: 'shell',
    brandName: 'INFAADEP Platform',
    menuItems: [
      { id: 'dashboard', label: 'Dashboard', icon: 'dashboard', route: '/dashboard' },
      { id: 'analytics', label: 'Analytics', icon: 'bar_chart', route: '/analytics' }
    ],
    user: {
      name: 'Enoc Emanuel',
      email: 'user@infaadep.com.mx'
    }
  };
}
```

---

## 5. Next Steps

- Explore [Shared Components Guide](shared.md) for navbar actions, footer widgets, and popovers.
- Explore [Charts Guide](charts.md) to integrate responsive ECharts.
- Explore [Design Tokens Guide](ui-tokens.md) for custom theme configurations.
- View live stories at [storybook.infaadep.com.mx](https://storybook.infaadep.com.mx).
