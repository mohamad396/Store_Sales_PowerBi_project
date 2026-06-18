# [cite_start]E-Commerce Sales Analytics Dashboard [cite: 1]

## Project Overview
[cite_start]This repository contains the **E-Commerce Sales Analytics Dashboard**, a Power BI-based data analytics project developed by a team of six students enrolled in the DEPI Egypt Power BI specialization program[cite: 11]. [cite_start]The project addresses the growing need for data-driven decision-making in the retail and e-commerce sector by transforming raw transactional data into actionable business intelligence[cite: 12]. 

[cite_start]The analysis is built upon an e-commerce sales dataset containing 10,000 transaction records and 26 columns [cite: 21][cite_start], spanning a multi-year period from 2021 to 2023[cite: 92].

---

## Project Objectives
* [cite_start]**Interactive Monitoring:** Develop an interactive Power BI dashboard that enables stakeholders to monitor sales performance across multiple dimensions including time, geography, category, and customer segment[cite: 14].
* [cite_start]**Trend Identification:** Identify revenue trends, seasonal patterns, and top-performing products or regions using historical order data[cite: 15].
* [cite_start]**Customer Behavior Analysis:** Analyze customer behavior by segment (New, Regular, Premium, VIP) to support targeted marketing and retention strategies[cite: 16].
* [cite_start]**Operational Evaluation:** Evaluate order fulfillment and shipping efficiency to highlight operational bottlenecks[cite: 17].
* [cite_start]**Profitability Diagnostics:** Present profit margin analysis by product category and sub-category to guide pricing and inventory decisions[cite: 18].

---

## Team Members & Roles
The project development responsibilities are distributed as follows:

| Team Member | Role | Key Responsibilities |
| :--- | :--- | :--- |
| **Mohamed Wael Hasanin** | Project Manager | [cite_start]Overall coordination, timeline management, stakeholder communication, GitHub repository management[cite: 42]. |
| **Fady Nasser** | Data Engineer | [cite_start]Data cleaning, transformation in Power Query, schema design, data quality checks[cite: 42]. |
| **Yousef Mohamed** | Data Analyst - Sales | [cite_start]Sales performance analysis, DAX measures, Sales Overview and Product Performance pages[cite: 42]. |
| **Mohamed Wael Mohamed** | Data Analyst - Customers | [cite_start]Customer segmentation analysis, DAX measures, Customer Analysis report page[cite: 42]. |
| **Abanoub Hany** | Data Analyst - Operations | [cite_start]Shipping and fulfillment analysis, Operations report page, KPI tracking[cite: 42]. |
| **Mahmoud** | Report Designer / QA | [cite_start]UI/UX design, visual consistency, final report formatting, testing and quality assurance[cite: 46]. |

---

## Project Timeline & Milestones
[cite_start]The project is executed across 6 key phases[cite: 34]:

1. **Planning & Management:** Proposal, Gantt Chart, Risk Plan | **Deadline:** 20 Feb 2026 | [cite_start]**Status:** Completed [cite: 34]
2. **Literature Review:** Research Review, Grading Criteria | **Deadline:** 20 Apr 2026 | [cite_start]**Status:** Completed [cite: 34]
3. **Requirements Gathering:** User Stories, Functional Specs | **Deadline:** 20 Apr 2026 | [cite_start]**Status:** Completed [cite: 34]
4. **System Analysis & Design:** ERD, DAX Model, Wireframes | **Deadline:** 1 May 2026 | [cite_start]**Status:** Completed [cite: 34]
5. **Implementation:** Power BI Report Files, Source Code | **Deadline:** 10 Jul 2026 | [cite_start]**Status:** Pending [cite: 34]
6. **Final Presentation:** PPT, User Manual, Video Demo | **Deadline:** 17 Jul 2026 | [cite_start]**Status:** Pending [cite: 34]

> [cite_start]**Note:** A detailed Gantt chart prepared in Microsoft Excel is available under the repository directory `/docs/gantt_chart.xlsx`[cite: 36].

---

## Data Model Architecture
[cite_start]The Power BI data model utilizes a industry-standard **Star Schema** architecture to ensure optimal analytical query performance[cite: 153].

