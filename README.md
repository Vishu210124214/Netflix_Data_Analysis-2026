# Netflix_Data_Analysis-2026
# 🎬 Netflix User Behavior & Retention Analysis

## 📌 Project Overview
This repository contains an end-to-end exploratory data analysis (EDA) and statistical inference pipeline examining customer streaming habits and platform interactions. The primary goal is to isolate key behavioral patterns that correlate with subscriber churn, evaluate the performance of Netflix's recommendation engine, and map geographic risk variables to help product and marketing teams build data-driven retention strategies.

---

## 📂 Repository File Structure
```text
├── Netflix_analysis2023.ipynb   # Main Jupyter Notebook with code, plots, and analysis
├── netflix_user_behavior_dataset.csv # Underlying user behavior data
├── netflix_demographics_and_inactivity.png # Visualization artifact: Churn vs Inactivity
├── netflix_regional_risk_matrix.png       # Visualization artifact: Regional Churn analysis
└── README.md                    # Project documentation and summary

🛠️ Tech Stack & MethodologyLanguage:
1.Python 3.10+Core
2.Data Engineering: Pandas, NumPyStatistical
3.Inference: SciPy (Stats module)Data Visualization: Seaborn, Matplotlib

📊 Business Metrics & Pipeline Summary
1. Data Integrity & Preprocessing

-- Sanity Checks: Cleaned the raw data by conducting systematic audits for structural anomalies, tracking missing values (df.isnull().sum()), and handling row duplication (df.duplicated()).

-- Display Configurations: Programmed global options using pd.set_option('display.max_rows', 50) to ensure systematic and legible data frame inspection profiles without truncating necessary variables.

2.Correlation Matrix Insights (Feature Synergy)

-- The Algorithmic Lift: Isolated a meaningful positive correlation of 0.31 between recommendation_click_rate and content_interactions. This proves that personalization and algorithmic discovery serve as primary engagement multipliers—users who click recommendations spend significantly more time interacting with platform content.

-- Generation & Plan Invariance: Variables like age and monthly_fee yielded flat correlations (~0.00) relative to core viewing volumes. This reveals that consumption habits on the platform are generationally universal and structurally independent of subscription pricing tiers.

Non-Linear Safeguards: Checked for hidden, non-linear relationships using Seaborn scatter plots (sns.scatterplot) to verify that the linear correlation values didn't overlook hidden quadratic (U-shaped) or clustered consumer behaviors.

3. Granular Segment BreakdownsDevice

-- Profiling: Grouped the data by primary_device using aggressive aggregations (.groupby().agg()) to track variations in average binge-watching sessions, completion rates, and weekly usage frequencies across TV, Laptop, Mobile, and Tablet profiles.

-- Genre Effectiveness: Rated content performance by evaluating recommendation_click_rate and user-submitted scores (rating_given) across different genres, helping content managers isolate underserved customer segments.

-- Geographic Matrix: Constructed a comprehensive regional scorecard. While platform-wide churn rests at a steady baseline of ~19.93%, geographic slicing exposed that Australia ($20.96\%$) and Japan ($20.81\%$) exhibit elevated attrition trends that correspond with lower average daily streaming hours.

🧪 Advanced Inferential Modeling (Hypothesis Testing)

To confirm whether a customer's login cadence is a definitive leading indicator of account cancellations, an Independent Two-Sample T-Test was evaluated against the continuous variable days_since_last_login across categorical targets (churned Status: Yes vs No).

-- Null Hypothesis ($H_0$): The average number of days since the last login is identical between active and churned users.

-- Alternative Hypothesis ($H_1$): Churned users exhibit a significantly larger window of inactivity before cancellation compared to active users.

-- Statistical Output: The test generated a highly critical $P\text{-value} < 0.05$.Conclusion: Reject the Null Hypothesis ($H_0$).

-- The variance in login gaps is statistically significant, validating that real-time tracking of logging intervals can serve as an automated early-warning metric to trigger targeted win-back notifications.

💡 **Strategic Recommendations for Stakeholders**


-- Targeted Regional Engagement: Marketing teams should allocate specialized retention budgets to the Australian and Japanese territories to incentivize platform engagement and drive usage beyond the critical churn threshold.

-- Proactive Automation Triggers: Product engineers can leverage the proven significance of the login latency window to flag accounts as "at-risk" once inactivity exceeds the statistically validated threshold, automating push messaging before user subscription renewal cycles end.
