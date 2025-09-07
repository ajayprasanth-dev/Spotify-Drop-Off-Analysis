# Project Overview – Spotify Drop-Off Analysis

## 1. Introduction
Customer churn is one of the most critical challenges for subscription-based services like Spotify. High churn rates directly impact revenue, reduce lifetime customer value, and increase marketing and acquisition costs.  

The goal of this project is to **analyze customer behavior patterns, identify the drivers of churn, and provide actionable strategies** to reduce drop-off. Using simulated user data including subscriptions, complaints, and usage patterns, this project creates an **interactive Power BI dashboard** to support data-driven decision-making.  

---

## 2. Business Problem
Spotify, like many streaming platforms, invests heavily in acquiring users, but retention is equally important. High churn leads to lost revenue and can indicate dissatisfaction with the product or service.  

Challenges addressed in this project:  
- Identifying which users are most likely to churn  
- Understanding the role of complaints in driving churn  
- Evaluating the risk across subscription types (Free, Basic, Premium)  
- Recognizing seasonal patterns in drop-offs  

The ultimate business objective is to **reduce churn by implementing targeted retention strategies**, improving user satisfaction, and optimizing long-term revenue.

---

## 3. Data Description
The dataset used in this project is simulated to reflect realistic user behavior. It includes:

| Column | Description |
|--------|-------------|
| Subscription Type | Free, Basic, Premium |
| Usage Hours | Average daily usage in hours |
| Login Frequency | Number of logins per month |
| Complaint Logs | Type, severity (low, medium, critical), resolution status |
| Drop-Off Status | Whether the user unsubscribed or remained active |
| Month | Month of activity for time-series analysis |

**Data Notes:**  
- The dataset spans multiple months to capture seasonal churn trends.  
- Missing values and inconsistencies were present in raw data, requiring cleaning and standardization.  

---

## 4. Tools & Technology
**SQL**  
- Cleaned and transformed raw data  
- Handled missing values, inconsistent subscription types, and usage anomalies  
- Structured tables for analysis and dashboard integration  

**Excel**  
- Performed exploratory data analysis (EDA)  
- Verified SQL-cleaned data with pivot tables and aggregation checks  
- Identified early patterns before visualization  

**Power BI**  
- Designed interactive dashboards with slicers, charts, and KPIs  
- Built DAX measures for metrics like churn rate, average usage, and complaint impact  
- Provided dynamic insights for stakeholders  

---

## 5. Methodology

### Step 1: Data Cleaning (SQL)
- Standardized subscription types and usage hours  
- Removed duplicates and handled NULL values  
- Created consistent, structured tables for further analysis  

### Step 2: Data Validation (Excel)
- Cross-checked SQL outputs using pivot tables  
- Conducted exploratory data analysis (EDA) to identify trends and anomalies  
- Ensured data consistency and reliability before visualization  

### Step 3: Dashboard Development (Power BI)
- Created **interactive charts**:
  - Total, Active, Dropped Users
  - Complaints vs. Drop-Off
  - Churn by Subscription Type
  - Churn by Usage Hours
  - Monthly Drop-Off Trends  
- Added **slicers** for filtering by month, subscription tier, usage hours, and complaint severity  
- Developed KPIs for quick decision-making  

---

## 6. Key Insights

1. **Complaint Severity Drives Churn**  
   - Users with **unresolved critical complaints** had the highest drop-off rate  
   - Indicates that **customer support responsiveness directly impacts retention**  

2. **High-Usage Users Are Vulnerable**  
   - 28% of churned users were high-usage, loyal users  
   - Suggests that **even engaged users may leave if dissatisfied**  

3. **Churn Across Subscription Tiers**  
   - Free, Basic, and Premium users all show significant drop-off rates  
   - Retention efforts must be **systemic rather than tier-specific only**  

4. **Seasonal Drop-Off Trends**  
   - Certain months show spikes in churn  
   - Timing **re-engagement campaigns strategically** can reduce seasonal losses  

---

## 7. Recommendations

- **Implement a fast-track complaint resolution system** for high-priority issues  
- **Launch a retention program for high-usage users**, offering personalized offers, exclusive perks, or rewards  
- **Customize retention strategies for each subscription tier**:
  - Free users → Upsell plans with benefits highlights  
  - Premium users → Reinforce value and engagement  
- **Run seasonal re-engagement campaigns** before high-risk periods  

---

## 8. Dashboard Highlights

**Features:**  
- High-level metrics: Total, Active, Dropped Users  
- Complaints vs. Drop-Off correlation charts  
- Subscription Tier Analysis  
- Usage Hours Analysis  
- Monthly Drop-Off Trends  
- Interactive filters for detailed insights  

**Screenshot Examples:**

[Dashboard Screenshots](screenshots)

---
## Stakeholder Value
- Dashboard allows **real-time exploration** of churn patterns.  
- Helps identify **at-risk users and problem areas** quickly.  
- Provides **data-driven recommendations** for marketing and support teams.  

---

## 9. Future Enhancements
- **Predictive Modeling:** Use machine learning to forecast users likely to churn.  
- **Sentiment Analysis:** Analyze complaints to uncover reasons behind dissatisfaction.  
- **A/B Testing:** Evaluate different retention strategies for effectiveness.  
- **Enhanced Segmentation:** Group users by engagement level, region, and subscription history.  

---

## 10. Conclusion
This project demonstrates the ability to **transform raw data into actionable insights**.  
The interactive Power BI dashboard, combined with SQL data cleaning and Excel validation, provides a **comprehensive, data-driven view of customer churn**.  
Stakeholders can use this analysis to **optimize retention strategies, reduce churn, and increase user lifetime value**.  

---

## Contact
- **Email:** ajayprasanth2026@gmail.com  
- **LinkedIn:** [LinkedIn Profile](https://www.linkedin.com/in/ajayprasanth1)

