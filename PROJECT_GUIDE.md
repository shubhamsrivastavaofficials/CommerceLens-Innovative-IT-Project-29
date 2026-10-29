# CommerceLens — Project Guide

## Project overview

CommerceLens is an academic online-shopping analytics project with two related parts:

- **Primary deliverable:** a reproducible Python notebook for Google Colab.
- **Supporting deliverable:** a static browser dashboard prototype that provides a visual way to explore illustrative transactions and compatible CSV files.

The notebook is the primary place to inspect the Python analysis and use verified results in the project report or presentation. The website is not a replacement for the notebook.

## Problem statement

Transaction records contain information about order dates, products, customers, categories, and sales channels. Raw rows are difficult to compare manually. This project uses data preparation, aggregation, visualizations, SQL, and customer grouping to make common patterns easier to explore.

## Objectives

1. Summarize revenue, order volume, and average order value.
2. Compare products, categories, and channels.
3. Apply transparent Recency–Frequency–Monetary (RFM) customer grouping.
4. Explore category pairs occurring in the same order.
5. Prepare clean summaries and CSV exports for further analysis.
6. Provide a small interactive dashboard prototype for exploration.

## Main Python workflow

1. Load the sample or a compatible dataset.
2. Inspect column names, types, missing values, and duplicates.
3. Prepare dates and numeric fields for analysis.
4. Calculate line revenue as `quantity × unit_price × (1 − discount_pct / 100)`.
5. Aggregate by date, order, customer, product, category, and channel.
6. Visualize the descriptive summaries with Matplotlib and Seaborn.
7. Calculate descriptive RFM groups and category co-occurrence.
8. Run example SQL queries with SQLite.
9. Export useful tables as CSV for optional Power BI use.

Use the notebook outputs as the source of truth for any numbers reported in the final submission. If a website, spreadsheet, report, or presentation displays a different value, reconcile it against a fresh notebook run before presenting it as a result.

## Dashboard modules

### 1. Shopping overview
Headline metrics, revenue trend, category contribution, channel mix, and customer-group summary.

### 2. Product intelligence
Product-level units, distinct orders, net revenue, and average listed price.

### 3. Customer segments
Fixed-rule RFM groups based on recency, distinct-order frequency, and net spend. These are descriptive groups, not trained predictions.

### 4. Basket analysis
Counts distinct category pairs appearing within the same order. Co-occurrence suggests hypotheses to test; it does not establish causation.

### 5. Business insights
Descriptive observations based on the currently selected records. Treat them as prompts for further investigation, not proof of business impact.

### 6. CSV import/export
The browser prototype accepts a CSV with required fields and exports the currently filtered rows. Imported records stay in browser memory for the session and are not sent to a server.

## Dashboard CSV data dictionary

| Field | Required | Meaning |
|---|---:|---|
| `date` | Yes | Order-line date, readable by the browser |
| `order_id` | Yes | Identifier shared by lines belonging to one order |
| `customer_id` | Yes | Stable, pseudonymous customer identifier |
| `region` | Yes | Region label |
| `channel` | Yes | Sales channel |
| `category` | Yes | Product category |
| `product` | Yes | Product name or identifier |
| `quantity` | Yes | Units on the product line |
| `unit_price` | Yes | Price per unit, in a consistent currency |
| `discount_pct` | No | Percentage discount; defaults to zero |
| `payment_method` | No | Payment method label |

## Technology

- **Analysis:** Python, Pandas, NumPy, Matplotlib, Seaborn, SQLite SQL
- **Notebook environment:** Google Colab
- **Supporting dashboard:** HTML5, CSS, vanilla JavaScript, Canvas charts
- **Optional reporting:** Power BI using exported CSV tables
- **Hosting:** GitHub Pages for the static website

## Data and limitations

- The bundled dataset is synthetic and illustrative, not real retailer or customer data.
- Use one consistent currency for each dataset; confirm the notebook's display conventions before reporting monetary values.
- Revenue derived from quantity, price, and discounts does not automatically account for tax, shipping, refunds, or cost of goods.
- RFM thresholds are descriptive rules and may not fit every business.
- Category co-occurrence is not formal association-rule mining and does not prove causality.
- The static dashboard has no backend, authentication, or persistent storage.
- Do not describe illustrative prototype metrics as verified notebook results unless the notebook has been run and the values reconciled.

## Suggested evaluation checklist

- Check sales totals against a small manually calculated sample.
- Verify distinct order and customer counts.
- Review date parsing and missing/invalid values.
- Confirm RFM group rules and assignments.
- Check category pairs against a few manually inspected orders.
- Confirm CSV exports and visualizations match the data being analysed.
- Clearly explain the synthetic-data limitation in the viva.
