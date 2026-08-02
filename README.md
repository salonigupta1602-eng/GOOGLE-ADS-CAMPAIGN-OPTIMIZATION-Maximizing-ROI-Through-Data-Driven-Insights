# GOOGLE-ADS-OPTIMIZATION: Maximizing ROI Through Data Driven Insights
End-to-end digital ad campaign analytics: Python/SQL, data cleaning, EDA, statistical testing and an interactive Power BI dashboard.


DESCRIPTION: 
Google Ads Campaign Optimization is an end-to-end data analytics project built using Python and SQL to uncover insights from a Digital Advertising Campaign Performance dataset. It analyzes campaign spend, revenue, ROI, ROAS, and conversions across platforms, industries, devices, and audience segments. The project builds predictive models to forecast revenue and profit, and delivers an interactive Power BI-style dashboard. It demonstrates data cleaning, statistical analysis, machine learning, and business storytelling techniques commonly used in professional data analytics roles.

OBJECTIVES:
- Identify the most profitable campaigns and highest-performing campaign objectives.
- Analyze advertiser spending behavior and budget allocation effectiveness.
- Identify the highest-performing audience segments, devices, and platforms.
- Determine statistically significant drivers of campaign profitability.
- Predict campaign revenue, profit, and conversions using machine learning.
- Generate actionable, data-driven business recommendations.

TECH STACK:
- Python – Primary programming language used for data analysis and modeling.
- Pandas / NumPy – Used for data cleaning, preprocessing, filtering, and KPI engineering.
- Matplotlib / Seaborn / Plotly – Used for static and interactive visualizations.
- Scikit-learn / XGBoost – Used for predictive modeling (Linear Regression, Random Forest, XGBoost).
- SQL (SQLite) – Used for business-annotated query analysis.
- Jupyter Notebook – Interactive environment used for coding, analysis, and visualization.
- Power BI – Dashboard specification, DAX measures, and data model.
- CSV Dataset – Source of digital advertising campaign data used for analysis.

DATA SOURCE:
- The dataset used for this project is a Digital Advertising Campaign Performance dataset.
- Dataset: `tech_advertising_campaigns_dataset.csv` — 10,000 campaigns × 41 features.

FEATURES:
- Data cleaning and validation, including formula-verification of all pre-computed KPIs.
- Univariate, bivariate, and multivariate exploratory data analysis.
- KPI feature engineering — ROI, ROAS, CTR, CPA, Conversion Rate, Profit Margin, and two composite scores.
- 20 business-annotated SQL queries covering profitability, segmentation, ranking, and trends.
- Statistical analysis — correlation matrix, hypothesis testing (ANOVA/Pearson), OLS regression.
- Predictive modeling — Linear Regression, Random Forest, and XGBoost with cross-validation and tuning.
- Interactive Plotly visualizations and a fully interactive HTML dashboard with slicers, drill-through, and bookmarks.
- Complete Power BI build package — Power Query, DAX measures, theme, and data model.

HIGHLIGHTS:
- Achieved an overall blended ROAS of 6.54x and ROI of ~554% across all campaigns.
- Identified that 21.7% of campaigns are currently loss-making despite active spend.
- Revealed Finance as the leading industry by median campaign profit.
- Found Facebook to be the top platform by median ROAS.
- Determined Video as the best-performing creative format by ROAS.
- Built an XGBoost model achieving R² of 0.70 for revenue prediction on held-out test data.

RESULTS:
- Total revenue ~$284.2M against ~$43.5M ad spend, yielding ~$240.7M in profit.
- Overall CTR: 2.16% | Conversion rate: 4.30% — the full-funnel baseline for all segment comparisons.
- Hypothesis testing (ANOVA/Pearson, α = 0.05) confirmed device type, Quality Score, budget tier, and audience segment as statistically significant performance drivers, not coincidental patterns.
- OLS regression confirmed ad spend, Quality Score, and conversion rate as genuine revenue drivers, not incidental correlations.
- XGBoost outperformed Random Forest and Linear Regression across all three prediction targets, with Linear Regression trailing on non-linear relationships.
- Feature importance ranked ad spend and Quality Score as the top controllable revenue predictors — ahead of platform, objective, and industry.
- Industry-level profitability analysis (SQL Q11) showed loss-making campaigns cluster unevenly — some industries carry disproportionately more risk, guiding where pre-launch screening matters most.

