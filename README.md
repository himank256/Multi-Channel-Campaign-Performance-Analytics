# Multi-Channel-Campaign-Performance-Analytics
The marketing team received four platform exports (Google Ads, Meta Ads, Email CRM, Display Network) in incompatible formats with no unified schema, making cross-channel performance analysis impossible.
| **Source**          | **Rows** | **Date Format Issues**                              | **Channel Name Variants**              | **Numeric Issues**                                   | **Null Rate** |
| ------------------- | -------- | --------------------------------------------------- | -------------------------------------- | ---------------------------------------------------- | ------------- |
| **Google Ads**      | 2,710    | Multiple formats: DD/MM/YYYY, YYYY-MM-DD + 4 others | 'Paid Search', 'paid_search', 'SEM'    | Cost stored as string (e.g., "$1,234.56")            | 6%            |
| **Meta Ads**        | 2,267    | Mixed formats; DD Mon YYYY dominant                 | 'Social Media', 'social', 'SM'         | Currency in USD (requires GBP conversion)            | 8%            |
| **Email CRM**       | 1,340    | D-M-YY dominant format                              | 'EMAIL', 'e-mail', 'Email Marketing'   | Revenue inconsistently stored (some rows in pennies) | 7%            |
| **Display Network** | 1,724    | Mixed MM-DD-YYYY and DD/MM/YYYY                     | 'display ads', 'Banner Ads', 'Display' | Negative spend values present (£)                    | 9%            |
| **Budget CSV**      | 7        | N/A                                                 | N/A                                    | Values contain £ symbol and commas (e.g., £12,500)   | N/A           |



⚙️ ETL Pipeline Overview
Step 1  → Load raw data (string dtype)
Step 2  → Data profiling (nulls, distributions)
Step 3  → Date standardisation (6 formats → YYYY-MM-DD)
Step 4  → Channel normalization (regex mapping)
Step 5  → Numeric cleaning (currency → float)
Step 6  → Deduplication (composite key)
Step 7  → Anomaly detection & quarantine
Step 8  → Schema standardisation
Step 9  → Data merge + FX conversion (USD → GBP)
Step 10 → KPI calculation (CTR, CVR, ROI, CPA)


📈 Data Processing Outcome
Stage	Rows
Raw Input- 8,041
After Deduplication- 7,387
Anomalies Removed- 217
Final Clean Dataset- 6,363
Retention Rate- 79.1%



📊 Deliverables:
📁 6-tab Excel Dashboard
📄 PDF Case Study Report
🐍 Python ETL Pipeline Script
🧾 Data Quality Audit Log

📊 Dashboard Highlights
KPI tracking: CTR, Conversion Rate, ROI, CPA
Monthly performance trends (Revenue vs Cost)
Channel-wise ROI heatmaps
Data quality transparency tab

| **Insight**                                           | **Action**                    |
| ----------------------------------------------------- | ----------------------------- |
| High-performing channel delivers disproportionate ROI | Reallocate +25% budget        |
| Display network shows high anomaly rate               | Audit tracking + reduce spend |
| Q4 consistently strongest                             | Front-load budget allocation  |
| Email channel highly cost-efficient                   | Scale personalization         |

💰 Business Impact:
Identified a channel reallocation strategy worth £60K+ incremental revenue (FY 2025) without increasing total budget.

🧠 Skills Demonstrated

ETL Design · Data Cleaning · Pandas · Regex · Excel Analytics · Campaign Analytics · Business Insights
