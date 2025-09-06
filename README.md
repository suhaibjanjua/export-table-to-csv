<h1 align="center"> Export Table to CSV </h1>
<p align="center"> Effortlessly export data from HTML and Angular Material tables to CSV. </p>

<p align="center">
  <img alt="Build" src="https://img.shields.io/badge/Build-Passing-brightgreen?style=for-the-badge">
  <img alt="Issues" src="https://img.shields.io/badge/Issues-0%20Open-blue?style=for-the-badge">
  <img alt="Contributions" src="https://img.shields.io/badge/Contributions-Welcome-orange?style=for-the-badge">
  <img alt="License" src="https://img.shields.io/badge/License-MIT-yellow?style=for-the-badge">
</p>

---

[![npm version](https://badge.fury.io/js/export-table-to-csv.svg)](https://www.npmjs.com/package/export-table-to-csv)
[![license](https://img.shields.io/npm/l/export-table-to-csv)](https://github.com/suhaibjanjua/export-table-to-csv/blob/main/LICENSE.md)

## 📖 Table of Contents
- [⭐ Overview](#-overview)
- [✨ Key Features](#-key-features)
- [🛠️ Tech Stack & Architecture](#️-tech-stack--architecture)
- [🚀 Getting Started](#-getting-started)
- [🔧 Usage](#-usage)
- [🤝 Contributing](#-contributing)
- [📝 License](#-license)

---

## ⭐ Overview

`export-table-to-csv` is a blazing-fast, lightweight JavaScript library designed for the seamless export of data from both standard HTML `<table>` elements and Angular Material `<mat-table>` components directly into Comma-Separated Values (CSV) format.

> 🌐 **The Problem:** In today's web applications, displaying tabular data is commonplace. However, users often face a significant hurdle when needing to extract this data for analysis, reporting, or integration with other tools. Manually copying and pasting is tedious and error-prone, while server-side solutions add complexity and latency. Especially with modern frameworks like Angular Material, the DOM structure can make extraction challenging.

> ✅ **The Solution:** This project provides an elegant, client-side solution that empowers end-users to effortlessly download table content as a CSV file with a single function call. By offering distinct modules for standard HTML tables (`ExportTableToCSV`) and Angular Material tables (`ExportMatTableToCSV`), it addresses diverse front-end needs, ensuring data portability and enhancing user experience without requiring server-side intervention or heavy dependencies.

**Inferred Architecture:**
This project is structured as a client-side JavaScript utility library. Its core logic resides in `src/index.js`, which is then transpiled using Babel (leveraging `babel-preset-env` for broad compatibility) and minified with UglifyJS into `src/index.min.js` for production use. This architecture ensures the library is lightweight, performs efficiently in web browsers, and is easily embeddable into any web project, including those built with modern frameworks like Angular.

---

## ✨ Key Features

*   **Universal HTML Table Export:** Provides a robust `ExportTableToCSV` module capable of parsing and exporting data from any standard HTML `<table>` element, offering broad compatibility for existing web pages.
*   **Angular Material Table Integration:** Specifically engineered with the `ExportMatTableToCSV` module to intelligently extract data from Angular Material's `<mat-table>` components, accommodating their unique DOM structure.
*   **Lightweight & Performant:** Optimized for client-side execution, the minified `index.min.js` ensures a minimal footprint and swift data export, even for large datasets.
*   **Direct CSV Output:** Converts table data directly into a standard Comma-Separated Values (CSV) format, ready for download and compatible with spreadsheet software.
*   **Easy Integration:** Designed for simplicity, the library exposes a straightforward API that can be quickly integrated into any JavaScript or TypeScript project, enhancing data usability with minimal development effort.

---

## 🛠️ Tech Stack & Architecture

| Technology | Purpose                  | Why it was Chosen                                                                      |
| :--------- | :----------------------- | :------------------------------------------------------------------------------------- |
| **JavaScript** | Core Logic & Interactivity | The universal language of the web, ensuring maximum browser compatibility and client-side execution. |
| **Babel**      | JavaScript Transpilation | Enables writing modern ES6+ JavaScript while ensuring compatibility with older browser environments. |
| **UglifyJS**   | Code Minification        | Reduces the final bundle size of the library, leading to faster load times and improved performance. |
| **NPM**        | Package Management       | The standard ecosystem for JavaScript package distribution, simplifying installation and dependency management. |

---

## 🚀 Getting Started

To get a copy of the project up and running on your local machine for development and testing purposes, follow these simple steps.

### Prerequisites

Ensure you have the following installed on your system:

*   **Node.js**: `v12` or higher (includes npm)
*   **(Optional) Yarn**: `v1.22` or higher

### Installation

This project is available as an npm package. You can install it in your project using either npm or yarn.

#### Via npm:

```bash
npm install export-table-to-csv
```

#### Via yarn:

```bash
yarn add export-table-to-csv
```

#### Manual Download:

Alternatively, you can directly download the minified JavaScript file and include it in your HTML:

1.  Download `src/index.min.js` from the repository.
2.  Include it in your HTML file:
    ```html
    <script src="path/to/index.min.js"></script>
    ```

---

## 🔧 Usage

Once installed, you can easily import and use the `ExportTableToCSV` or `ExportMatTableToCSV` modules in your JavaScript or TypeScript application.

### Importing the Modules

#### ES Module (recommended for modern projects):

```javascript
import { ExportTableToCSV, ExportMatTableToCSV } from 'export-table-to-csv';
```

#### CommonJS (for Node.js environments or older bundlers):

```javascript
const { ExportTableToCSV, ExportMatTableToCSV } = require('export-table-to-csv');
```

#### Global Script (if included via `<script>` tag):

The functions will be available globally as `window.ExportTableToCSV` and `window.ExportMatTableToCSV`.

### Exporting a Standard HTML Table

To export a standard `<table>` element, provide its ID and the desired filename.

```html
<table id="myDataTable">
  <thead>
    <tr>
      <th>Header 1</th>
      <th>Header 2</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Data A1</td>
      <td>Data A2</td>
    </tr>
    <tr>
      <td>Data B1</td>
      <td>Data B2</td>
    </tr>
  </tbody>
</table>

<button onclick="exportMyTable()">Export Data</button>

<script>
  // Assuming ExportTableToCSV is imported or available globally
  function exportMyTable() {
    ExportTableToCSV('myDataTable', 'my_exported_data.csv');
    alert('Table exported successfully!');
  }
</script>
```

### Exporting an Angular Material Table

For Angular Material tables, use `ExportMatTableToCSV` and provide the ID of your `<mat-table>` element along with the filename.

```html
<!-- Assuming this is within an Angular component template -->
<mat-table #myMatTable [dataSource]="dataSource">
  <!-- Column definitions -->
  <ng-container matColumnDef="col1">
    <mat-header-cell *matHeaderCellDef> Column 1 </mat-header-cell>
    <mat-cell *matCellDef="let element"> {{element.col1}} </mat-cell>
  </ng-container>
  <ng-container matColumnDef="col2">
    <mat-header-cell *matHeaderCellDef> Column 2 </mat-header-cell>
    <mat-cell *matCellDef="let element"> {{element.col2}} </mat-cell>
  </ng-container>

  <mat-header-row *matHeaderRowDef="displayedColumns"></mat-header-row>
  <mat-row *matRowDef="let row; columns: displayedColumns;"></mat-row>
</mat-table>

<button (click)="exportMatTable()">Export Material Table</button>
```

```typescript
// Within your Angular component (.ts file)
import { Component } from '@angular/core';
import { ExportMatTableToCSV } from 'export-table-to-csv'; // Import the module

@Component({
  selector: 'app-my-component',
  templateUrl: './my-component.html',
  styleUrls: ['./my-component.css']
})
export class MyComponent {
  dataSource = [ /* your data array */ ];
  displayedColumns: string[] = ['col1', 'col2'];

  exportMatTable() {
    // You might need to get the nativeElement from a ViewChild reference if using #myMatTable
    // For simplicity, this example assumes the ID 'myMatTable' directly references the DOM element.
    ExportMatTableToCSV('myMatTable', 'material_table_data.csv');
    alert('Angular Material Table exported!');
  }
}
```

---

## 🤝 Contributing

We welcome contributions to make `export-table-to-csv` even better! If you have suggestions for improvements, new features, or bug fixes, please follow these steps:

1.  **Fork** the repository on GitHub.
2.  **Clone** your forked repository to your local machine.
3.  **Create a new branch** for your feature or bug fix: `git checkout -b feature/your-feature-name` or `git checkout -b bugfix/issue-description`.
4.  **Make your changes** and ensure they align with the project's coding style.
5.  **Test your changes** thoroughly.
6.  **Commit your changes** with a clear and descriptive commit message.
7.  **Push your branch** to your forked repository: `git push origin feature/your-feature-name`.
8.  **Open a Pull Request** from your branch to the `main` branch of this repository, describing your changes and their benefits.

---

## 📝 License

Distributed under the MIT License. See `LICENSE.md` for more information.
