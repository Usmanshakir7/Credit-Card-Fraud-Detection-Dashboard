# Credit Card Fraud Detection Dashboard

This is a Power BI dashboard I built as part of my Data Visualization practice as a Data Science student. I wanted to work with a real dataset and understand how data visualization can make unusual transaction patterns easier to explore.

The project looks at historical credit card transactions and compares fraudulent and legitimate activity. It is a **data analysis and visualization project**, not a machine learning fraud detection system.

## Dataset

I used the [Credit Card Fraud Detection dataset on Kaggle](https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud).

| Dataset summary | Value |
| --- | ---: |
| Total transactions | 284,807 |
| Legitimate transactions | 284,315 |
| Fraudulent transactions | 492 |
| Fraud rate | About 0.17% |

The dataset contains `Time`, `Amount`, `Class`, and anonymized features `V1` to `V28`. In the `Class` column, **0 means legitimate** and **1 means fraud**. The transaction amounts do not have a specified currency.

I did not upload the raw CSV because it is large. You can download it from the Kaggle link above.

## What's in the dashboard?

I organized the report into three pages:

**1. Overview** — A quick look at total transactions, fraud count, legitimate transactions, fraud rate, average transaction amount, and some basic comparisons.

**2. Fraud Pattern Analysis** — Charts to compare fraud rates and counts across transaction amount ranges, along with a comparison of the anonymized V1–V5 features. Filters help explore different groups.

**3. Transaction Explorer** — A table for looking more closely at individual transactions, with filters for transaction class and amount range.

## Dashboard screenshots

### 1. Executive Overview

A summary of the transaction dataset, with KPI cards, fraud versus legitimate transactions, fraud by elapsed hour, and average transaction amount by class.

![Executive Overview](screenshots/Screenshot%202026-11-27%20010151.png)

### 2. Fraud Pattern Analysis

Compare fraud counts and rates across amount ranges. The 0–49 range has the most fraud cases (305), while the 500–999 range has the highest fraud rate (approximately 0.41%). This shows why both counts and rates matter.

![Fraud Pattern Analysis](screenshots/Screenshot%202026-11-27%20003448.png)

### 3. Transaction Explorer

Explore individual transactions using class and amount filters, with summary statistics that respond to the selection.

![Transaction Explorer](screenshots/Screenshot%202026-11-27%20003546.png)

## Tools I used

- **Power BI Desktop** to build the dashboard and charts
- **Power Query** to load and prepare the data
- **DAX** to calculate KPIs such as fraud rate and transaction counts
- **Git and GitHub** to share and document the project

For example, this is the DAX measure I used to calculate fraud rate:

```dax
Fraud Rate =
DIVIDE(
    [Fraud Transactions],
    [Total Transactions],
    0
)
```

## What I learned

The biggest thing I noticed was how **imbalanced** the dataset is: only 492 out of 284,807 transactions are labeled as fraud. A simple count chart can hide such a small group, so fraud rates and focused comparisons are useful.

While building this project, I practiced creating DAX measures, designing KPI cards, working with slicers, organizing report pages, and making charts easier to read. I also learned how to upload a large Power BI file to GitHub using Git LFS.

## How to open the project

1. Install [Power BI Desktop](https://www.microsoft.com/en-us/power-platform/products/power-bi/desktop).
2. Clone or download this repository. If cloning, install [Git LFS](https://git-lfs.com/) first so the Power BI file is downloaded correctly.
3. Open **`Credit_Card_Fraud_Dashboard.pbix`** in Power BI Desktop.
4. If Power BI asks for the CSV source, download the dataset from Kaggle, update the file path in **Transform data → Data source settings**, and refresh.

## Repository files

```text
Credit-Card-Fraud-Detection-Dashboard/
├── Credit_Card_Fraud_Dashboard.pbix
├── README.md
├── .gitattributes
├── .gitignore
└── screenshots/
    ├── Screenshot 2026-11-27 010151.png
    ├── Screenshot 2026-11-27 003448.png
    └── Screenshot 2026-11-27 003546.png
```

## Limitations and next steps

This dashboard describes transactions that are already labeled. It does **not** predict fraud in new transactions. Also, because V1–V28 are anonymized, I cannot explain exactly what each feature represents.

In the future, I'd like to try building a machine learning model on the same dataset and compare its results with the patterns I explored in Power BI.

---

**Made by CH.M.U.S**

[GitHub](https://github.com/Usmanshakir7) · [LinkedIn](https://www.linkedin.com/in/usman-shakir7/)
