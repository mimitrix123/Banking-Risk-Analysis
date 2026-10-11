# 🏦 Banking Credit Risk & Loan Default Analysis

**AICTE | IBM SkillsBuild Data Analytics with AI Academic Internship 2026 | BharatCares**

| Field | Details |
|---|---|
| **Author** | Mamashri Gupta |
| **Primary Tool** | IBM Bob |
| **Language** | Python 3 |
| **Environment** | Jupyter Notebook |
| **Sector** | Banking & Financial Services |
| **Dataset** | Synthetic — 5,000 records, seed=42 |

---

## 📋 Project Overview

This project delivers a complete, professional, reproducible banking-sector data analytics project
that analyses loan applications, borrower characteristics, repayment behaviour, credit risk and
loan defaults.

The project was built end-to-end using **IBM Bob** (AI-assisted development) and submitted as the
final project for the AICTE IBM SkillsBuild Data Analytics with AI Academic Internship 2026.

---

## 🎯 Business Problem & Objectives

**Problem:** Loan defaults are one of the most significant sources of financial loss for retail
banks. When a borrower fails to repay a loan, the bank must write off the outstanding balance
as a Charged-Off (bad) debt, impacting profitability and capital adequacy.

**Objectives:**
1. Identify borrower and loan characteristics most strongly associated with default.
2. Quantify the total financial exposure from defaults.
3. Segment borrowers by risk level (High Risk / Low Risk).
4. Provide evidence-based recommendations for banking risk-management teams.

---

## 📊 Dataset Description & Source

| Property | Value |
|---|---|
| **File** | `data/banking_credit_risk.csv` |
| **Nature** | **SYNTHETIC** — programmatically generated, NOT real customer data |
| **Records** | 5,000 loans |
| **Columns** | 15 |
| **Date range** | January 2018 – December 2023 |
| **Random seed** | 42 (fully reproducible) |
| **Licence** | Creative Commons CC0 1.0 Universal (public domain) |

The dataset was generated using Python (`numpy`, `pandas`) with a fixed random seed to ensure
full reproducibility. It mimics realistic distributions of loan characteristics and default
behaviour in retail banking.

See [`data/DATA_SOURCE.md`](data/DATA_SOURCE.md) for the complete data dictionary and generation
methodology.

---

## 🛠️ Technologies & Libraries

| Tool / Library | Version | Purpose |
|---|---|---|
| Python | 3.9+ | Core programming language |
| pandas | ≥1.5.0 | Data manipulation and analysis |
| numpy | ≥1.23.0 | Numerical computing, random data generation |
| matplotlib | ≥3.6.0 | Data visualisation |
| seaborn | ≥0.12.0 | Statistical visualisation |
| Jupyter Notebook | ≥1.0.0 | Interactive development environment |
| ipykernel | ≥6.0.0 | Jupyter Python kernel |
| IBM Bob | — | AI-assisted development (primary tool) |

---

## 📁 Project Folder Structure

```
IBM-BOB-Banking-Credit-Risk-Analysis/
├── MamashriGupta_BankingRiskAnalysis.ipynb   ← Jupyter Notebook (main analysis)
├── requirements.txt                           ← Python dependency list
├── MamashriGupta_BankingRiskAnalysis_Report.docx  ← Professional Word report
├── README.md                                  ← This file
└── data/
    ├── banking_credit_risk.csv                ← Synthetic dataset (5,000 records)
    └── DATA_SOURCE.md                         ← Dataset documentation & data dictionary
```

---

## ⚙️ Installation & Setup

