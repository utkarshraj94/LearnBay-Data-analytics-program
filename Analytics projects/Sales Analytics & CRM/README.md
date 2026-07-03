# Sales Performance & CRM Analytics

## Objective

Analyze CRM sales-pipeline data to identify what drives deal success, why deals are lost, which accounts are at risk of churn, and how revenue fluctuates seasonally — giving sales teams, managers, and business leaders a data-driven view to prioritize deals, refine strategy, and forecast retention risk.

## Dataset

Four related tables from a CRM sales-pipeline export:

| Table | Description |
|---|---|
| `accounts` | Company profile — sector, year established, revenue, employee count, HQ location, parent company |
| `products` | Product name, series, list price |
| `sales_teams` | Sales agent, manager, regional office |
| `sales_pipeline` | Opportunity-level records — agent, product, account, deal stage, engage/close dates, close value |

Analyzed via [`Utkarsh_raj_Sales_analytics.sql`](Utkarsh_raj_Sales_analytics.sql) and visualized in [`Utkarsh_raj_Sale_analytics.pbix`](Utkarsh_raj_Sale_analytics.pbix); full write-up in [`Analysis report`](Analysis%20report).

## Key Insights

The SQL analysis surfaces:

- **High-value deal segmentation** — classifies deals into high/mid/low-value percentile bands and identifies which agents close the most high-value deals.
- **Pipeline velocity** — flags accounts moving unusually slowly or quickly through deal stages, highlighting bottlenecks in the Prospecting → Engaging → Won/Lost funnel.
- **Deal-closing time by industry** — compares average days-to-close across sectors.
- **Churn risk** — scores accounts by lost-deal percentage and time since their last won deal to flag retention risk.
- **Seasonality** — tracks monthly and yearly revenue fluctuations to guide resourcing and marketing timing.

The companion Power BI dashboard tracks total revenue, win rate, funnel drop-off, agent leaderboard, and product/industry/regional performance.

## Tech Stack

SQL · Power BI
