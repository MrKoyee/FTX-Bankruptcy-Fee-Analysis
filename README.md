# Table of Contents
- [Introduction](https://github.com/MrKoyee/Power-BI-Dashboard#-introduction)
- [Business Questions](https://github.com/MrKoyee/Power-BI-Dashboard#-business-questions)
- [Why this Project Matters](https://github.com/MrKoyee/Power-BI-Dashboard#-why-this-project-matters)
- [Skills Showcased](https://github.com/MrKoyee/Power-BI-Dashboard#-skills-showcased)
- [Tools & Technologies](https://github.com/MrKoyee/Power-BI-Dashboard#%EF%B8%8F-tools--technologies)
- [Key Findings & Conclusion](https://github.com/MrKoyee/Power-BI-Dashboard#-key-findings--conclusion)
- [Overall Recommendatins](https://github.com/MrKoyee/Power-BI-Dashboard#-overall-recommendations)
- [Author](https://github.com/MrKoyee/Power-BI-Dashboard#author)

# FTX Bankruptcy Fees Data Analysis
## 📊 Interactive Dashboard




![Dashboard Page 1](/Images/FTX_1.png)
[View Interactive Dashboard](https://app.powerbi.com/view?r=eyJrIjoiMWJlNWI4YTgtNmE2My00MjcwLTk4ZTktYzBkNjIzMDFiMzIyIiwidCI6IjRiMmE0YjE5LWQxMzUtNDIwZS04YmIyLWIxY2QyMzg5OThjYyIsImMiOjF9)


## 📖 Introduction


This project presents a comprehensive analysis of various costs incurred during the bankruptcy proceedings of **FTX Trading Ltd.** 

The dramatic collapse of the 🪙 crytocurrency trading platform in November 2022 triggered one of the most complex and high-profile bankruptcy cases in US history. The legal action was initiated under Chapter 11 of the US Bankruptcy Code in the District of Delaware.

Chapter 11 allows a company struggling with debt repayment to restructure its affairs while retaining control. In this type of proceedings, the troubled company engages the services of law firms, financial advisors, forensic investigators, tax specialists, claims administrators, and restructuring consultancy firms to assist with asset recovery, litigation, investigations, and creditor distributions.

These advisors often bill the bankruptcy estate under court supervision, a process that involves a public disclosure of fees and expenses incurred during the process through applications filed on the court docket. These disclosures can make for a rich data and reveal patterns for stakeholders about who billed FTX and for what services, as well as how Chapter 11 costs can grow rapidly for various types of companies.

This project scrapped hundreds of pages of those fee applications from FTX's court dockets, with the goal of transforming raw, unstructured PDF filings into a structured, interactive Power BI dashboard. 

## 🎯 Business Questions
- **💰 Spending Analysis**
    - How much has the FTX estate spent on professional fees?
    - Which advisory firms have received the highest compensation?
    - Which professional categories account for the largest share of total fees?
    - How much of spending relates to professional fees versus expenses?
    - Which professionals billed the most?


- **👥 Resource Utilization**
    - Which employee titles generated the highest billable fees?
    - Which professionals recorded the highest number of billable hours?
    - Are firms relying primarily on senior personnel or junior staff?
    - Which firms deployed the largest teams?

- **💵 Billing Rate Analysis**
    - Which firms command the highest average billing rates?
    - How do billing rates differ across professions and job titles?
    - What is the relationship between billing rates and hours worked?
    - Which firms appear most labor-intensive?**

## 📌 Why This Project Matters

Companies facing financial distress often turn to bankruptcy protection as a means of restructuring their obligations and preserving value for stakeholders. While bankruptcy can provide a structured path to recovery, the process itself can be extremely costly. Debtors typically retain a wide range of professional service providers to navigate the legal, operational, and financial complexities of the proceedings.

This project explores the scale and composition of those professional costs through the lens of the FTX bankruptcy, one of the largest and most complex corporate restructurings in recent history. This project reveals how professional fees accumulate over time, which firms and professionals account for the largest share of costs, and the key factors driving overall expenditures.

The findings demonstrate that bankruptcy-related professional fees can reach hundreds of millions of dollars, and in some cases, such as FTX, approach or exceed $1 billion. Thereby reducing the assets ultimately available to creditors and other stakeholders. As a result, understanding how these costs are incurred is important not only for legal and financial professionals, but also for investors, creditors, restructuring advisors, and policymakers interested in the efficiency and economics of the bankruptcy process.


## 🧠 Skills Showcased
- **🗂️ Data Extraction from PDFs:**  
This was the most technically demanding phase of the project. The FTX bankruptcy generated dozens of monthly, interim, and final fee applications filed by various law firms, consulting firms, investment banks, and other retained professionals. These filings were downloaded from the bankruptcy court docket and stored in a dedicated local repository for processing.   

    The first challenge was transforming these unstructured court filings into a format suitable for analysis. Using Power Query's native PDF connector, relevant tables were extracted directly from each filing and reviewed individually. This process required significant manual validation because fee applications were prepared by different firms and were intended for court reporting purposes rather than analytical use.

    During the extraction process, several recurring data quality issues were identified:

    - Inconsistent table structures
    - Merged cells
    - Multi-page tables that were split during PDF extraction
    - Missing or incomplete values
    - Different naming conventions
    - Varying date formats
    - Duplicate records across filings
    - Non-tabular content embedded within extracted tables

- **🧹 Power Query Transformation Process for Data Cleaning:** This step involves transforming the raw PDF extracts into a clean, analyzable dataset using Power Query. Columns in the imported tables were standadized, while firms and professionals were grouped based on their roles and titles in the proceedings. 

- **🗃️ Data Model in Power BI** The transformed data was modeled using a star schema, with interactive slicers, buttons, and bookmarks added to improve dashboard navigation and usability.

- **📐 DAX Measures:** Custom measures were written in DAX to power the dashboard analytics. These include **Total Requested**, **Total Approved**, **Total Paid**, **Average Blended Rate**, and **Total Hours**.

- **📊 Dashboards & Visualization:** Two dashboards were built; one for advisory firms and the other for professionals. 
    - **Dashboard 1: Advisory Firms** 
        ![Dashboard Page 1](/Images/FTX_1.png)
        - **KPI Cards:** Total Amount Charged, Number of Advisors, Average Hourly Rate, Average Fee Realization Rate, and Average Expense Realization Rate.
        - **Bar Chart:** Top advisory firms by amount charged.
        - **Donut Chart:** Amount charged distribution.
        - **Treemap:** Share of professional categories.
        - **Scatter Chart:** Three-in-one dynamic scatter charts for relationships among fees, hours and rates.
        - **Stacked Bar Chart:** Workforce breakdown.
        - **Funnel Chart:** Fee flow from request to approval.
    
    - **Dashboard 2: Professionals**
        ![Dashboard Page 1](/Images/FTX_2.png)
      - **KPI Cards:** Total Professional Compensation, Number of Professionals, Average Hourly Rate, Total Hours Billed, and Average Hours.
       - **Bar Charts:** Top professionals by compensation, Billing Rates and Total Fees by job titles.
        - **Line and Clustered Column Chart:** Professionals by billale hours and hourly rates.
        
## 🛠️ Tools & Technologies
Documents were sourced from PACER and processed using Power Query for data extraction, cleaning, and transformation. Power BI was used for data modeling, dashboard development, and visualization, with DAX supporting the creation of calculated columns, measures, and custom metrics.

## 💡 Key Findings & Conclusion  
The analysis examines how professional service costs were distributed across the FTX bankruptcy estate and identifies the primary drivers of fee generation.

- Professional firms engaged by FTX billed the estate nearly $1 billion, making the case one of the most expensive bankruptcy proceedings in US history.
- Fee generation was highly concentrated, with Alvarez & Marsal and Sullivan & Cromwell accounting for a substantial share of total advisory costs.
- Reimbursable expenses represented less than 2% of total costs, indicating that professional fees were the dominant expense category.

- The analysis found that hours worked were a stronger determinant of total fees than hourly billing rates, highlighting the importance of staffing intensity in driving costs.

- Ernst & Young deployed the largest number of professionals among all firms retained by the estate.
- More than 2,000 professionals were engaged across legal, consulting, accounting, and advisory firms throughout the proceedings.
- Senior partner billing rates exceeded $1,600 per hour, consistent with compensation levels observed in other large-scale Chapter 11 restructurings.
- The findings demonstrate the significant scale, complexity, and resource demands associated with administering one of the largest corporate bankruptcies in recent history.

## 📣 Overall Recommendations
- Given the scale of professional fees observed, bankruptcy estates should adopt more standardized and granular reporting formats for fee applications.
- The analysis shows that total hours are a stronger driver of costs than hourly rates. This suggests that controlling staffing intensity is more effective than negotiating rates alone. Future estates should implement pre-approved budget caps on hours by workstream and require justification for significant overruns.
- The data suggests significant variation in how firms deploy senior vs junior staff. Estates should encourage a more balanced leverage model, ensuring that higher-cost senior professionals are used primarily for strategic work, while routine tasks are delegated to lower-cost staff.
- The heavy reliance on unstructured PDFs created significant inefficiencies in analysis. Courts and estates should consider adopting standardized digital submission templates to enable automated ingestion, auditing, and analytics.

## Author
### Segun
Data Analyst and Storyteller

[Return Home](https://github.com/MrKoyee/Power-BI-Dashboard#table-of-contents)

