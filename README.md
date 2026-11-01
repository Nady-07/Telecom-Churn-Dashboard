# Telecom Customer Churn Dashboard

A 4-page Power BI report that shows **why telecom customers leave, how much revenue it costs, and where retention efforts should focus**. It is built on a star-schema data model and styled with the e& (Etisalat) brand look.

> **Data disclaimer:** The dataset is **synthetic** (7,043 simulated customer records, no real customer data). This is a portfolio project and is not affiliated with e& or Etisalat.

![Dashboard overview](images/01-overview-dark.png)

## Contents

- [Project goal](#project-goal)
- [Dashboard pages](#dashboard-pages)
- [Headline KPIs](#headline-kpis)
- [Key findings](#key-findings)
- [Recommendations](#recommendations)
- [Data model](#data-model)
- [Getting started](#getting-started)
- [Repository structure](#repository-structure)

## Project goal

Customer churn is one of the costliest problems for a telecom operator. This dashboard turns raw customer and billing data into clear answers for business stakeholders:

1. **Who** is leaving, and at what point in their lifecycle?
2. **What** does churn cost in revenue?
3. **Which** products, contracts and behaviors drive it?
4. **Where** should retention campaigns focus first?

Each visual is titled as a business question with a one-line answer beneath it, so the story can be read without any explanation.

## Dashboard pages

| # | Page | What it covers |
|---|------|----------------|
| 1 | **Overview** | Churn by contract type, tenure, internet service and payment method, plus the effect of tech support and phone service |
| 2 | **Revenue Impact & Risk Mitigation** | Revenue lost by contract, service and payment method; churn across customer value tiers; where to focus retention campaigns |
| 3 | **Customer Demographics & Value Bundling Optimization** | Churn by family status, gender and billing type; the effect of add-on services, bundles and service combinations |
| 4 | **Overview Bright** | The Overview page in a light theme |

## Headline KPIs

| Metric | Value |
|---|---|
| Total customers | 7,043 |
| Churned customers | 1,869 |
| Churn rate | 26.5% |
| Total revenue | $16.06M |
| Revenue lost to churn | $2.86M (17.83% of total) |
| High-value customers churned | 255 |
| Revenue at risk | $136.45K |

## Key findings

| Driver | What the data shows |
|---|---|
| **Contract type** | Month-to-month customers churn at **42.71%**, against 11.27% on one-year and about 3% on two-year contracts. Month-to-month accounts for over 67% of lost revenue ($1.93M). |
| **Tenure** | Churn peaks at **47.4% in the first 12 months** and falls steadily as tenure grows. |
| **Internet service** | Fiber optic churns at **41.89%** and accounts for $2.48M of lost revenue. Active month-to-month fiber customers are the largest forward-looking risk ($85K). |
| **Payment method** | Electronic-check customers churn at **45.3%**, against under 17% for automatic payment, and make up over 54% of lost revenue. |
| **Support and add-ons** | Tech support cuts churn from 41.6% to 15.2%. Churn drops from 50.3% with no add-ons to under 6% for customers with the most. |
| **Household and billing** | Single customers churn at 34.2% against 14.2% for families. Paperless-billing customers churn at 33.6%, about double the rate of the rest. |
| **Not a driver** | Gender and phone service show almost no difference in churn. |

## Recommendations

Based on the findings above:

1. **Target month-to-month fiber customers first.** They are the highest-risk and highest-value segment for retention offers.
2. **Invest in the first year.** Onboarding and early-life engagement matter most when churn is highest.
3. **Move customers to contracts and auto-pay.** Offer incentives to switch from month-to-month plans and manual electronic checks.
4. **Promote tech support and bundled add-ons.** Both are linked to much lower churn.
5. **Do not segment by gender or phone service.** They don't separate churners from stayers.

## Screenshots

| Revenue Impact & Risk Mitigation | Customer Demographics & Bundling |
|---|---|
| ![Revenue impact and risk mitigation](images/02-revenue-impact-risk-mitigation.png) | ![Customer demographics and bundling](images/03-customer-demographics-bundling.png) |

**Light theme**

![Overview in light theme](images/04-overview-light.png)

## Data model

The report uses a **star schema**:

| Table | Role |
|---|---|
| `fact_Billing_Churn` | Fact table with billing and churn data per customer |
| `dim_Customer` | Customer attributes |
| `dim_Contract` | Contract details |
| `dim_Service` / `dim_Service_Unpivoted` | Services and add-ons |
| `_Measures` | Dedicated table for DAX measures |

**Built with:** Power BI Desktop, DAX, a custom crimson theme, bookmarks and a filter panel.

## Getting started

1. Clone or download this repository.
2. Open `Telecom_Churn.pbix` in [Power BI Desktop](https://powerbi.microsoft.com/desktop/) (free for Windows).
3. Use the filter button at the top left of each page to slice the data.

## Repository structure

```
Telecom-Churn-Dashboard/
├── Telecom_Churn.pbix   # Power BI report
├── images/              # Dashboard screenshots
└── README.md
```
