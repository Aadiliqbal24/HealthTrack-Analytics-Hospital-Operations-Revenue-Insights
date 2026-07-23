# Hospital Management Data Analysis (SQL + Power BI Project)

An end-to-end data analytics portfolio project built on a hospital
management dataset — modeled as a star schema (4 dimension tables + 1
fact table), analyzed with **Snowflake SQL** (joins, subqueries, CTEs,
window functions), and visualized with an interactive **Power BI
dashboard**.

## Dataset Overview

| Table              | Rows | Description                                   |
|--------------------|------|------------------------------------------------|
| `Dim_Patient`      | 100  | Patient demographics (name, gender, DOB, city, state, blood group, registration date) |
| `Dim_Doctor`       | 21   | Doctor details (name, specialization, department, experience, consultation fee) |
| `Dim_Department`   | 8    | Hospital departments (Cardiology, Orthopedics, Neurology, Pediatrics, General Medicine, Dermatology, ENT, Gynecology) |
| `Dim_Date`         | 366  | Date dimension for 2024 (day/month/quarter/year/weekday) |
| `Fact_Appointment` | 5000 | Appointments (type, status, treatment, cost, billing, payment mode/status, links to patient/doctor/department/date) |

**Schema type:** Star schema — `Fact_Appointment` is the fact table,
joined to `Dim_Patient`, `Dim_Doctor`, and `Dim_Date`; `Dim_Doctor` in
turn links to `Dim_Department`.

```
Dim_Department ──< Dim_Doctor ──< Fact_Appointment >── Dim_Patient
                                        v
                                    Dim_Date
```

## Project Structure

```
├── data/
│   ├── Dim_Patient.csv
│   ├── Dim_Doctor.csv
│   ├── Dim_Department.csv
│   ├── Dim_Date.csv
│   └── Fact_Appointment.csv
├── sql/
│   ├── 01_schema.sql                  -- CREATE TABLE statements (with PK/FK)
│   ├── 02_business_questions.sql      -- 26 business questions + queries
│   ├── business_questions_list.md     -- questions only, no queries
│   └── my_queries.sql                 -- final queries as run in Snowflake
├── powerbi/
│   ├── Hospital_Dashboard.pbix                     -- Power BI file
│   ├── powerbi_dashboard_analysis.md               -- worked analysis per visual
│   └── screenshots/
│       └── hospital_performance_overview.png
└── README.md
```

## How to Run (Snowflake)

1. Open a Snowflake worksheet.
2. Run `sql/01_schema.sql` to create the database, schema, and all 5 tables.
3. Stage and load the 5 CSVs from `data/` in this order (parents before
   the fact table): `Dim_Department` → `Dim_Doctor` → `Dim_Patient` →
   `Dim_Date` → `Fact_Appointment`.
4. Verify row counts: 8 / 21 / 100 / 366 / 5000.
5. Run `sql/02_business_questions.sql` (or `sql/my_queries.sql`) to
   reproduce the analysis.

## Business Questions Answered

**26 business questions** (`sql/02_business_questions.sql`), grouped by difficulty:

**A. Basic filtering & sorting** — patients by state, completed appointments, high-billing cases, gender split, doctor experience

**B. Joins & aggregation** — department revenue, doctor workload, average treatment cost by type, patient visit frequency, monthly volume & revenue, cancellation/no-show rate by department

**C. Subqueries & HAVING** — high-revenue departments, above-average doctors, patients with zero completed visits, top 5 patients by spend

**D. CASE statements & date functions** — cost tiers, patient age groups, yearly registrations, weekday footfall

**E. Window functions & CTEs** — doctor rank within department, running revenue totals, top-earning doctor per department, month-over-month growth %, patient visit leaderboard

## Power BI Dashboard


**Dashboard includes:**
- Executive KPIs: Total Revenue, Total Appointments, Average Treatment Cost, No-Show Rate
- Revenue by department (bar chart)
- Appointment status breakdown — Completed / Cancelled / No-show (donut)
- Monthly revenue trend (line chart)
- Doctor performance table: revenue, appointment count, average treatment cost, no-show rate per doctor
- Slicers: Metrics, City, Quarter, Gender



**Key findings:**
- No-shows + cancellations account for ~20% of all scheduled appointments — the biggest operational improvement opportunity.
- Revenue is fairly evenly spread across departments, with Gynecology and General Medicine leading.
- Doctor performance splits into two patterns: volume-driven (high appointment count) vs value-driven (higher cost per visit).

## Tech Stack
- **Database:** Snowflake
- **Visualization:** Power BI
- **SQL concepts used:** DDL, FK relationships, joins, GROUP BY/HAVING,
  correlated & non-correlated subqueries, CASE expressions, date functions,
  CTEs, window functions (RANK, DENSE_RANK, LAG, running SUM)
- **Power BI concepts used:** DAX measures, slicers, KPI cards, donut/bar/
  line charts, conditional-formatted tables

## Notes
- All SQL queries were run and verified in Snowflake before publishing.
- Screenshots were captured with all filters reset to "All" so the numbers
  reflect the full dataset.
