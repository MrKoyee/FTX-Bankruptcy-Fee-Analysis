#  [FTX Bankruptcy Professional Fees and Asset Recovery Analytics](#ftx-bankruptcy-professional-fees-and-asset-recovery-analytics)
## [Table of Contents](#table-of-contents)
 
  - [📊 Dashboard Preview](#-dashboard-preview)
  - [📖 Project Overview](#-project-overview)
  - [🎯 Business Questions](#-business-questions)
  - [❓ Business Problem: Why This Project Matters](#-business-problem-why-this-project-matters)
  - [🗂️ Dataset Information](#️-dataset-information)
  - [🧠 Skills Showcased](#-skills-showcased)
  - [🛠️ Tools \& Technologies](#️-tools--technologies)
  - [💡 Key Findings](#-key-findings)
    - [Cost of the Bankruptcy Process](#cost-of-the-bankruptcy-process)
    - [Professional Fee Drivers](#professional-fee-drivers)
    - [Expense Analysis](#expense-analysis)
    - [Asset Recovery and Efficiency](#asset-recovery-and-efficiency)
  - [🎯 Conclusion](#-conclusion)
  - [📣 Overall Recommendations](#-overall-recommendations)
  - [👤 Author Information](#-author-information)
    


## 📊 Dashboard Preview

![Dashboard Page 1](/Images/FTX_1.png)

[View Interactive Dashboard](https://app.powerbi.com/view?r=eyJrIjoiYTBmNTQxZjQtOWQ1MC00ZmE5LTk5NTMtYjA2Y2M2MTI1MjZhIiwidCI6IjRiMmE0YjE5LWQxMzUtNDIwZS04YmIyLWIxY2QyMzg5OThjYyIsImMiOjF9)


## 📖 Project Overview

This project analyzes the professional fees incurred during the bankruptcy proceedings of **FTX Trading Ltd.** and evaluates them in the context of the company's asset recovery efforts. The analysis breaks down nearly $1bn in fees while examining how these costs relate to the recovery of $16.5bn assets available to creditors.

FTX's journey to bankruptcy gained global prominence in 2022 when the 🪙 crypto exchange collapsed and then sought bankruptcy protection in a move that resulted into one of the most complex and high-profile Chapter 11 cases in the US.

Chapter 11 allows financially distressed companies to restructure their operations and obligations while retaining control. As part of this process, companies often retain a wide range of professional advisors who support critical activities such as asset recovery, litigation, forensic investigations, claims administration, and the distribution of funds to creditors.

The advisors are required to publicly disclosed the compensation earned for these services through applications filed on the bankruptcy docket. These disclosures create a rich and transparent dataset that provides valuable insight into how professional services are used during a case. More so, stakeholders can identify the firms engaged, understand the nature of the services provided, and analyze how restructuring costs accumulate over the bankruptcy period.

This project collected and scraped dozens of fee applications from the FTX bankruptcy docket, and then transformed the raw and unstructured PDF filings into a structured dataset for analysis. 

## 🎯 Business Questions

Professional fee analysis serves multiple stakeholders within the restructuring ecosystem. However, for the purpose of this project, the following business questions were established to guide the analysis and evaluate both the costs and outcomes of the court-supervised restructuring:

- **💰 Spending Analysis: Where did the money go?**
    - How much did FTX spend on professional services?
    - Which advisory firms received the largest share of professional fees?
    - How were these fees distributed across service categories?
    - Were bankruptcy costs concentrated among a small number of firms or spread across many advisors?
    - Which professionals generated the highest billable fees throughout the case?

- **👥 Resource Utilization**
    - Which employee titles generated the highest billable fees?
    - Which professionals recorded the highest number of billable hours?
    - Which firms deployed the largest teams?

- **💵 Billing Rate Analysis**
    - Which firms command the highest average billing rates?
    - How do billing rates differ across professions and job titles?
    - What's the biggest driver of advisor fees?
  
- **💵 Asset Recovery and Efficiency Analysis: What's the outcome?**
    - How much value was ultimately recovered for creditors during the FTX bankruptcy?
    - What was the fee-to-recovery ratio?
    - How much value was recovered for every dollar spent on professional services?

The goal is to answer all these questions and provide even more insights into the restructuring case. 

## ❓ Business Problem: Why This Project Matters

Companies facing financial distress often seek protection through the bankruptcy courts. While Chapter 11 provides a structured framework for maximizing recoveries for creditors, the process can be very expensive.

Advisors involved in the case of FTX charged nearly $1bn in professional fees. When viewed in isolation, this amount provides little insight into the effectiveness of the process. However, the true significance of these costs can be determined in the context of the value recovered for creditors. Bankruptcy costs could become a concern when they consume a substantial portion of the assets available for distribution, reducing the net recovery available to creditors and other stakeholders.

This project therefore examines not only how professional fees were accumulated and distributed among advisors, but also how those costs compare to the assets recovered through the bankruptcy process, providing a more complete assessment of the efficiency and value generated by the proceedings.


## 🗂️ Dataset Information
Multiple datasets were extracted from the fee application filings and consolidated into structured tables containing key data points, including:

- Advisory firms, role, party represented, service category, and blended rate.
- Professional name, title, hours billed, billing rate and fees requested.
- Total amount requested, approved and paid for fees and expenses.
- Fee application period.
- Application type (interim or final).
- Expense reimbursements requested and category.
- Total assets recovered by FTX.

## 🧠 Skills Showcased
- **🗂️ Data Extraction from PDFs**   
    This was the most technically demanding phase of the project. The FTX bankruptcy generated dozens of fee applications filed by various firms. In total, 76 filings were downloaded from the court docket and stored in a dedicated local repository for processing.

    The first challenge involved transforming these unstructured court filings into a format suitable for analysis. Relevant tables were extracted directly from each filing and reviewed individually using Power Query's native PDF connector.

    This process required extensive validation and standardization because the fee applications were prepared by different firms and often followed inconsistent formats and reporting conventions.

    A key observation was that these documents were designed primarily for court reporting and regulatory compliance rather than analytical use. As a result, significant effort was required to identify relevant data fields, reconcile structural differences across filings, and create a consistent dataset suitable for meaningful cleaning and analysis.

    During the extraction process, several recurring data quality issues were identified, such as:

    - Inconsistent table structures
    - Merged cells
    - Multi-page tables that were split during PDF extraction
    - Missing or incomplete values
    - Different naming conventions
    - Varying date formats
    - Duplicate records across filings
    - Non-tabular content embedded within extracted tables

- **🧹 Power Query Transformation Process for Data Cleaning**  
This phase focused on resolving the data quality issues identified during the extraction process to create a clean and reliable dataset for analysis. Column names and data formats were standardized across all imported tables, while professional firms and individuals were categorized according to their roles and responsibilities in the proceedings.

    Similarly, expense records were reviewed and categorized, reducing 154 unique expense descriptions to 32 standardized expense categories. This transformation improved data quality, facilitated cross-firm comparisons, and provided a clearer view of how reimbursable expenses were incurred.

- **🗃️ Data Model in Power BI**   
Once the data was cleaned and standardized, a dimensional data model was developed to support analysis and reporting. The final model consisted of four dimension tables and seven fact tables, providing a foundation for measures, dashboard development, slicers, and performance analysis. Relationships were subsequently defined between the tables using key fields, creating a star-schema model that facilitated efficient querying, cross-table analysis, and accurate measure calculations.

- **📐 DAX Measures**  
  A deliberate design decision was made to prioritize DAX measures over calculated columns for this project. This approach improved model efficiency and allowed calculations to respond dynamically to interactions and filter selections. A range of custom measures was written in DAX and organized within a dedicated measures table to support key performance indicators, recovery metrics, and interactive dashboard analytics. 


- **📊 Dashboards & Visualization**  
Two dashboards were developed and connected through navigation buttons to enhance the user experience. One dashboard focuses on advisory firms and their fee activity, while the other provides a detailed analysis of individual professionals across those firms.

    - **Dashboard 1: Advisory Firms** 
    - 
      ![Dashboard Page 1](/Images/FTX_1.png)

        - **KPI Cards:** Total Amount Requested, Asset Recovered, Average Hourly Rate, Fee-to-Expense Ratio = Amount/Asset Recovered * 100%, and Recovery Efficiency = Asset Recovered/Amount.
        - **Extra KPI Cards:** Number of firms, fee and expense ratios.
        - **Bar Chart:** Top advisory firms by amount charged.
        - **Donut Chart:** Firm share of amount charged.
        - **Treemap:** Share of advisory firm categories.
        - **Scatter Chart:** Three-in-one dynamic scatter charts to show how hours, team size and rates related with fees.
        - **Stacked Bar Chart:** Workforce breakdown.
        - **Funnel Chart:** Visualizes the progression of professional fees from the amounts initially requested to the amounts ultimately paid. PCR refers to the Post-Confirmation Report, where reported payment (Paid-PCR) amounts may differ slightly from those disclosed in the final fee applications (Paid) due to subsequent adjustments, reconciliations, or approved distributions.
        - **Slicer:** For filtering advisory firms based on the client(s) they served.
        - **Buttons:** The first dashboard features four sets of buttons that power the interactive interface. 



    - **Dashboard 2: Professionals**
    - 
        ![Dashboard Page 2](/Images/FTX_2.png)
        
        - **KPI Cards:** Total Professional Fees, Number of Professionals, Average Hourly Rate, Total Professional Hours, and Average Professional Hours.
        - **Bar Charts:** Top professionals by compensation, rates by job titles, and a breakdown of expenses by amount.
        - **Line and Clustered Column Chart:** Professionals by billable hours and hourly rates.
        - **Slicer:** Three slicers were added to filter fee type, part represented and advisory firms.
        
## 🛠️ Tools & Technologies
- **⚖️ PACER:** – To access fee application documents and other bankruptcy filings.
- **📈 Microsoft Excel:** For exploratory data analysis and quality checks.
- **🔄 Power Query:** ETL tool for data extraction, cleaning, standardization, and transformation.
- **📊 Power BI:** For data modeling, dashboard development, and visualization. 
- **🧮 Data Analysis Expressions:** To support the creation of calculated columns, measures, and custom metrics.
- **💻 Visual Studio Code:** For project documentation, README development, file management, and Git integration.
- **🗂️ Git & GitHub:** For project documentation, portfolio presentation, and version control.

## 💡 Key Findings 
The analysis examines the distribution of professional fees across the FTX bankruptcy estate, identifies the primary drivers of advisory costs, and evaluates the relationship between those costs and the $16.5bn recovered. 

### Cost of the Bankruptcy Process

* The FTX's case generated nearly **$1bn in professional fees**, making it one of the most expensive bankruptcy cases in recent history.

* More than **2,000 professionals** were engaged across **22 advisory firms** throughout the proceedings.

* Professional fees were highly concentrated among a small number of firms, with **Alvarez & Marsal** and **Sullivan & Cromwell** accounting for more than half of all compensation paid by FTX.

* **Ernst & Young** deployed the largest workforce among all firms retained by FTX.

### Professional Fee Drivers

* The analysis found that **hours billed has the strongest positive correlation with professional fees**, indicating that total compensation was driven more by workload and time commitment than by staffing levels or billing rates alone.

* Significant variation existed in billing rates, hours worked, and total compensation across firms and professional roles, reflecting differences in expertise, responsibilities, and scope of work.

* **Of Counsel** professionals were the highest-billing professionals, with hourly rates exceeding **$2,200**.

* Among individual professionals, **John J. Ray III** of Owl Hill Advisory earned approximately **$48.7m**, making him the highest-compensated professional in the proceedings. His compensation included approximately **$38.1m in incentive fees** and a **$3m completion bonus**.

### Expense Analysis

* Expense reimbursements represented less than **2% of total compensation**, which indicates that labor costs were overwhelmingly the primary driver of bankruptcy-related expenditures.

* Reimbursable expenses were concentrated in a small number of categories, with **license fees, professional services, transportation, accommodation, and data services** accounting for the largest share of expense claims.

### Asset Recovery and Efficiency

* Despite incurring substantial professional costs, FTX recovered **$16.5bn in assets** for creditors and other stakeholders.

* Professional fees represented approximately **6% of total assets recovered**, leaving the vast majority of recovered value available for creditor distributions.

* FTX recovered approximately **$20 of value for every dollar spent on professional services**, indicating that recovery outcomes significantly exceeded the costs incurred during the restructuring process.



## 🎯 Conclusion

Overall, the analysis suggests that while the FTX bankruptcy was exceptionally expensive, professional costs represented a relatively small proportion of the value ultimately preserved and recovered for creditors.


## 📣 Overall Recommendations

* The analysis found that hours worked were a stronger driver of professional fees than either staffing levels or hourly billing rates. As a result, cost-control efforts should focus on monitoring workload allocation, staffing intensity, and time utilization. 

* The heavy reliance on unstructured PDF filings created significant challenges for data extraction, validation, and analysis. Courts and estates should consider adopting standardized digital submission templates or structured reporting formats that support automated ingestion, auditing, and analytics.

* Finally, bankruptcy courts and restructuring professionals should consider developing industry-wide benchmarking frameworks for professional fees, staffing models, and recovery outcomes. Such benchmarks would help stakeholders evaluate whether costs incurred in future cases are reasonable relative to the complexity of the proceedings and the value ultimately recovered.


## 👤 Author Information
### Segun Olakoyenikan
Data Analyst and Storyteller

[Return Home](https://github.com/MrKoyee/Power-BI-Dashboard#ftx-bankruptcy-fees-data-analysis)