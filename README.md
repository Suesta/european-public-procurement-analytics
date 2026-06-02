# European Public Procurement Analytics

Interactive data visualization project exploring European public procurement awards using TED Contract Award Notices from 2021 to 2023.

The project combines data cleaning, aggregation and web-based visualization to make a large public procurement dataset easier to explore.

## Live demo

[https://suavesote.github.io/european-public-procurement-visualization/](https://suavesote.github.io/european-public-procurement-visualization/)

## Project overview

Public procurement data can be difficult to interpret because it contains many records, large monetary values, different contract types, country-level differences and sector classifications.

This project provides an interactive overview of European contract award notices, focusing on five main questions:

* How did public procurement awards evolve between 2021 and 2023?
* Which buyer countries concentrated the largest procurement volume?
* Which CPV sectors represented the highest awarded value or number of awards?
* How was procurement distributed across services, supplies and works?
* What part of the data corresponds to domestic, cross-border or unknown supplier-country awards?

The final visualization is designed as an exploratory dashboard, with a simple structure and a metric selector that allows the user to switch between awarded value and number of awards.

## Data source

The project uses TED Contract Award Notices from 2021 to 2023.

TED, Tenders Electronic Daily, is the European platform for public procurement notices. The original files were cleaned and aggregated before visualization.

Only processed CSV files are included in this repository. The original raw files are not included because of their size.

## Data preparation

The original data was processed to keep the most relevant fields for visualization, including:

* Year.
* Buyer country.
* Contract type.
* CPV code and CPV division.
* Awarded value.
* Supplier country.
* Domestic or cross-border supplier status.

The preparation process included:

* Selecting relevant columns.
* Cleaning missing or invalid award values.
* Removing extreme award-value outliers to reduce visual distortion.
* Aggregating the data by year, country, contract type, CPV division and supplier status.
* Exporting lightweight CSV files for the web visualization.

## Main features

* Overview KPIs for the processed dataset.
* Interactive metric selector:

  * Total awarded value.
  * Number of awards.
* Evolution of awards over time.
* Ranking of main buyer countries.
* CPV sector comparison.
* Contract type comparison by year.
* Supplier country information, separating domestic awards, cross-border awards and awards with unknown supplier country.
* Public web deployment using GitHub Pages.

## Repository structure

```text
.
├── index.html
├── style.css
├── app.js
├── data
│   ├── summary_kpis.csv
│   ├── awards_by_year.csv
│   ├── awards_by_country.csv
│   ├── awards_by_cpv_division.csv
│   ├── awards_by_year_and_contract_type.csv
│   └── awards_by_year_and_supplier_status.csv
├── README.md
└── LICENSE
```

## How to run locally

Because the visualization loads CSV files with JavaScript, it should be opened through a local web server.

From the repository folder, run:

```bash
python -m http.server 8000
```

Then open:

```text
http://localhost:8000
```

## Tools used

* HTML
* CSS
* JavaScript
* D3.js
* Plotly.js
* Python for data preparation

## Notes and limitations

This project is exploratory and does not aim to provide a complete procurement intelligence system.

The original TED data contains missing values, especially in some supplier-country fields. For this reason, supplier-country information is separated into domestic awards, cross-border awards and awards with unknown supplier country.

The most extreme 0.5% of award values were excluded to reduce distortion in the charts.
