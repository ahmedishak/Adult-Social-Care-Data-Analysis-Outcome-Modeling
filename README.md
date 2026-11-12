<img width="1657" height="851" alt="Adult Social Care Financial   Outcomes" src="https://github.com/user-attachments/assets/c6557aca-6598-4600-a4ab-7c134d17f616" />
# Adult Social Care: Financial & Outcome Intelligence Suite 📊

## 📌 Project Overview

This project explores Adult Social Care (ASC) expenditure and service outcomes through an end-to-end data analytics pipeline, combining SQL, Excel Power Query, and Tableau to transform raw administrative data into actionable insights.

The analysis focuses on identifying regional spending variations, exploring relationships between socio-economic deprivation and care costs, and evaluating the impact of informal carer support on individual independence outcomes.

The primary objective is to support evidence-based decision-making by highlighting areas of financial pressure, identifying potential gaps in preventative care, and informing opportunities for more effective resource allocation across Adult Social Care services.

## 🛠️ Technical Stack

| Technology | Purpose |
|---|---|
| **SQL** | Data extraction, aggregation, querying and analytical modelling |
| **Excel Power Query** | Data cleaning, transformation, standardisation and validation |
| **Tableau** | Interactive dashboards, data visualisation and insight generation |

---

## 1. Data Analysis & SQL Development

SQL was used to extract, aggregate and analyse the underlying dataset, focusing on three key analytical areas.

### A. Regional Expenditure Analysis

Identified geographical variations in weekly care expenditure to highlight potential spending hotspots and areas requiring further financial investigation.

```sql
SELECT
    ward,
    SUM(weekly_cost_gbp) AS total_weekly_spend
FROM care_data
GROUP BY ward
ORDER BY total_weekly_spend DESC;
```

### B. Socio-Economic Cost Analysis

Examined the relationship between Index of Multiple Deprivation (IMD) deciles and average weekly care expenditure to understand how care costs vary across different socio-economic groups.

```sql
SELECT
    deprivation_decile,
    AVG(weekly_cost_gbp) AS average_weekly_cost
FROM care_data
GROUP BY deprivation_decile
ORDER BY deprivation_decile ASC;
```

### C. Care Outcome Effectiveness

Investigated the relationship between recorded carer support and improved independence outcomes, using resident counts to compare outcome distributions.

```sql
SELECT
    carer_flag,
    outcome_improved_independence,
    COUNT(person_id) AS resident_count
FROM care_data
GROUP BY
    carer_flag,
    outcome_improved_independence
ORDER BY resident_count DESC;
```

---

## 2. Data Transformation & Governance

Excel Power Query was used as the primary ETL (Extract, Transform, Load) tool to prepare and standardise the dataset before its integration into Tableau.

The transformation process focused on improving data consistency, analytical accuracy and reporting reliability.

### Key Transformation Activities

- **Source Integration:** Imported structured SQL outputs in CSV format to establish a repeatable data preparation workflow.
- **Categorical Standardisation:** Consolidated over 12 variations of independence outcome descriptions into a consistent three-category classification: `Yes`, `Partial` and `No`.
- **Data Type Standardisation:** Converted deprivation deciles into integer values and standardised financial fields to support accurate numerical analysis.
- **Geographical Normalisation:** Cleaned inconsistent ward naming conventions to ensure geographical data was consistently categorised.
- **Feature Engineering:** Created standardised binary classifications for carer status to support comparative outcome analysis.
- **Missing Value Management:** Reviewed missing values in deprivation and carer status fields to minimise their impact on analytical results.
- **Data Integrity Validation:** Compared row counts and aggregate totals against the original SQL outputs to verify data consistency throughout the ETL process.

These steps established a consistent analytical dataset and reduced inconsistencies in the final reporting process.

---

## 3. Interactive Tableau Dashboard

An interactive Tableau dashboard was developed to communicate the financial and service outcome findings through accessible visualisations.

### Dashboard Components

**📍 Geographical Expenditure Map**

A ward-level representation of total weekly Adult Social Care expenditure, highlighting geographical concentrations of spending and potential areas for further investigation.

**📈 Deprivation & Cost Analysis**

A trend analysis comparing average weekly care expenditure across IMD deprivation deciles (1–10), exploring variations in spending across socio-economic groups.

**🔥 Independence Outcome Heatmap**

A comparative visualisation examining the relationship between informal carer support and recorded independence outcomes.

The dashboard brings together financial and operational indicators to support more informed strategic decision-making.

---

## 4. Key Findings & Strategic Insights

The analysis identified several patterns with potential implications for Adult Social Care commissioning, financial planning and preventative services.

### 1. Hazel Grove – Regional Spending Outlier

Hazel Grove recorded the highest identified weekly expenditure concentration at **£9,045 per week**.

This highlights a potential area for further investigation, including provider-rate comparisons, service demand and the distribution of care packages.

**Strategic implication:** Consider a targeted review of commissioning arrangements and local expenditure drivers.

### 2. The Deprivation Decile 7 Spending Peak

Average weekly care expenditure peaked at **£819 in deprivation decile 7**, challenging the assumption that care expenditure necessarily increases in line with deprivation.

This suggests that care demand and associated costs may be influenced by additional factors, including service accessibility, individual circumstances and the timing of intervention.

**Strategic implication:** Further investigate whether residents in less deprived areas are accessing services at later stages of need, potentially indicating opportunities for earlier intervention.

### 3. Informal Carer Support & Independence Outcomes

Residents with recorded carer support demonstrated a higher likelihood of achieving improved independence outcomes within the dataset.

This highlights the potential contribution of informal care networks to maintaining independence and supporting individuals receiving Adult Social Care services.

**Strategic implication:** Strengthen the evidence base for carer support initiatives and consider the role of informal care in longer-term service planning.

*Note: These findings identify associations within the dataset and should not be interpreted as proof of causation.*

---

## 5. Future Development Roadmap

Several opportunities have been identified to extend the project beyond retrospective analysis.

| Development Area | Proposed Enhancement |
|---|---|
| **Live Data Integration** | Replace static CSV imports with a live SQL Server connection to support more frequent reporting. |
| **Predictive Analytics** | Develop forecasting models using historical expenditure patterns to support 2026/27 budget planning. |
| **Data Quality Improvement** | Investigate the 22% gap in recorded carer status and introduce improved data validation processes. |
| **Advanced Analytics** | Explore additional relationships between deprivation, service demand, expenditure and independence outcomes. |

---

## 6. Skills Demonstrated

This project demonstrates practical experience across the data analytics lifecycle, including:

- SQL querying, aggregation and analytical data modelling.
- ETL development and transformation using Excel Power Query.
- Data cleaning, standardisation and quality assurance.
- Socio-economic and financial data analysis.
- KPI development and comparative analysis.
- Interactive dashboard development using Tableau.
- Translating analytical findings into actionable business recommendations.
- Communicating complex data insights to support strategic decision-making.

---

## 🎯 Project Outcome

The Adult Social Care Financial & Outcome Intelligence Suite demonstrates how fragmented administrative data can be transformed into meaningful financial and operational intelligence.

By combining SQL-based analysis, structured ETL processes and interactive Tableau reporting, the project provides a framework for exploring expenditure patterns, understanding service outcomes and identifying opportunities to improve resource allocation and service planning.