### Schema Breakdown
* [cite_start]**`fact_Orders` (Fact Table):** Central transaction table containing numeric metrics: Revenue, Cost, Profit, Quantity, Discount, and Shipping Cost[cite: 154].
* **`dim_Date` (Dimension):** Time dimension table enabling time-intelligence DAX functions (Year, Month, Quarter, Season)[cite: 155].
* **`dim_Product` (Dimension):** Product hierarchy (Product Name, Category, Sub-Category, Unit Price) allowing deep drill-downs[cite: 156].
* **`dim_Customer` (Dimension):** Customer attributes for demographic and behavioral segmentation analysis (Gender, Segment)[cite: 157].
* **`dim_Geography` (Dimension):** Geographic attributes mapping transactions to specific Regions and Countries[cite: 159].
* **`dim_Shipping` (Dimension):** Operational metrics covering Shipping Method, Payment Method, and Order Status[cite: 160].

### Relationship Integrity
* All dimension tables connect to the `fact_Orders` table via **one-to-many (1:*) relationships** stemming from the dimension side[cite: 161].
* Cross-filter direction is explicitly set to **Single** (dimension to fact) to prevent ambiguity and optimize resource cost[cite: 162].
* [cite_start]The `dim_Date` table is formally marked as a **Date Table** within Power BI to support reliable time-series modeling[cite: 163].

---

## Core DAX Calculations
[cite_start]All transactional metrics are calculated dynamically and organized within a dedicated `Measures` table[cite: 139, 175]. Core calculations include:

* [cite_start]**Total Revenue:** `SUM(fact_Orders[Revenue])` [cite: 164]
* [cite_start]**Total Cost:** `SUM(fact_Orders[Cost])` [cite: 165]
* [cite_start]**Total Profit:** `[Total Revenue] - [Total Cost]` [cite: 165]
* **Profit Margin %:** `DIVIDE([Total Profit], [Total Revenue], 0)` [cite: 166]
* [cite_start]**Total Orders:** `COUNTROWS(fact_Orders)` [cite: 166]
* **Avg Order Value:** `DIVIDE([Total Revenue], [Total Orders], 0)` [cite: 167]
* [cite_start]**Avg Discount Rate:** `AVERAGE(fact_Orders[Discount])` [cite: 167]
* **Avg Shipping Days:** `AVERAGE(fact_Orders[Shipping_Days])` [cite: 168]
* [cite_start]**YoY Revenue %:** `DIVIDE([Total Revenue] - [Prev Year Revenue], [Prev Year Revenue], 0)` [cite: 168]
* [cite_start]**MoM Revenue %:** `DIVIDE([Total Revenue] - [Prev Month Revenue], [Prev Month Revenue], 0)` [cite: 169]

---

## Dashboard UI/UX & Layout Design
[cite_start]The finalized `.pbix` report consists of 4 main analytical views utilizing a strict grid layout, consistent typography (Segoe UI), and a clear page-navigation panel[cite: 123, 185, 186, 188]:

1. [cite_start]**Sales Overview:** High-level executive summary tracking core business health with 4x KPI cards (Revenue, Profit, Orders, Margin), running sales over time, and regional market shares[cite: 125, 178].
2. [cite_start]**Product Performance:** Identifies top and bottom-performing components using Category revenue bars, a product profitability matrix, and Top-10 structured tables[cite: 126, 179].
3. [cite_start]**Customer Analysis:** Explores demographic segments using order distribution donut charts, revenue-by-gender splits, and customer value scatter plots[cite: 127, 180].
4. [cite_start]**Shipping & Operations:** Monitored supply chain efficiency with fulfillment status bars, delivery methods speed arrays, and running return rate indicators[cite: 128, 181].

---

## Technology Stack
* [cite_start]**Data Storage:** Flat CSV files hosted via Git infrastructure[cite: 189].
* **ETL Engineering:** Power Query (M Language) for deep schema cleaning and normalization[cite: 190].
* [cite_start]**Data Model:** Power BI Desktop leveraging the in-memory columnar VertiPaq engine[cite: 191].
* [cite_start]**Analytics Layer:** Data Analysis Expressions (DAX)[cite: 192].
* **Publishing Platform:** Power BI Service (Free Tier) with shareable web-link distribution[cite: 194].
* [cite_start]**Version Control:** GitHub for file tracking and continuous asset staging[cite: 195].