BUSINESS IMPACT & INSIGHTS:
- Helps advertisers understand which platforms, devices, and audiences convert spend into profit most efficiently.
- Enables identification of high-performing budget tiers to guide reallocation decisions.
- Supports pre-launch risk screening by flagging campaign configurations likely to be loss-making.
- Assists creative teams in understanding which formats and objectives drive the best returns.
- Provides a ready-to-use interactive dashboard for stakeholders to explore performance without needing code.
- Demonstrates practical applications of the full data analytics lifecycle for business intelligence and decision-making.

CONCLUSION:
- Profitability isn't driven by spend alone — platform, creative format, audience targeting, and Quality Score each measurably affect ROI and ROAS, confirmed through statistical testing, not assumption.
- Over a fifth of campaigns are currently unprofitable despite strong overall returns — a concrete, quantifiable optimization opportunity, not a marginal edge case.
- Revenue, profit, and conversions can be reliably forecasted from pre-campaign attributes, letting underperforming configurations be flagged and redesigned before spend commits, not diagnosed after the fact.
- Paired with the SQL analysis, interactive dashboard, and Power BI package, this project delivers a reusable analytical framework — not just findings — for evidence-based budget, audience, and creative decisions.

<details>
<summary><strong>Recommendations</strong> (click to expand)</summary>

- Prioritize Lead Generation campaigns — the most profit-efficient objective at current spend levels.
- Shift budget toward high-ROAS segments, led by Business Professionals, targeted by interest × income intersection.
- Reallocate toward the highest-ROI budget tier — bigger budgets don't guarantee better returns.
- Pair Desktop with Video creative, since format performance varies by device.
- Prioritize Finance-vertical accounts — highest median profit per campaign.
- Standardize on Video creative and monitor Quality Score — the two most controllable, high-leverage factors.
- Use the predictive model pre-launch to flag likely loss-making configurations before spend commits.
- Diagnose zero-conversion campaigns via placement-level bounce rate.
</details>

<details>
<summary><strong>Project Structure</strong> (click to expand)</summary>

```
Google-Ads-Campaign-Analytics/
├── README.md
├── data/
│   ├── raw/tech_advertising_campaigns_dataset.csv     # original 10,000 x 41 dataset
│   └── cleaned/
│       ├── campaigns_cleaned.csv                       # post-cleaning
│       └── campaigns_with_kpis.csv                     # + engineered KPIs
├── notebooks/
│   └── Google_Ads_Campaign_Optimization_Analysis.ipynb # full analysis, zero errors
├── sql/
│   └── campaign_analysis_queries.sql                   # all 20 queries, annotated
├── dashboard/
│   └── PowerBI_Dashboard_Specification.md              # 6-page dashboard spec + DAX
└── assets/
    ├── *.png                                            # static EDA / model charts
    └── *.html                                           # interactive Plotly exports
```

</details>

<details>
<summary><strong>How to Reproduce</strong> (click to expand)</summary>

```bash
pip install pandas numpy matplotlib seaborn plotly scikit-learn xgboost statsmodels scipy jupyter
jupyter nbconvert --to notebook --execute --inplace notebooks/Google_Ads_Campaign_Optimization_Analysis.ipynb
```

Self-contained: reads only the raw CSV and regenerates every cleaned file, chart, model, and metric from scratch.

</details>

<details>
<summary><strong>Future Improvements</strong> (click to expand)</summary>

- Add an advertiser/account ID field for advertiser-level lifetime-value modeling.
- Introduce time-series cross-validation once sequential campaigns per advertiser are available.
- Extend XGBoost with SHAP values for per-campaign explainability.
- Automate the Power BI refresh pipeline against `campaigns_with_kpis.csv` or a live warehouse table.

</details>
