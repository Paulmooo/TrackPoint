# TrackPoint Platform

## Project Overview

TrackPoint Platform is a visualization platform for data reported by the tracking SDK. It provides three modules: **Behavior Analysis**, **Performance Analysis**, and **Exception Analysis**. Each module contains a filter panel and a data dashboard. Platform users can apply filters to analyze the processed tracking data aggregated by the data service.

## Getting Started

```bash
pnpm install
pnpm start
```

## Tech Stack

1. **React + TypeScript + SCSS**: Core framework and styling.
2. **React Router**: Routing library for navigation.
3. **Ant Design (Antd)**: Component library for layout and filter panels.
4. **Echarts + Echarts for React**: Chart library for building dashboards.
5. **Axios + Axios Mock Adapter**: HTTP client and mock server for API simulation.
6. **dayjs**: Utility library for date and time formatting.

## Directory Structure

```
platform
│  config-overrides.js            // Webpack configuration overrides
│  package.json                   // Dependencies
│  README.md                      // Documentation
│  tsconfig.json                   // TypeScript configuration
└─src
    │  data.tsx                   // Filter panel option data
    │  global.scss                // Global SCSS file
    │  global.ts                  // Global TypeScript file
    │  index.tsx                  // Entry point
    │  routes.tsx                 // Routing configuration
    ├─commons                      // Common components and utilities
    │  ├─Filter                    // Filter panel components
    │  │  ├─CascaderFilter         // Cascader selector
    │  │  ├─DateFilter             // Date picker
    │  │  ├─PanelFilter            // Filter panel
    │  │  ├─RadioFilter            // Radio button
    │  │  └─SelectFilter           // Dropdown selector
    │  ├─function                  // Utility functions
    │  └─Panel
    │      └─BasePanel
    ├─layouts
    │  └─MainLayout                // Main layout
    ├─pages
    │  ├─Action                     // User behavior monitoring page
    │  ├─Exception                  // Exception monitoring page
    │  ├─Home                        // Home page
    │  └─Performance                 // Performance monitoring page
    └─themes
        └─antd                       // Ant Design theme configuration
```

## Module Details

### Behavior Analysis

Analyzes user behavior trends within a specified time range, counting how many times specific actions occur for selected users.

#### Filter Panel

##### Date Picker

* Filter by day or month within a defined range.
* When filtering by day, the dashboard displays hourly data.
* When filtering by month, the dashboard displays daily data.

##### Behavior Selector

* Single selection within a defined range.

#### Dashboard

* X-axis represents time, Y-axis represents occurrence count.
* Displays the number and names of relevant behaviors over the selected time period.

---

### Performance Analysis

Analyzes performance metrics for specific URLs over a given time range, helping developers understand page load speed and user experience. Metrics include **First Paint (FP)**, **First Contentful Paint (FCP)**, **Largest Contentful Paint (LCP)**, and **Cumulative Layout Shift (CLS)**.

#### Filter Panel

##### Date Picker

* Filter by day or month within a defined range.
* When filtering by day, the dashboard displays hourly data.
* When filtering by month, the dashboard displays daily data.

##### URL Selector

* Single selection within a defined range.

#### Dashboard

* **Simplified mode (bar chart)**: Shows the average values of FP, FCP, LCP, and CLS.
* **Detailed mode (line chart)**: Shows both average and maximum values over time, visualizing performance trends for the selected URL.

---

### Exception Analysis

Analyzes the URLs and types of pages where exceptions occurred.

#### Filter Panel

##### URL Selector

* Multi-selection within a defined range.

##### Exception Type Selector

* Multi-selection within a defined range.

#### Dashboard

* Displays data in a table format.
* The last column contains an alert button that allows sending notifications (e.g., email) to developers or testers.
