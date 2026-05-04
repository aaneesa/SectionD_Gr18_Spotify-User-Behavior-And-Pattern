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
* **Dashboard URL:** (https://public.tableau.com/views/Spotify_Dashboard_17774564636670/Dashboard1?:language=en-US&publish=yes&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link)
* **Executive View:** High-level summary of Churn Rate, Total Active Users, and Revenue distribution by subscription type.
* **Operational View:** Drill-down into age group distributions, primary device usage, and engagement levels per country.
* **Main Filters:** Country, Subscription Type, Age Group, and Gender.

## Key Insights
* Engagement Parity: High, Medium, and Low engagers all churn at similar rates (61.29–61.63%), suggesting total volume of time is a weak churn predictor.

* Conversion Bottleneck: The transition from Ad Interaction (34.96%) to Conversion (24.87%) is the primary constraint.

* Tier Stability: Subscription types do not show a statistically significant relationship with churn (p=0.58), indicating churn is behavioral, not cost-driven.

* Feature Stickiness: "Personalized Playlists" and "Social Sharing" are the most liked features for users aged 18-34.

* Inactivity Warning: Users inactive for 3 months have an 85% higher probability of formal churn next quarter

## Recommendations
#	Insight	Recommendation	Expected Impact
1	Free is the largest cohort	Trigger Premium trial offers after behavioral thresholds.	Higher Conversion Rate
2	High "Likely Churn" (38.56%)	Launch win-back programs with curated playlists for at-risk users.	10-15% Churn Reduction[cite: 1]
3	Skips vs Rating uncorrelated	Re-evaluate recommendation engine models via A/B testing.	Lower Skips/Day

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

## Contribution Matrix
Team MemberETL & CleaningEDA & AnalysisStatistical AnalysisTableau DashboardReport & PPTAnwesha AdhikariYesLokendra SinghYesAjit Kumar PrasadYesAdarshYesAditya BhardwajYesAaryan YadavYes
