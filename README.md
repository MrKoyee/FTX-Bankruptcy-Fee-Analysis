# FTX Bankruptcy Fees Data Analysis
## Table of Contents
- [Project Overview](https://github.com/MrKoyee/Power-BI-Dashboard#-introduction)
- [Business Questions](https://github.com/MrKoyee/Power-BI-Dashboard#-business-questions)
- [Why this Project Matters](https://github.com/MrKoyee/Power-BI-Dashboard#-why-this-project-matters)
- [Skills Showcased](https://github.com/MrKoyee/Power-BI-Dashboard#-skills-showcased)
- [Tools & Technologies](https://github.com/MrKoyee/Power-BI-Dashboard#%EF%B8%8F-tools--technologies)
- [Key Findings & Conclusion](https://github.com/MrKoyee/Power-BI-Dashboard#-key-findings--conclusion)
- [Overall Recommendatins](https://github.com/MrKoyee/Power-BI-Dashboard#-overall-recommendations)
- [Author Information](https://github.com/MrKoyee/Power-BI-Dashboard#author)


## 📊 Dashboard Preview

![Dashboard Page 1](/Images/FTX_1.png)

[View Interactive Dashboard](https://app.powerbi.com/view?r=eyJrIjoiN2M5OTliMTUtMGJhZC00NGJlLTg5MDctODZjNjNjNTgyMzZlIiwidCI6IjRiMmE0YjE5LWQxMzUtNDIwZS04YmIyLWIxY2QyMzg5OThjYyIsImMiOjF9)


## 📖 Project Overview


This project presents a comprehensive analysis of various costs **FTX Trading Ltd.** incurred during bankruptcy. 

FTX sought protection under Chapter 11 of the US Bankruptcy Code in the District of Delaware after the 🪙 cryptocurrency exchange platform's collapse in 2022. The legal action eventually led to one of the most complex and high-profile bankruptcy cases in US history.

Chapter 11 allows a company struggling with debt repayment to restructure its operations while retaining control. As part of the restructuring process, the company typically engages a range of professional advisors, including law firms and financial advisors. These professionals assist with critical tasks such as asset recovery, litigation, internal investigations, and creditor distributions.

Because these advisors are compensated from the bankruptcy estate, their fees and expenses are subject to court oversight and must be publicly disclosed through fee applications filed on the bankruptcy docket. These disclosures create a rich and transparent dataset that offers valuable insights into how professional services are utilized during a Chapter 11 case. Stakeholders can identify who billed the debtor, the nature of the services provided, and how restructuring costs can escalate over the course of a large and complex bankruptcy proceeding.

This project scrapped hundreds of pages of those fee applications from the FTX bankruptcy docket, converting raw and unstructured PDF filings into a structured dataset that reveals how advisory fees accumulated for the company.

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

Companies facing financial distress often seek protection through the bankruptcy courts. While Chapter 11 can provide a structured path to recovery and maximize value for creditors, the restructuring process itself can be extraordinarily expensive.

In the case of FTX, professional advisory fees approached $1 billion, making it one of the costliest bankruptcy proceedings in the US. These expenses can significantly reduce the pool of assets ultimately available for distribution to creditors and other stakeholders.

Understanding how these costs are accumulated is therefore important not only for legal and financial professionals, but also for investors, creditors, restructuring advisors, policymakers, and researchers interested in the efficiency, transparency, and economics of the bankruptcy process.

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

- **📊 Dashboards & Visualization:** Two dashboards were built; one for advisory firms and the other for professionals in those firms. 
    - **Dashboard 1: Advisory Firms** 
      ![Dashboard Page 1](/Images/FTX_1.png)
        - **KPI Cards:** Total Amount Charged, Number of Firms, Average Hourly Rate, Fees Requested, and Expenses Requested.
        - **Bar Chart:** Top advisory firms by amount charged.
        - **Donut Chart:** Amount charged distribution.
        - **Treemap:** Share of advisory firm categories.
        - **Scatter Chart:** Three-in-one dynamic scatter charts for relationships among fees, hours and rates.
        - **Stacked Bar Chart:** Workforce breakdown.
        - **Funnel Chart:** Fee flow from request to approval.
        - **Buttons:** Two sents of buttons for the Scatter Chart and the fees.
        
    - **Dashboard 2: Professionals**
        ![Dashboard Page 2](/Images/FTX_2.png)
        - **KPI Cards:** Total Professional Fees, Number of Professionals, Average Hourly Rate, Total Hours Billed, and Average Hours.
        - **Bar Charts:** Top professionals by compensation, rates by job titles, and a breakdown of expenses.
        - **Line and Clustered Column Chart:** Professionals by billable hours and hourly rates.
        - **Slicer:** Added one to select advisory firms.
        
## 🛠️ Tools & Technologies
- **⚖️ PACER:** – To access fee application documents and other bankruptcy filings.
- **📈 Microsoft Excel:** For exploratory data analysis and quality checks.
- **🔄 Power Query:** ETL tool for data extraction, cleaning, standardization, and transformation.
- **📊 Power BI:** For data modeling, dashboard development, and visualization. 
- **🧮 Data Analysis Expressions:** To support the creation of calculated columns, measures, and custom metrics.
- **💻 Visual Studio Code:** For project documentation, README development, file management, and Git integration.
- **🗂️ Git & GitHub:** For project documentation, portfolio presentation, and version control.

## 💡 Key Findings & Conclusion  
The analysis examines how professional service costs were distributed across the FTX bankruptcy estate and identifies the primary drivers of fee generation.

- Professional firms engaged by FTX billed the estate nearly $1 billion, making the case one of the most expensive bankruptcy proceedings in the US.
- Fee generation was highly concentrated, with Alvarez & Marsal and Sullivan & Cromwell accounting for more than half of total costs.
- Reimbursable expenses represented less than 2% of total costs, indicating that professional fees were the dominant expense category.
- Expenses were dominated by license fees, accomodation, and logistics.
- The analysis found that hours worked were a stronger determinant of total fees than hourly billing rates.
- Owl Hill CEO John Ray earned $48.7m to become highest earner.
- Ernst & Young deployed the largest number of professionals among all firms retained by the estate.
- More than 1,600 professionals were engaged across legal, consulting, accounting, and advisory firms throughout the proceedings.
- Of Counsels were the most expensive professionals with hourly rates exceeding $2,000.

## 📣 Overall Recommendations
- Given the scale of professional fees observed, bankruptcy estates should adopt more standardized and granular reporting formats for fee applications.
- The analysis shows that hours worked are a stronger driver of costs than rates. This suggests that controlling staffing intensity is more effective than negotiating rates alone. Future estates should implement pre-approved budget caps on hours by workstream and require justification for significant overruns.
- The heavy reliance on unstructured PDFs created significant inefficiencies in analysis. Courts and estates should consider adopting standardized digital submission templates to enable automated ingestion, auditing, and analytics.

## Author Information
### Segun Olakoyenikan
Data Analyst and Storyteller

[Return Home](https://github.com/MrKoyee/Power-BI-Dashboard#table-of-contents)