### Prerequisites
- Python 3.9 or later ([download](https://www.python.org/downloads/))
- pip (included with Python)

### Step 1 — Clone or download the repository

```bash
git clone https://github.com/<your-username>/IBM-BOB-Banking-Credit-Risk-Analysis.git
cd IBM-BOB-Banking-Credit-Risk-Analysis
```

Or download and extract the ZIP file from GitHub, then open a terminal in the extracted folder.

### Step 2 — (Recommended) Create a virtual environment

```bash
# Windows
python -m venv venv
venv\Scripts\activate

# macOS / Linux
python3 -m venv venv
source venv/bin/activate
```

### Step 3 — Install dependencies

```bash
pip install -r requirements.txt
```

This installs: `pandas`, `numpy`, `matplotlib`, `seaborn`, `jupyter`, `ipykernel`.

---

## 🚀 Running the Notebook

### Launch Jupyter Notebook

```bash
jupyter notebook
```

This opens Jupyter in your browser. Click on
`MamashriGupta_BankingRiskAnalysis.ipynb` to open the notebook.

### Run all cells from start to finish

In the Jupyter menu:
```
Kernel → Restart & Run All
```

Or run cells individually from top to bottom using **Shift+Enter**.

> ⚠️ **Important:** Open the notebook from the project root directory
> (`IBM-BOB-Banking-Credit-Risk-Analysis/`) so that the relative path
> `data/banking_credit_risk.csv` resolves correctly.

### Dataset note

The dataset file `data/banking_credit_risk.csv` is included in the repository.
If it is missing for any reason, Cell 2 of the notebook will automatically regenerate
it using the fixed seed (42), ensuring identical results.

---

## 📈 Key Metrics & Findings

All values below were calculated directly from the dataset in the notebook.
They are fully reproducible by running the notebook with seed=42.

### Portfolio KPIs

| KPI | Value |
|---|---|
| Total Loan Applications | 5,000 |
| Fully Paid | 3,834 (76.7%) |
| Charged Off (Defaults) | 729 (14.6%) |
| Current (Active) | 340 (6.8%) |
| Late 31-120 days (At-Risk) | 97 (1.9%) |
| **Default Rate** (Charged Off / Closed-Outcome) | **15.98%** |
| Total Loan Principal | $107,483,929.04 |
| Outstanding Exposure (non-paid loans) | $11,493,720.25 |
| **Charged-Off Balance** | **$7,262,670.05** |
| Average Loan Amount | $21,496.79 |
| Average Interest Rate | 8.33% |
| Average Credit Score | 680.0 |
| Average Annual Income | $66,926.21 |
| Average DTI Ratio | 0.1348 |
| Late Loan Exposure (at-risk) | $1,166,624.69 |

> **Default Rate Denominator:** Closed-outcome loans (Fully Paid + Charged Off) only.
> Current and Late loans are excluded as their final outcomes remain uncertain.

### Key Findings

1. **Credit score is the strongest predictor** — Very Poor (300-579) borrowers default at
   >3× the portfolio average. Strong negative correlation between credit score and default.
2. **Income matters** — Borrowers earning <$30K default at significantly above-average rates.
3. **Unemployed borrowers carry the highest risk** — Default rate nearly double the average.
4. **Vacation and Business loans are highest-risk by purpose** — above-average default rates.
5. **Debt Consolidation loans drive the highest charged-off balance** — high volume × moderate rate.
6. **60-month loans have higher default rates** than shorter-term products.

---

## 📉 Visualisations Produced (10 charts)

| # | Chart | Key Insight |
|---|---|---|
| 1 | Loan Status Distribution (bar + pie) | 76.7% Fully Paid, 14.6% Charged Off |
| 2 | Default Rate by Loan Purpose | Vacation > Business > Portfolio avg |
| 3 | Default Rate by Credit Score Band | Clear inverse relationship |
| 4 | Default Rate by Annual Income Band | Lower income → higher default rate |
| 5 | Default Rate by Employment Status | Unemployed >> all others |
| 6 | Financial Exposure (purpose + segment) | Debt Consolidation largest absolute loss |
| 7 | Default Trend Over Time (2018-2023) | Stable trend, year-over-year view |
| 8 | Correlation Heatmap | Interest rate (+), Credit Score (-) strongest |
| 9 | High-Risk vs Low-Risk Segment | Multi-metric side-by-side comparison |
| 10 | Default Rate by Loan Term | 60-month highest default rate |

---

## 📋 Expected Outputs

When the notebook is run end-to-end, it produces:
- Printed validation results for all 8 data quality checks (all pass ✅).
- Printed KPI summary table.
- 10 matplotlib/seaborn charts rendered inline.
- Final reconciliation printout matching the report KPIs.
- Terminal message: `✅ Notebook executed successfully. All cells ran without errors.`

---

## 🚦 Limitations & Responsible Use

1. **Synthetic data only** — This dataset was programmatically generated. It does NOT represent
   real customers, real banks, or real financial transactions. Do not make real lending decisions
   based on this analysis.
2. **No macroeconomic factors** — GDP cycles, interest rate environments and systemic shocks are
   not modelled.
3. **Static snapshot** — Each loan has a single observation point. Real credit risk analysis
   requires longitudinal (vintage) data.
4. **Descriptive analytics only** — No machine learning model is included. A predictive model
   would be needed for production credit-decisioning.
5. **Privacy** — All borrower IDs are fictional (CUST000001 format). No personally identifiable
   information (PII) is present.

---

## 📤 Submission Files (AICTE IBM SkillsBuild Form)

The internship submission form requires four separate file uploads:

| Form Field | Local File | Size |
|---|---|---|
| Code File (.ipynb) | `MamashriGupta_BankingRiskAnalysis.ipynb` | ~1 MB (with outputs) |
| Requirements File (.txt) | `requirements.txt` | <1 KB |
| Project Report (.docx) | `MamashriGupta_BankingRiskAnalysis_Report.docx` | ~50 KB |
| README File (.md) | `README.md` | ~7 KB |

The GitHub repository URL should also be provided in the form's GitHub field.

---

## 🐙 Publishing to GitHub

```bash
# 1. Create a new repository on GitHub (public, no README template)

# 2. Initialise git in the project folder
cd IBM-BOB-Banking-Credit-Risk-Analysis
git init
git add .
git commit -m "Initial commit: Banking Credit Risk Analysis — Mamashri Gupta"

# 3. Link to your GitHub repository and push
git remote add origin https://github.com/<your-username>/IBM-BOB-Banking-Credit-Risk-Analysis.git
git branch -M main
git push -u origin main
```

Replace `<your-username>` with your actual GitHub username.

---

## 👤 Author

**Mamashri Gupta**  
AICTE | IBM SkillsBuild Data Analytics with AI Academic Internship 2026 | BharatCares  
Primary Tool: IBM Bob

---

*This project was created using IBM Bob as the primary AI development tool.*
