# @infaadep/charts

The `@infaadep/charts` package provides responsive enterprise chart components built on top of [Apache ECharts](https://echarts.apache.org/) and `ngx-echarts`.

---

## Installation

```bash
npm install @infaadep/charts echarts ngx-echarts
```

---

## Available Chart Components

| Component | Selector | Primary Use Case |
| :--- | :--- | :--- |
| `LineChartComponent` | `app-line-chart` | Trend analysis and time series data. |
| `AreaChartComponent` | `app-area-chart` | Volume tracking over intervals. |
| `BarChartComponent` | `app-bar-chart` | Category comparison and frequency distribution. |
| `StackedBarChartComponent` | `app-stacked-bar-chart` | Part-to-whole comparisons across categories. |
| `ComboChartComponent` | `app-combo-chart` | Combined bar and line dual-axis comparisons. |
| `DonutChartComponent` | `app-donut-chart` | Proportional distribution with center KPI slot. |
| `PieChartComponent` | `app-pie-chart` | Categorical market share and breakdown. |
| `GaugeChartComponent` | `app-gauge-chart` | Target vs. actual metric indicators. |
| `HeatmapChartComponent` | `app-heatmap-chart` | Activity intensity across 2D matrices (e.g. days/hours). |
| `RadarChartComponent` | `app-radar-chart` | Multi-variable performance profiles. |
| `SparklineComponent` | `app-sparkline` | Compact micro-charts for KPI cards and tables. |
| `TreemapChartComponent` | `app-treemap-chart` | Hierarchical nested metric visualization. |
| `WaterfallChartComponent` | `app-waterfall-chart` | Sequential step analysis (financial variances). |

---

## Basic Usage

Import the chart component directly into your Angular standalone component:

```typescript
import { Component } from '@angular/core';
import { LineChartComponent } from '@infaadep/charts';

@Component({
  selector: 'app-sales-overview',
  standalone: true,
  imports: [LineChartComponent],
  template: `
    <div class="chart-card">
      <h3>Monthly Revenue</h3>
      <app-line-chart
        [categories]="categories"
        [series]="series"
        [height]="'320px'"
      ></app-line-chart>
    </div>
  `
})
export class SalesOverviewComponent {
  categories = ['Jan', 'Feb', 'Mar', 'Apr', 'May', 'Jun'];
  series = [
    {
      name: 'Revenue 2026',
      data: [12000, 19000, 15000, 24000, 28000, 35000]
    }
  ];
}
```

---

## Interactive Examples

Preview all chart configurations, colors, and responsive behavior in the Storybook catalog:
👉 [https://storybook.infaadep.com.mx/?path=/docs/charts](https://storybook.infaadep.com.mx)
