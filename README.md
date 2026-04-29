# Spotify User Behavior and Patterns Analysis

| Field | Details |
| :--- | :--- |
| **Project Title** | Spotify User Behavior and Pattern Analysis |
| **Sector** | Media & Entertainment / Digital Streaming |
| **Team ID** | G18 |
| **Section** | Section D |
| **Faculty Mentor** | Archit Raj |
| **Institute** | Newton School of Technology |
| **Submission Date** | April 29, 2026 |

## Team Members
| Role | Name | GitHub Username |
| :--- | :--- | :--- |
| **Project Lead** | Anwesha Adhikari | aaneesa |
| **Data Lead** | Lokendra Singh | lokibanna |
| **ETL Lead** | Lokendra Singh | lokibanna |
| **Analysis Lead** | Ajit kumar prasad | Shamarvey1 |
| **Visualization Lead** | Adarsh | AdarshVashith |
| **Strategy Lead** | Aditya Bhardwaj | Aditya44860 |
| **PPT and Quality Lead** | Aaryan yadav | 69Igris |

## Business Problem
In the highly competitive music streaming industry, understanding user engagement and churn is critical for platform sustainability. This project serves the Product and Marketing teams at Spotify to address the challenge of identifying key behavioral drivers that lead to user inactivity and subscription churn. By analyzing interaction data, we aim to uncover patterns in listening habits, ad interactions, and feature preferences to improve user retention strategies.

### Core Business Question
"What are the primary behavioral and demographic factors—specifically listening hours, skip rates, and subscription types—that significantly influence user churn and platform engagement?"

### Decision Supported
This analysis enables stakeholders to design targeted retention campaigns for "Likely Churned" segments, optimize ad-to-subscription conversion funnels, and prioritize product feature development based on user "Most Liked" data.

## Dataset
| Attribute | Details |
| :--- | :--- |
| **Source Name** | Spotify User Behavior Dataset (Simulated Realistic) |
| **Direct Access Link** | [Data/Raw/spotify_user_behavior_realistic_50000_rows.csv](data/raw/spotify_user_behavior_realistic_50000_rows%20(1).csv) |
| **Row Count** | 49,834 (Cleaned) |
| **Column Count** | 29 (Processed) |
| **Time Period Covered** | 2018 to 2024 (based on signup dates) |
| **Format** | CSV |

### Key Columns Used
| Column Name | Description | Role in Analysis |
| :--- | :--- | :--- |
| `is_churned` | Binary flag for user churn status | Target Variable / KPI |
| `avg_listening_hours` | Average weekly listening duration | KPI / Segmentation |
| `avg_skips_per_day` | Daily frequency of skipped tracks | Behavioral Metric |
| `subscription_type` | Tier (Free, Premium Duo, Family, etc.) | Filter / Dimension |
| `engagement_score` | Calculated metric based on activity | KPI |

*For full definitions, see [docs/data_dictionary.md](docs/data_dictionary.md).*

## KPI Framework
| KPI | Definition | Formula / Computation |
| :--- | :--- | :--- |
| **Churn Rate** | Percentage of users who have discontinued service. | `Count(Churned) / Total Users` |
| **Engagement Score** | A weighted index of listening hours and creation activity. | `(Hours * 0.7) + (Playlists * 0.3)` |
| **Conversion Rate** | Rate at which ad-exposed users move to Premium. | `Count(Ad_Converted) / Count(Ad_Interacted)` |

## Tableau Dashboard
* **Dashboard URL:** [Tableau Public Link Placeholder]
* **Executive View:** High-level summary of Churn Rate, Total Active Users, and Revenue distribution by subscription type.
* **Operational View:** Drill-down into age group distributions, primary device usage, and engagement levels per country.
* **Main Filters:** Country, Subscription Type, Age Group, and Gender.

## Key Insights
1.  **Engagement Consistency:** Churned users and active users show almost identical mean listening hours (approx. 9.95 hrs/week), suggesting that total volume of time is a weaker predictor of churn than previously hypothesized.
2.  **Skip Behavioral Parity:** Statistical testing (Mann-Whitney U) confirmed no significant difference in skip rates between churned and active users (p=0.47), indicating skipping is a universal behavior across segments.
3.  **Tier Stability:** Subscription types (Free vs. Premium) do not show a statistically significant relationship with churn (Chi-square p=0.58), suggesting churn triggers are behavioral rather than cost-driven.
4.  **Feature Stickiness:** "Personalized Playlists" and "Social Sharing" emerge as the most-liked features across the 18-24 and 25-34 age groups.
5.  **Age Distribution:** The platform sees a peak in the 25-34 age segment, with engagement scores tapering off significantly in the 55+ demographic.
6.  **Device Dominance:** Mobile remains the primary device across all churn statuses, but Desktop users show higher playlist creation rates.
7.  **Ad-to-Subscription Funnel:** Conversion rates are highest among users who interact with ads specifically between 6 PM and 10 PM.
8.  **Inactivity Warning:** Users reaching 3 months of inactivity have an 85% higher probability of formal churn within the following quarter.

## Recommendations
| # | Insight | Recommendation | Expected Impact |
| :--- | :--- | :--- | :--- |
| 1 | Inactivity Correlation | Automate "Come Back" push notifications after 45 days of zero listening hours. | 10-15% reduction in churn |
| 2 | Feature Stickiness | Launch "Social Listening" events targeting the 25-34 age group to increase session frequency. | 5% increase in Engagement Score |
| 3 | Tier Parity | Shift marketing focus from "Price Savings" to "Exclusive Discovery Features" for Premium retention. | Higher lifetime value (LTV) |

## Repository Structure
```text
sectiond_gr18_spotify-user-behavior-and-pattern/
|-- data/
|   |-- raw/                # Original 50,000 row dataset
|   `-- processed/          # Final cleaned 49,834 row dataset
|-- notebooks/
|   |-- 01_extraction.ipynb # Data loading
|   |-- 02_cleaning.ipynb   # Outlier handling and imputation
|   |-- 03_eda.ipynb        # Visual distributions
|   |-- 04_statistical_analysis.ipynb # T-tests, Chi-Sq, Feature Importance
|   `-- 05_final_load_prep.ipynb # Final formatting
|-- tableau/
|   |-- screenshots/        # Dashboard visual captures
|   `-- dashboard_links.md  # Public URL
|-- docs/
|   `-- data_dictionary.md  # Column definitions
```

## Tech Stack
* **Python (Pandas, Scipy, Seaborn):** ETL, Statistical Testing, and Feature Importance Modeling.
* **Tableau Public:** Interactive data storytelling.
* **GitHub:** Version control and collaboration.
