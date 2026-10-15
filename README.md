# RappiPlus | Business Performance & Profitability Analysis

**Python · Pandas · SQL (PostgreSQL) · Statistical Testing · Power BI**

## Project overview

This project analyzes RappiPlus business performance through a connected workflow: data quality assessment, order profitability, sales behavior, conversion funnel analysis, customer retention cohorts, and an A/B test of a checkout interface change. The goal is to turn operational data into evidence-based business recommendations.

## Questions explored

- How do revenue, product costs, and marketing spending affect estimated profitability?
- Which products and channels contribute to sales performance?
- At which stages of the purchasing funnel do users drop off?
- How does retention vary across registration cohorts?
- Does the checkout UI experiment show a statistically significant conversion difference?

## Analytical workflow

1. **Data preparation:** inspect missing values, inconsistent categories, anomalies, dates, and duplicates; export cleaned order, catalog, and marketing datasets.
2. **Business performance:** compute revenue, product costs, marketing spending, profit under the available cost definition, average order value, and product/channel metrics.
3. **Conversion funnel (PostgreSQL):** query events and calculate a sequential funnel.
4. **Retention (PostgreSQL):** analyze weekly activity across registration cohorts.
5. **Experimentation:** compare checkout conversion across A/B test variants using a statistical hypothesis test.
6. **Reporting:** communicate findings through a Power BI dashboard.

## Key findings

The notebook reports an average order value of approximately **$385.88**, an average of **1.50 items per order**, and **Vacuum-Pro-Black** as the highest-volume product (**6,284 units**) in the analyzed period. These are results from the supplied educational dataset, not independently verified operating figures of a real company.

**Profitability scope:** the project's profit estimate deducts available product costs and marketing spending from revenue; it is **not** a full net-profit calculation because other operating expenses are not represented.

For complete calculations, statistical results, limitations, and recommendations, see [`rappiplus_analysis.ipynb`](rappiplus_analysis.ipynb).

## Files

```text
rappiplus-business-analytics/
├── rappiplus_analysis.ipynb
├── requirements.txt
├── .gitignore
├── .env.example
└── README.md
```

## How to run

1. Clone this repository and open it in VS Code or Jupyter.
2. Install dependencies: `pip install -r requirements.txt`.
3. Run the notebook in order. The data-preparation and A/B test sections download their inputs from source URLs embedded in the notebook; these URLs must remain accessible.
4. **PostgreSQL sections require separate, authorized access** to the `events`, `users`, and `user_activity` tables. Set the environment variables in `.env.example` in your own environment before running the SQL cells. The notebook does not automatically load `.env` files.
5. The SQL-dependent outputs cannot be regenerated without that database. The repository does not provide credentials or a database dump.

**Data availability:** source download URLs are included for reference; their availability and redistribution permissions are controlled by the source provider. Cleaned datasets and the `.pbix` file are intentionally not bundled here.

## Dashboard

The project also includes a Power BI reporting stage. A dashboard reference appears in the final section of the notebook. Access to external dashboard files may depend on the owner’s sharing permissions.

## Limitations

- Some sections depend on a separate PostgreSQL environment.
- Profit is estimated using only costs represented in the datasets.
- Observed relationships and recommendations should not be interpreted as proof of causal impact without appropriate testing.
- Source datasets are educational; results should not be treated as real-world corporate financial statements.

## Author

Jasmanik Torres López — [Portfolio](https://jasmaniktl.github.io/) · [GitHub](https://github.com/JasmanikTL)
