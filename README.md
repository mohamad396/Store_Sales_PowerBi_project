#  E-Commerce Sales Analytics Dashboard 

## Project Overview
 This repository contains the **E-Commerce Sales Analytics Dashboard**, a Power BI-based data analytics project developed by a team of six students enrolled in the DEPI Egypt Power BI specialization program.  The project addresses the growing need for data-driven decision-making in the retail and e-commerce sector by transforming raw transactional data into actionable business intelligence. 

 The analysis is built upon an e-commerce sales dataset containing 10,000 transaction records and 26 columns  , spanning a multi-year period from 2021 to 2023.

---

## Project Objectives
*  **Interactive Monitoring:** Develop an interactive Power BI dashboard that enables stakeholders to monitor sales performance across multiple dimensions including time, geography, category, and customer segment.
*  **Trend Identification:** Identify revenue trends, seasonal patterns, and top-performing products or regions using historical order data.
*  **Customer Behavior Analysis:** Analyze customer behavior by segment (New, Regular, Premium, VIP) to support targeted marketing and retention strategies.
*  **Operational Evaluation:** Evaluate order fulfillment and shipping efficiency to highlight operational bottlenecks.
*  **Profitability Diagnostics:** Present profit margin analysis by product category and sub-category to guide pricing and inventory decisions.

---

## Team Members & Roles
The project development responsibilities are distributed as follows:

| Team Member | Role | Key Responsibilities |
| :--- | :--- | :--- |
| **Mohamed Wael Hasanin** | Project Manager |  Overall coordination, timeline management, stakeholder communication, GitHub repository management. |
| **Fady Nasser** | Data Engineer |  Data cleaning, transformation in Power Query, schema design, data quality checks . |
| **Yousef Mohamed** | Data Analyst - Sales |  Sales performance analysis, DAX measures, Sales Overview and Product Performance pages . |
| **Mohamed Wael Mohamed** | Data Analyst - Customers |  Customer segmentation analysis, DAX measures, Customer Analysis report page . |
| **Abanoub Hany** | Data Analyst - Operations |  Shipping and fulfillment analysis, Operations report page, KPI tracking . |
| **Mahmoud** | Report Designer / QA |  UI/UX design, visual consistency, final report formatting, testing and quality assurance . |

---

## Project Timeline & Milestones
 The project is executed across 6 key phases :

1. **Planning & Management:** Proposal, Gantt Chart, Risk Plan | **Deadline:** 20 Feb 2026 |  **Status:** Completed  
2. **Literature Review:** Research Review, Grading Criteria | **Deadline:** 20 Apr 2026 |  **Status:** Completed  
3. **Requirements Gathering:** User Stories, Functional Specs | **Deadline:** 20 Apr 2026 |  **Status:** Completed  
4. **System Analysis & Design:** ERD, DAX Model, Wireframes | **Deadline:** 1 May 2026 |  **Status:** Completed  
5. **Implementation:** Power BI Report Files, Source Code | **Deadline:** 10 Jul 2026 |  **Status:** Pending  
6. **Final Presentation:** PPT, User Manual, Video Demo | **Deadline:** 17 Jul 2026 |  **Status:** Pending  

>  **Note:** A detailed Gantt chart prepared in Microsoft Excel is available under the repository directory `/docs/gantt_chart.xlsx` .

---

## Data Model Architecture
 The Power BI data model utilizes a industry-standard **Star Schema** architecture to ensure optimal analytical query performance .

### Schema Breakdown
*  **`fact_Orders` (Fact Table):** Central transaction table containing numeric metrics: Revenue, Cost, Profit, Quantity, Discount, and Shipping Cost .
* **`dim_Date` (Dimension):** Time dimension table enabling time-intelligence DAX functions (Year, Month, Quarter, Season) .
* **`dim_Product` (Dimension):** Product hierarchy (Product Name, Category, Sub-Category, Unit Price) allowing deep drill-downs .
* **`dim_Customer` (Dimension):** Customer attributes for demographic and behavioral segmentation analysis (Gender, Segment) .
* **`dim_Geography` (Dimension):** Geographic attributes mapping transactions to specific Regions and Countries.
* **`dim_Shipping` (Dimension):** Operational metrics covering Shipping Method, Payment Method, and Order Status.

### Relationship Integrity
* All dimension tables connect to the `fact_Orders` table via **one-to-many (1:*) relationships** stemming from the dimension side.
* Cross-filter direction is explicitly set to **Single** (dimension to fact) to prevent ambiguity and optimize resource cost.
*  The `dim_Date` table is formally marked as a **Date Table** within Power BI to support reliable time-series modeling.

---

## Core DAX Calculations
 All transactional metrics are calculated dynamically and organized within a dedicated `Measures` table. Core calculations include:

*  **Total Revenue:** `SUM(fact_Orders[Revenue])` 
*  **Total Cost:** `SUM(fact_Orders[Cost])` 
*  **Total Profit:** `[Total Revenue] - [Total Cost]` 
* **Profit Margin %:** `DIVIDE([Total Profit], [Total Revenue], 0)` 
*  **Total Orders:** `COUNTROWS(fact_Orders)` 
* **Avg Order Value:** `DIVIDE([Total Revenue], [Total Orders], 0)` 
*  **Avg Discount Rate:** `AVERAGE(fact_Orders[Discount])` 
* **Avg Shipping Days:** `AVERAGE(fact_Orders[Shipping_Days])` 
*  **YoY Revenue %:** `DIVIDE([Total Revenue] - [Prev Year Revenue], [Prev Year Revenue], 0)` 
*  **MoM Revenue %:** `DIVIDE([Total Revenue] - [Prev Month Revenue], [Prev Month Revenue], 0)` 

---

## Dashboard UI/UX & Layout Design
 The finalized `.pbix` report consists of 4 main analytical views utilizing a strict grid layout, consistent typography (Segoe UI), and a clear page-navigation panel:

1.  **Sales Overview:** High-level executive summary tracking core business health with 4x KPI cards (Revenue, Profit, Orders, Margin), running sales over time, and regional market shares.
2.  **Product Performance:** Identifies top and bottom-performing components using Category revenue bars, a product profitability matrix, and Top-10 structured tables.
3.  **Customer Analysis:** Explores demographic segments using order distribution donut charts, revenue-by-gender splits, and customer value scatter plots.
4.  **Shipping & Operations:** Monitored supply chain efficiency with fulfillment status bars, delivery methods speed arrays, and running return rate indicators.

---

## Technology Stack
* **Data Storage:** Flat CSV files hosted via Git infrastructure.
* **ETL Engineering:** Power Query (M Language) for deep schema cleaning and normalization.
* **Data Model:** Power BI Desktop leveraging the in-memory columnar VertiPaq engine.
* **Analytics Layer:** Data Analysis Expressions (DAX).
* **Publishing Platform:** Power BI Service (Free Tier) with shareable web-link distribution.
* [cite_start]**Version Control:** GitHub for file tracking and continuous asset staging.
