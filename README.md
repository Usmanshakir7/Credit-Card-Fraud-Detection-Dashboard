Credit Card Fraud Analysis Dashboard | Power BI
An interactive Power BI dashboard for exploring credit card transaction patterns, understanding the distribution of fraudulent and legitimate transactions, and comparing transaction amounts and anonymized features.

This is a data analysis and visualization project, not a machine-learning fraud prediction system. It uses the existing fraud labels in the dataset to describe patterns and help users investigate the data.
Project Overview
Credit card fraud can be difficult to explore because fraudulent transactions represent a small portion of a typical transaction dataset. This project brings key measures and comparisons together in one report to make the data easier to understand.

Project objectives:
- Summarize total, fraudulent, and legitimate transactions.
- Calculate the fraud rate with interactive DAX measures.
- Compare transaction amounts and amount ranges.
- Explore how transactions change across elapsed-time intervals.
- Inspect patterns in anonymized variables such as V1–V5.
- Make individual transaction records easier to filter and review.
Dashboard Pages
Page	What it shows
01 — Executive Overview	KPI cards, fraud vs. legitimate transaction distribution, fraud trends, and amount-based summaries.
02 — Fraud Pattern Analysis	Interactive slicers, amount-range comparisons, elapsed-time trends, fraud rates, and V1–V5 feature comparisons.
03 — Transaction Explorer	A filterable transaction table, supporting charts, and summary cards for exploring selected records.


Core Metrics
- Total Transactions — number of transactions in the current filter context.
- Fraud Transactions — records with Class = 1.
- Legitimate Transactions — records with Class = 0.
- Fraud Rate — fraudulent transactions divided by total transactions.
- Average Transaction Amount — mean transaction amount in the current filter context.
Example DAX measures used in the model:
Total Transactions = COUNTROWS('creditcard')

Fraud Transactions =
CALCULATE(
    COUNTROWS('creditcard'),
    'creditcard'[Class] = 1
)

Fraud Rate =
DIVIDE([Fraud Transactions], [Total Transactions], 0)
Dataset
The project expects a local file named creditcard.csv with these fields:
Field	Description
Time	Seconds elapsed since the first recorded transaction; not a calendar date or local clock time.
V1–`V28`	Anonymized numerical features. Their original meanings are not supplied.
Amount	Transaction amount; the file does not specify a currency.
Class	Transaction label: 0 = legitimate, 1 = fraud.


The column structure matches the publicly available Credit Card Fraud Detection dataset commonly shared via Kaggle. Download the dataset separately and review its terms before use. The CSV is not included in this repository.
Tools and Techniques
- Microsoft Power BI Desktop — report building and interactive visualization.
- Power Query — CSV import and column data types.
- DAX — calculated measures and columns.
- Power BI Project (.pbip) — editable, source-control-friendly report and semantic model files.
How to Run This Project
1. Download or clone this GitHub repository to your Windows computer.
2. Download the dataset and save it locally as creditcard.csv.
3. Open Credit_Card_Fraud_Dashboard.pbip using a recent version of Power BI Desktop.
4. If Power BI asks you to fix the data source, open Home → Transform data → Power Query Editor.
5. Select the creditcard query. Under Applied Steps, edit the Source step to point to the location of your own creditcard.csv. Do not use the file path saved from the original developer's computer.
6. Select Close & Apply, then Refresh to load the data and calculate measures.
7. Explore the three report pages. Once everything loads correctly, you can save a local .pbix copy from Power BI Desktop.
Note: This is the lightweight project version. The imported transaction-data cache was deliberately excluded to make GitHub sharing easier. The report layout and semantic model definitions are included, but you must provide the CSV and refresh the model.

Repository Structure
Credit-Card-Fraud-Analysis-Dashboard/
├── README.md
├── .gitignore
├── Credit_Card_Fraud_Dashboard.pbip
├── Credit_Card_Fraud_Dashboard.Report/
│   ├── definition/
│   └── StaticResources/
└── Credit_Card_Fraud_Dashboard.SemanticModel/
    ├── definition.pbism
    └── definition/
The project folders also contain Power BI metadata files required to open the report.
Interpretation and Limitations
- Fraud is rare relative to legitimate transactions, so raw counts and percentages should be interpreted together.
- Charts using Time or Hour Interval refer to elapsed time from the dataset's first transaction, not actual hours of the day.
- V1–`V28` are anonymized features. A difference in their plotted values does not explain the real-world cause of fraud.
- The report explores already-labeled transactions. It does not predict whether a new transaction is fraudulent.
- No bank, customer, or financial-business outcome should be inferred directly from this demonstration dataset.
Possible Future Improvements
- Add interactive drill-through and transaction-level tooltips.
- Add documentation of dataset quality checks and exploratory findings.
- Compare additional anonymized features beyond V1–V5.
- Develop a separate machine-learning experiment and evaluate it with appropriate imbalanced-class metrics before considering predictive use.
Project Status
The report pages, visual definitions, and data-model definitions are provided. The project files were structurally checked, but final visual rendering and data refresh must still be verified in Power BI Desktop.
