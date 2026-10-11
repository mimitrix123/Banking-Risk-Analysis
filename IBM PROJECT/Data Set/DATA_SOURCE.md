# Dataset Source and Attribution

## Dataset Name
Banking Credit Risk & Loan Default Analysis — Synthetic Dataset

## File
`data/banking_credit_risk.csv`

## Nature of Data
**SYNTHETIC** — This dataset was programmatically generated using Python (`numpy`, `pandas`) with
a fixed random seed (`np.random.seed(42)`) to ensure full reproducibility.  
It does **not** represent real customer records, real borrowers, or any real financial institution.  
It was created solely for the purpose of this academic internship project.

## Why Synthetic Data Was Used
External data retrieval from Kaggle or other repositories is not available in the current
execution environment. As required by the project prompt (Section 4), the dataset is clearly
labelled as synthetic and all analysis is performed exclusively on this generated data.

## Dataset Characteristics
| Property | Value |
|---|---|
| Number of records | 5,000 |
| Number of columns | 15 |
| Date range | 2018-01 to 2023-12 |
| Random seed | 42 (fully reproducible) |

## Columns and Data Dictionary

| Column | Type | Description |
|---|---|---|
| `loan_id` | string | Unique loan identifier (LN000001 … LN005000) |
| `customer_id` | string | Anonymised borrower ID (CUST000001 … CUST005000) |
| `origination_date` | date (YYYY-MM-DD) | Loan origination date |
| `loan_amount` | float | Principal loan amount disbursed (USD) |
| `loan_term_months` | integer | Loan repayment term in months (12 / 24 / 36 / 48 / 60) |
| `interest_rate` | float | Annual interest rate (%) |
| `annual_income` | float | Borrower's annual income (USD) |
| `credit_score` | integer | Borrower's credit score (300 – 850, FICO-style) |
| `employment_status` | string | Full-Time / Part-Time / Self-Employed / Unemployed / Retired |
| `employment_length_years` | integer | Years of current employment (0 – 30) |
| `loan_purpose` | string | Home Improvement / Debt Consolidation / Medical / Education / Auto / Business / Personal / Vacation |
| `loan_status` | string | Fully Paid / Charged Off / Current / Late (31-120 days) |
| `outstanding_balance` | float | Remaining balance at observation date (USD) |
| `monthly_payment` | float | Scheduled monthly instalment (USD) |
| `months_elapsed` | integer | Number of months since origination at observation |

## Loan Status Definitions
| Status | Meaning | Default? |
|---|---|---|
| Fully Paid | Loan has been repaid in full | No |
| Charged Off | Borrower defaulted; bank wrote off the loan | **Yes** |
| Current | Loan is active and payments are on time | Ongoing |
| Late (31-120 days) | Payments are 31–120 days overdue | At-risk |

**Default Indicator:** `loan_status == 'Charged Off'`  
The default rate denominator used throughout this project is all loans with a **known final
outcome** (Fully Paid + Charged Off), consistent with standard banking practice.

## Generation Script
The dataset was generated inline within the Jupyter Notebook (Cell 3) and is saved at
`data/banking_credit_risk.csv` relative to the project root.

## Licence
This synthetic dataset is released under the **Creative Commons CC0 1.0 Universal** (public domain)
licence. You may use, copy, modify and distribute it freely for any purpose without attribution.

## References
The default-probability model and loan characteristics are inspired by publicly documented
patterns from the LendingClub loan dataset (Kaggle, CC BY 4.0) and academic literature on
consumer credit risk, but **no real LendingClub records were used or reproduced**.
