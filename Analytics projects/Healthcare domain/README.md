# Healthcare Cost & Risk Optimization

## Objective

Analyze patient encounters, procedures, and payer coverage to surface financial risk from uncovered costs, identify patients with recurring high-cost encounters, and evaluate how much of each procedure's cost payers actually cover — supporting proactive cost control and patient risk stratification for healthcare organizations.

## Dataset

Synthetic electronic health records queried directly via SQL, spanning four core tables:

- `patients` — demographics (gender, birth date)
- `encounters` — visit-level records (claim cost, payer coverage, reason code, class, start/stop dates)
- `procedures` — procedures performed per encounter
- `payers` — payer/insurer details

No flat file is included in this folder — analysis runs directly against the relational tables via [`UtkarshRaj_healthcare_project_SQLAnalysis.sql`](UtkarshRaj_healthcare_project_SQLAnalysis.sql) and is visualized in [`UtkarshRaj_healthcare_project_Visual analysis.pbix`](UtkarshRaj_healthcare_project_Visual%20analysis.pbix).

## Key Insights

The six SQL analyses in this project surface:

1. **Financial risk by encounter reason** — ranks reason codes by total and average uncovered cost (claim cost minus payer coverage), alongside average patient age and most common gender per reason.
2. **Frequent high-cost patients** — flags patients with multiple encounters above a $10,000 claim-cost threshold within a year, useful for case-management prioritization.
3. **Demographic risk factors** — cross-references age and gender against encounter reasons to identify at-risk demographic segments.
4. **Payer contribution by procedure type** — measures how much of each procedure's cost is actually covered by payers versus billed to patients.
5. **Multi-procedure patients** — identifies patients undergoing multiple procedures across encounters, a proxy for care complexity.
6. **Encounter duration by class** — compares how long encounters take across visit classes (e.g., inpatient vs. outpatient vs. emergency) to spot process inefficiencies.

## Tech Stack

SQL · Power BI
