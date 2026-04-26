# 🏦 Banking Customer Analytics — EDA & Power BI Dashboard

> An end-to-end data analytics project exploring customer financial behaviour across banking products using Python (Exploratory Data Analysis) and Power BI (interactive dashboard).

---

## 📋 Table of Contents

- [Project Overview](#project-overview)
- [Business Objective](#business-objective)
- [Dataset](#dataset)
- [Project Structure](#project-structure)
- [Tech Stack](#tech-stack)
- [Exploratory Data Analysis](#exploratory-data-analysis)
- [Power BI Dashboard](#power-bi-dashboard)
- [Key Insights](#key-insights)
- [How to Run](#how-to-run)
- [Author](#author)

---

## Project Overview

This project performs a comprehensive analysis of banking customer data to uncover patterns in savings behaviour, income distribution, loan portfolios, and demographic profiles. The analysis is conducted in two layers:

1. **Python EDA** (`BankEDA.ipynb`) — data cleaning, statistical exploration, and visual correlation analysis.
2. **Power BI Dashboard** (`Banking_Dashboard.pbix`) — interactive, business-ready reporting for stakeholder consumption.

---

## Business Objective

Banks accumulate rich customer data that often goes underutilised. This project aims to:

- Understand how demographic factors (age, income, nationality, occupation) influence financial product holdings.
- Identify relationships between deposits, savings, loans, and credit balances.
- Segment customers by income band and loyalty classification to support targeted strategies.
- Surface actionable insights for customer retention and cross-sell opportunities.

---

## Dataset

**File:** `Banking.csv`

The dataset contains customer-level banking records with the following key attributes:

| Category | Columns |
|---|---|
| **Demographics** | Age, Nationality, Occupation, Properties Owned |
| **Financial Products** | Bank Deposits, Saving Accounts, Checking Accounts, Foreign Currency Account, Business Lending, Bank Loans, Credit Card Balance, Superannuation Savings |
| **Classification** | Risk Weighting, Loyalty Classification, Income Band, Fee Structure |
| **Temporal** | Joined Bank (date) |

> **Income Band** is a derived feature engineered during EDA:
> - `Low` → Estimated Income < ₹1,00,000
> - `Mid` → ₹1,00,000 – ₹3,00,000
> - `High` → > ₹3,00,000

---

## Project Structure

```
banking-customer-analytics/
│
├── Banking-Customer-presentation.pdf               # Project Presentation
├── BankEDA.ipynb                                   # Python Exploratory Data Analysis notebook
├── Banking_Dashboard.pbix                          # Power BI interactive dashboard
├── Banking.csv                                     # Source dataset (add if sharing publicly)
└── README.md                                       # Project documentation
```

---

## Tech Stack

| Tool | Purpose |
|---|---|
| **Python 3.x** | Data processing and EDA |
| **Pandas** | Data manipulation and aggregation |
| **NumPy** | Numerical computations |
| **Matplotlib & Seaborn** | Statistical visualisations |
| **Power BI Desktop** | Interactive business dashboard |

---

## Exploratory Data Analysis

The Jupyter notebook (`BankEDA.ipynb`) covers the full EDA pipeline:

**1. Data Loading & Inspection**
- Shape and schema review
- Data type validation (`Joined Bank` parsed to datetime)
- Missing value audit

**2. Feature Engineering**
- `Income Band` created using `pd.cut()` with custom bin thresholds

**3. Univariate Analysis**
- Distribution plots (histogram + KDE) for all numerical columns: Age, Estimated Income, Superannuation Savings, Credit Card Balance, Bank Loans, Bank Deposits, Checking Accounts, Saving Accounts, Foreign Currency Account, Business Lending
- Value counts for categorical columns: Risk Weighting, Nationality, Occupation, Fee Structure, Loyalty Classification, Income Band

**4. Bivariate & Correlation Analysis**
- Pearson correlation heatmap across 11 numerical features
- Regression scatter plots for 7 strategically selected variable pairs:
  - Bank Deposits vs Saving Accounts
  - Checking Accounts vs Saving Accounts
  - Checking Accounts vs Foreign Currency Account
  - Age vs Superannuation Savings
  - Estimated Income vs Checking Accounts
  - Bank Loans vs Credit Card Balance
  - Business Lending vs Bank Loans

---

## Power BI Dashboard

The `Banking_Dashboard.pbix` file provides an interactive executive-level view of the data with:

- Customer segmentation by income band, loyalty tier, and risk weighting
- Geographic and occupational breakdown of account holders
- Portfolio analysis across banking products
- Trend views using the `Joined Bank` date field

> Open with **Power BI Desktop** (free download from [Microsoft](https://powerbi.microsoft.com/desktop/)).

---

## Key Insights

**Deposits & Savings Behaviour**
Customers who actively deposit funds tend to maintain higher saving account balances — suggesting these variables capture overlapping wealth-accumulation behaviour. Banks may leverage this to offer bundled savings products.

**Income, Age & Financial Accumulation**
Older and higher-income customers hold larger superannuation, savings, and checking balances — consistent with standard financial lifecycle theory. This cohort is a prime target for premium banking tiers.

**Property Ownership — Weakly Correlated**
Property ownership shows low correlation with banking metrics, likely driven by external factors (real estate markets, inheritance, geography) not captured in transactional data.

**Business vs. Personal Lending**
Business lending has a moderate overlap with personal bank loans, pointing to a segment of dual-debt customers. However, business lending is largely decoupled from deposit and property metrics, indicating a distinct customer sub-segment that warrants dedicated product strategies.

---

## How to Run

**Python Notebook**

```bash
# 1. Clone the repository
git clone https://github.com/avisaini764/banking-customer-analytics.git
cd banking-customer-analytics

# 2. Install dependencies
pip install pandas numpy matplotlib seaborn jupyter

# 3. Launch the notebook
jupyter notebook BankEDA.ipynb
```

> Make sure `Banking.csv` is in the same directory as the notebook.

**Power BI Dashboard**

1. Download and install [Power BI Desktop](https://powerbi.microsoft.com/desktop/).
2. Open `Banking_Dashboard.pbix`.
3. If prompted, update the data source path to point to your local `Banking.csv`.

---

## Author

**Avi Saini**
Data Analyst | Python · SQL · Power BI

[![GitHub](https://img.shields.io/badge/GitHub-avisaini764-black?logo=github)](https://github.com/avisaini764)

---

*Feel free to fork this repository, raise issues, or suggest improvements via pull requests.*
