# CommerceLens — Online Shopping Data Analysis

**Project 29 · Innovative Internal Test · B.Tech CSE (Data Science & AI)**

CommerceLens explores online shopping transactions and turns item-level records into understandable sales, product, customer, and basket insights. The repository contains two complementary deliverables:

1. **Primary analysis:** a Python notebook for Google Colab using Pandas, NumPy, Matplotlib, Seaborn, and SQLite SQL.
2. **Supplementary dashboard prototype:** a responsive static website for interactively exploring illustrative records or importing a compatible CSV.

> **Data note:** the bundled dataset is synthetic and intended for learning and demonstration. It is not real retailer data. Verify notebook outputs before quoting any metrics in a report or presentation.

## Open the project

- **Live dashboard:** https://shubhamsrivastavaofficials.github.io/CommerceLens-Innovative-IT-Project-29/
- **Open notebook in Google Colab:** https://colab.research.google.com/github/shubhamsrivastavaofficials/CommerceLens-Innovative-IT-Project-29/blob/main/notebooks/Online_Shopping_Data_Analysis.ipynb
- **Notebook source on GitHub:** [notebooks/Online_Shopping_Data_Analysis.ipynb](notebooks/Online_Shopping_Data_Analysis.ipynb)
- **Sample transaction data:** [sample_dataset.csv](sample_dataset.csv)

## Repository layout

| Path | Purpose |
|---|---|
| `index.html` | Dashboard page structure |
| `assets/css/style.css` | Dashboard styling and responsive layouts |
| `assets/js/app.js` | Browser-side filtering, calculations, charts, CSV import/export |
| `notebooks/Online_Shopping_Data_Analysis.ipynb` | Main Python analysis workflow for Colab |
| `sample_dataset.csv` | Illustrative item-level transaction data |
| `CommerceLens_Sample_Dataset.xlsx` | Workbook with sample data and analysis summaries |
| `CommerceLens_Innovative_Internal_Test_Report.docx` | Project report |
| `CommerceLens_Innovative_Internal_Test_Presentation.pptx` | Presentation |
| `PROJECT_GUIDE.md` | Methods, modules, schema, and limitations |
| `SUBMISSION_CHECKLIST.md` | Final review checklist |
| `requirements.txt` | Python packages used by the notebook |

## Notebook workflow

1. Open the notebook using the Google Colab link above.
2. Run cells from top to bottom.
3. Review data preparation and missing/invalid-value handling.
4. Explore sales trends, categories, products, customers, and basket patterns.
5. Review the SQL examples and generated CSV exports.
6. Use the notebook's actual outputs when writing findings; do not copy illustrative website figures as notebook results.

The analysis includes net line revenue, order-level summaries, customer RFM grouping, category-pair co-occurrence, visualizations, SQL queries, and exports intended for further analysis or Power BI.

## Dashboard prototype

The dashboard is a static front-end demonstration. It can be hosted by GitHub Pages and does not require a server or build step. Use **Import CSV** to load a compatible file; uploaded records stay in browser memory for the current session and are not sent to a backend.

Required CSV headers:

```text
date, order_id, customer_id, region, channel, category, product, quantity, unit_price
```

Optional headers: `discount_pct`, `payment_method`. Each row represents one product line. Use a consistent currency and browser-readable dates such as `2026-04-15`.

## Methods and interpretation

Net line revenue is calculated as:

```text
quantity × unit_price × (1 − discount_pct / 100)
```

RFM groups are rule-based descriptive segments, not machine-learning predictions. Category co-occurrence indicates that categories appear in the same order; it does not prove causation. The sample data excludes tax, shipping, refunds, and cost of goods unless those are explicitly added to a dataset and model.

## Local setup (optional)

The notebook is designed for Google Colab. For local Python use, install dependencies with:

```bash
python -m pip install -r requirements.txt
```

The static dashboard can be opened directly in a browser or served with any static web server.

## Limitations

- Sample data is generated and illustrative, not observed customer behaviour.
- The dashboard uses client-side calculations and in-memory state; it has no login, backend, or persistent storage.
- RFM thresholds are fixed, and basket analysis is category co-occurrence rather than formal association-rule mining.
- Validate all calculations and outputs before using them in the final report, PPT, or viva.
