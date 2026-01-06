# 📞 Telecom Revenue Analysis: Statistical Hypothesis Testing for Megaline

## 🎯 Project Overview
This project provides a data-driven evaluation of Megaline's "Surf" and "Ultimate" prepaid plans. By analyzing a sample of 500 customers from 2018, I conducted **Inferential Statistical Testing** to determine which plan generates higher revenue and whether geographic location influences spending. These insights serve as a foundation for optimizing marketing budgets and strategic pricing.

## 🛠️ Data Engineering & Aggregation
To calculate monthly revenue, I developed a pipeline to merge five distinct datasets (`users`, `calls`, `messages`, `internet`, and `plans`).

### Key Processing Steps:
* **Temporal Feature Engineering:** Converted raw timestamps into standardized monthly periods.
* **Usage Normalization:** Applied plan-specific rounding rules (rounding up seconds to minutes and megabytes to gigabytes) to align with business billing logic.
* **Revenue Modeling:** Created a custom calculation engine to sum base monthly fees plus overage charges for minutes, SMS, and data.

## 🧪 Statistical Hypothesis Testing
I performed independent two-sample **t-tests** using `scipy.stats` with a significance level ($\alpha$) of **0.05**.

### Hypothesis 1: Plan Profitability
* **Null Hypothesis ($H_0$):** Average monthly revenue from Ultimate and Surf users is equal.
* **Alternative Hypothesis ($H_1$):** Average monthly revenue from Ultimate and Surf users differs.
* **Result:** Rejected $H_0$. Statistical evidence shows a significant difference in revenue between plans.

### Hypothesis 2: Regional Impact (NY-NJ vs. Others)
* **Null Hypothesis ($H_0$):** Average revenue in the NY-NJ area is equal to other regions.
* **Alternative Hypothesis ($H_1$):** Average revenue in the NY-NJ area differs from other regions.
* **Result:** Analyzed using regional filtering to determine local market behavior patterns.



## 📊 Exploratory Data Analysis (EDA) Highlights
* **Revenue Composition:** Discovered that overage charges account for approximately **84% of total revenue**, indicating a high reliance on "Surf" plan excedents.
* **Consumption Patterns:** Visualized the distributions of call duration, message volume, and data usage using histograms and boxplots to identify outliers and behavior variance.


## 🛠️ Tech Stack
* **Language:** Python 3.12.1
* **Data Science Stack:** Pandas, NumPy, Matplotlib, Seaborn.
* **Statistical Analysis:** SciPy (stats module).
* **Tools:** Jupyter Notebook, VS Code.

## 📈 Strategic Business Insights
* **Upselling Opportunity:** "Ultimate" generates higher average revenue; however, "Surf" users often pay significant overage fees. There is a clear opportunity for an upselling campaign targeting high-usage "Surf" customers.
* **Pricing Strategy:** The extreme reliance on overages suggests a need to re-evaluate "Surf" limits to improve customer satisfaction while maintaining profitability.
* **Market Focus:** Geographic differences in spending suggest that marketing campaigns should be tailored differently for the NY-NJ metro area versus the rest of the country.
