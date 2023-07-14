# export-table-to-csv

[![npm version](https://badge.fury.io/js/export-table-to-csv.svg)](https://www.npmjs.com/package/export-table-to-csv)
[![license](https://img.shields.io/npm/l/export-table-to-csv)](https://github.com/suhaibjanjua/export-table-to-csv/blob/main/LICENSE.md)

Fast and lightweight html TABLE to CSV exporter. This package includes two modules:

  * **[ExportMatTableToCSV](#exportfrommattable):** A synchronous mat TABLE(`<mat-table>`) to CSV exporter written in simple JavaScript. It's fast and simple to use.
  * **[ExportTableToCSV](#exportfromtable):** A synchronous html TABLE(`<table>`) to CSV exporter written in simple JavaScript. Really fast and supports large datasets.


### Features

- Fast and lightweight
- Support for standard TABLE as well as MAT-TABLE
- Support for custom filename that also shows up in the top row


## Requirements

- None


## Installation

### **NPM**

You can install export-table-to-csv as a dependency using NPM.

```bash
$ npm install export-table-to-csv --save
```


### **Yarn**

You can install export-table-to-csv as a dependency using Yarn.

```bash
$ yarn add export-table-to-csv
```


## ExportMatTableToCSV

`ExportMatTableToCSV` can be used programmatically as a synchronous converter.

It retrieves the entire Angular Material Table with the tag (`<mat-table>`) that matches to the param `tableId` to load headers and rows to converts the data into the CSV format, and export the file as download for the user.


### Usage

```js
import { ExportMatTableToCSV } from "export-table-to-csv";

try {
  const tableId = '#tableId';
  const filename = 'Export HTML Data';
  ExportMatTableToCSV(tableId, filename);
  
  // Exported file name ==> Export HTML Data - Thu Jan 13 2023 15_42_45.csv
} catch (err) {
  console.error(err);
}
```


#### Parameters

* tableId (string): The id of the desired angular material table or a standard table from the html you want to export.
* filename (string): The desired filename for the exported CSV file.


##### Note

The `ExportMatTableToCSV` function assumes the presence of a `<mat-table>` structure in the DOM, with the appropriate structure of `<mat-header-row>`, `<mat-header-cell>`, `<mat-row>`, and `<mat-cell>` elements. 

This module is designed to work in a browser environment with access to the Document Object Model (DOM) APIs (e.g., browser or Node.js).


## ExportTableToCSV

`ExportTableToCSV` can be used programmatically as a synchronous converter.

It retrieves the html table (`<table>`) by matching the param `tableId` in the DOM, with the appropriate structure of `<thead>`, `<tbody>`, `<th>`, `<tr>`, and `<td>` elements. `<tfoot>` is not considered while exporting the table to a CSV format.

### Usage

```js
import { ExportTableToCSV } from "export-table-to-csv";

try {
  const tableId = '#tableId';
  const filename = 'Export HTML Data';
  ExportTableToCSV(tableId, filename);

  // Exported file name ==> Export HTML Data - Thu Jan 13 2023 15_42_45.csv
} catch (err) {
  console.error(err);
}
```


#### Parameters

* tableId (string): The id of the desired angular material table or a standard table from the html you want to export.
* filename (string): The desired filename for the exported CSV file.


##### Note

While `ExportTableToCSV` function assumes the presence of a standard `<table>` structure in the DOM, with the appropriate structure of `<thead>`, `<tbody>`, `<th>`, `<tr>`, and `<td>` elements. `<tfoot>` is not a part of the exported file.

This module is designed to work in a browser environment with access to the Document Object Model (DOM) APIs (e.g., browser or Node.js).


## License

See [LICENSE.md](https://github.com/suhaibjanjua/export-table-to-csv/blob/main/LICENSE.md).
