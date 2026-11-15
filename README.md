
# 💳 Credit Card Fraud Analysis Dashboard | Power BI

An interactive **Power BI dashboard** designed to analyze credit card transactions, explore fraud patterns, and transform raw transaction data into meaningful insights.

## 📌 Project Overview

Credit card fraud is a major challenge in the financial industry. Analyzing transaction data can help identify patterns associated with fraudulent activities.

This project focuses on developing an interactive dashboard using **Microsoft Power BI** to explore historical credit card transactions and compare fraudulent and legitimate activities.

The dashboard provides an overview of transaction behavior, fraud rates, transaction amounts, and anonymized numerical features.

## 🎯 Project Objectives

- Analyze fraudulent and legitimate transactions.
- Calculate fraud rates and transaction statistics.
- Explore transaction amount distributions.
- Identify patterns in historical fraudulent transactions.
- Develop interactive data visualizations.
- Present findings through an organized Power BI dashboard.

## 📊 Dashboard Features

### 1. Executive Overview

Provides a high-level summary of transaction data.

**Key Performance Indicators (KPIs):**
- Total Transactions
- Fraud Transactions
- Legitimate Transactions
- Fraud Rate (%)
- Average Transaction Amount

**Visualizations:**
- Fraud vs. Legitimate Transactions
- Transaction Distribution
- Transaction Trends
- Transaction Amount Analysis

### 2. Fraud Pattern Analysis

Explores patterns and differences between fraudulent and legitimate transactions.

**Features:**
- Fraud Rate Comparisons
- Transaction Amount Analysis
- Elapsed-Time Transaction Trends
- V1–V5 Feature Comparisons
- Interactive Filters and Slicers

### 3. Transaction Explorer

Allows users to explore transaction-level information.

**Features:**
- Transaction Data Table
- Fraud and Legitimate Transaction Filtering
- Supporting Summary Charts
- Interactive Data Exploration

## 🛠️ Tools & Technologies

| Technology | Purpose |
|------------|---------|
| Power BI Desktop | Dashboard Development |
| Power Query | Data Import and Transformation |
| DAX | Measures and KPI Calculations |
| CSV | Dataset Format |
| GitHub | Version Control and Documentation |

## 📂 Dataset

This project uses the **Credit Card Fraud Detection Dataset**, available on Kaggle.

**Dataset Source:**
https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud

### Dataset Features

| Feature | Description |
|---------|-------------|
| Time | Seconds elapsed from the first transaction |
| V1–V28 | Anonymized numerical features |
| Amount | Transaction amount |
| Class | Transaction classification |

**Target Variable:**
- `0` = Legitimate Transaction
- `1` = Fraudulent Transaction

The dataset is highly imbalanced, with fraudulent transactions representing a very small percentage of total transactions.

## 📐 DAX Measures

The dashboard uses DAX measures to calculate important metrics.

### Total Transactions

```dax
Total Transactions = COUNTROWS('creditcard')
```

### Fraud Transactions

```dax
Fraud Transactions =
CALCULATE(
    COUNTROWS('creditcard'),
    'creditcard'[Class] = 1
)
```

### Legitimate Transactions

```dax
Legitimate Transactions =
CALCULATE(
    COUNTROWS('creditcard'),
    'creditcard'[Class] = 0
)
```

### Fraud Rate

```dax
Fraud Rate =
DIVIDE(
    [Fraud Transactions],
    [Total Transactions],
    0
)
```

Format the Fraud Rate measure as a percentage.

*Note: These are example implementations. The field and measure names should match the Power BI model.*

## 🚀 How to Run the Project

1. Clone or download this GitHub repository.
2. Install Microsoft Power BI Desktop.
3. Download the dataset from Kaggle.
4. Extract `creditcard.csv`.
5. Open `Credit_Card_Fraud_Dashboard.pbip` in Power BI Desktop.
6. Open Power Query.
7. Update the CSV source path to your local dataset location.
8. Apply changes and refresh the data.
9. Explore the interactive dashboard.

## 📁 Project Structure

```text
Credit-Card-Fraud-Analysis-Dashboard/
│
├── README.md
├── .gitignore
│
├── Credit_Card_Fraud_Dashboard.pbip
│
├── Credit_Card_Fraud_Dashboard.Report/
│
├── Credit_Card_Fraud_Dashboard.SemanticModel/
│
└── screenshots/
    ├── executive-overview.png
    ├── fraud-pattern-analysis.png
    └── transaction-explorer.png
```

## 📸 Dashboard Screenshots

### Executive Overview

![Executive Overview](screenshots/executive-overview.png)

### Fraud Pattern Analysis

![Fraud Pattern Analysis](screenshots/fraud-pattern-analysis.png)

### Transaction Explorer

![Transaction Explorer](screenshots/transaction-explorer.png)

*Screenshots should be added after verifying the report in Power BI Desktop.*

## 📚 Key Learning Outcomes

Through this project, I gained practical experience in:

- Data analysis and visualization.
- Creating interactive Power BI dashboards.
- Writing DAX measures.
- Data preparation using Power Query.
- Understanding imbalanced datasets.
- Building KPI cards and analytical charts.
- Communicating insights through dashboards.
- Managing and documenting projects on GitHub.

## ⚠️ Project Limitations

- The dashboard analyzes historical labeled transactions.
- It does not currently implement a machine learning prediction model.
- Anonymized features limit the interpretation of individual transaction characteristics.
- Dataset refresh requires access to the original CSV file.

## 🔮 Future Improvements

- Add advanced fraud pattern analysis.
- Implement drill-through reporting.
- Improve interactive filtering capabilities.
- Integrate Python-based fraud classification models.
- Experiment with machine learning techniques.
- Extend the dashboard with predictive analytics.

## 📌 Project Status

**Power BI dashboard developed — final Desktop verification required.**

The project contains editable report and semantic model files.

## 🤝 Connect With Me

I'm a Data Science undergraduate passionate about data analytics, machine learning, artificial intelligence, and solving real-world problems using data.

**LinkedIn:** https://www.linkedin.com/in/usman-shakir7/

**GitHub:** https://github.com/Usmanshakir7

---

⭐ If you find this project useful, consider giving the repository a star!
