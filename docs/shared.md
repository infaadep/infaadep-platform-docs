# @infaadep/shared

The `@infaadep/shared` package delivers shared Angular navigation, layouts, identity headers, and contextual help tools.

---

## Installation

```bash
npm install @infaadep/shared @angular/cdk @angular/material
```

---

## Components

### 1. `SidebarComponent`
The primary navigation container supporting three layout configurations:
- **`shell` (Recommended):** Full desktop application shell with top navigation bar and collapsible sidebar.
- **`sidebar`:** Independent sidebar drawer navigation.
- **`navbar`:** Horizontal top navigation bar only.

#### Example: Shell with Projection Slots

```typescript
import { Component } from '@angular/core';
import { SidebarComponent, SidebarConfig } from '@infaadep/shared';

@Component({
  selector: 'app-shell',
  standalone: true,
  imports: [SidebarComponent],
  template: `
    <app-sidebar [config]="config">
      <!-- Projected custom actions in navbar -->
      <div shell-navbar-actions>
        <button mat-icon-button aria-label="Notifications">
          <mat-icon fontSet="material-symbols-outlined">notifications</mat-icon>
        </button>
      </div>

      <!-- Top section in sidebar (e.g. tenant or organization switcher) -->
      <div sidebar-top>
        <div class="org-badge">Tenant: Sucursal Norte</div>
      </div>

      <!-- Footer section in sidebar -->
      <div sidebar-footer>
        <span class="version-label">v2.1.2</span>
      </div>

      <!-- Main body projection -->
      <router-outlet></router-outlet>
    </app-sidebar>
  `
})
export class ShellComponent {
  config: SidebarConfig = {
    layout: 'shell',
    brandName: 'INFAADEP Platform',
    menuItems: [
      { id: 'home', label: 'Inicio', icon: 'home', route: '/home' },
      {
        id: 'sales',
        label: 'Ventas',
        icon: 'storefront',
        children: [
          { id: 'invoices', label: 'Facturación', route: '/sales/invoices' },
          { id: 'reports', label: 'Reportes', route: '/sales/reports' }
        ]
      }
    ],
    user: {
      name: 'Enoc Emanuel',
      email: 'eehcx.contacto@gmail.com'
    }
  };
}
```

---

### 2. `BrandHeaderComponent`
A consistent header component displaying the organization brand logo, name, and environment context.

```html
<app-brand-header
  [title]="'CFDI Miner'"
  [subtitle]="'Portal Fiscal v2'"
  [environment]="'Producción'"
></app-brand-header>
```

---

### 3. Contextual Help: `FieldHelpComponent` & `InfoPopoverComponent`
Interactive help popovers and field guidance buttons using Angular CDK overlays.

```html
<app-field-help
  [tooltip]="'El RFC debe estar registrado ante el SAT con estatus activo.'"
></app-field-help>
```

---

## Storybook Live Preview

All shared components and interactive configurations are documented at:
👉 [https://storybook.infaadep.com.mx/?path=/docs/shared](https://storybook.infaadep.com.mx)
