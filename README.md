# Agricultural Export Analysis | Excel Analytics Dashboard

An end-to-end Excel data analytics project that transforms agricultural export transaction data into an interactive executive dashboard. The project demonstrates the complete analytics workflow, from understanding the business problem and preparing the dataset to exploratory analysis using PivotTables, KPI development, dashboard design, business findings, and recommendations.

---

## Quick Navigation

- [Project Overview](#project-overview)
- [Business Problem](#business-problem)
- [Key Business Questions Explored](#key-business-questions-explored)
- [Objectives](#objectives)
- [Project Workflow](#project-workflow)
- [Dashboard Features](#dashboard-features)
- [Key Performance Indicators](#key-performance-indicators)
- [Project Highlights](#project-highlights)
- [Key Findings](#key-findings)
- [Recommendations](#recommendations)
- [Repository Structure](#repository-structure)
- [Project Documentation](#project-documentation)
- [Future Improvements](#future-improvements)
- [About the Author](#about-the-author)

---

# Project Documentation

The complete technical and analytical documentation for this project is available below.

| Document | Description |
|----------|-------------|
| [Project Overview](documentation/01_Project_Overview.md) | Introduces the project, business problem, key business questions, objectives, dataset, and analytical scope. |
| [Data Preparation](documentation/02_Data_Preparation.md) | Documents the Power Query cleaning and transformation process, including data-quality issues, missing values, financial validation, and the Shipping Cost investigation. |
| [Analytical Framework](documentation/03_Analytical_Framework.md) | Explains the calculated columns and the decisions behind the KPI cards, charts, and interactive slicers. |
| [PivotTable Analysis](documentation/04_PivotTable_Analysis.md) | Documents the exploratory analysis performed with PivotTables and the deeper questions generated during the investigation. |
| [Dashboard Design](documentation/05_Dashboard_Design.md) | Explains the wireframe, dashboard layout, visual hierarchy, KPI design, chart selection, slicer placement, and color system. |
| [Dashboard Analysis](documentation/06_Dashboard_Analysis.md) | Documents the most important insights identified from the completed dashboard and supporting exploratory analysis. |
| [Findings and Recommendations](documentation/07_Findings_and_Recommendations.md) | Translates the most important analytical findings into practical recommendations and areas for further investigation. |
| [Project Reflection](documentation/08_Project_Reflection.md) | Reflects on the analytical process, challenges encountered, lessons learned, and skills developed throughout the project. |

---

# Repository Contents

- 1 Interactive Excel Executive Dashboard
- 1 Complete Excel Analysis Workbook
- Power Query data preparation and transformation workflow
- PivotTable exploratory analysis
- Dashboard wireframe
- Executive dashboard preview
- Supporting analytical screenshots
- 8 Technical and analytical documentation files
- Data source documentation

---

# Dashboard Preview

![Executive Dashboard](images/dashboard-preview.png)

---

# Project Overview

The Agricultural Export Analysis project was developed to investigate the financial and operational performance of an agricultural export business using transactional data covering products, customers, suppliers, countries, shipping methods, costs, delivery performance, and customer feedback.

The project began with a business problem rather than a predefined set of charts. Management believed that valuable business opportunities and operational problems were hidden within the available data, creating a need for a structured analytical approach that could reveal where the business was performing well and where further attention might be required.

Before working directly with the dataset, I first studied the project overview and business problem to understand what the analysis was expected to answer. I then reviewed the dataset to understand the story behind the available fields and considered how the information could be connected to the business questions.

The dataset was subsequently prepared and transformed using Power Query. During this stage, I encountered several data-quality challenges, including missing customer information, 152 missing Shipping Cost values, inconsistent data formatting, and financial calculations that required independent validation.

After the data was prepared, calculated columns were created to support time-based, operational, delivery, and customer-satisfaction analysis. The cleaned dataset was then explored using PivotTables. This became an important part of the project because it allowed me to investigate the data beyond the initial dashboard requirements and identify patterns that were not immediately obvious from the raw dataset.

The findings from this exploration were then used to refine the KPI cards, charts, slicers, and overall dashboard design.

The final solution combines data preparation, exploratory analysis, business-focused KPI development, PivotTable investigation, and interactive dashboard design into a single Excel-based analytical workflow.

---

# Business Problem

Management believed that valuable business opportunities and operational problems were hidden within the available export data. However, without a structured analytical approach, it was difficult to determine how the business was performing financially, which products and markets were contributing most to performance, and where operational issues could be affecting profitability and customer experience.

The purpose of this project was to transform the available transaction data into an analytical solution that could provide management with a clear view of financial performance while also helping identify important operational patterns across products, markets, shipping methods, delivery performance, and customer satisfaction.

The analysis therefore focused on connecting the available data to practical business questions rather than simply producing charts from the dataset.

---

# Key Business Questions Explored

The analysis was guided by a small number of important questions that the KPI cards and dashboard visuals were designed to answer quickly.

### 1. How is the business performing financially?

The analysis examines Total Revenue, Total Net Profit, Profit Margin, and Total Orders to provide an immediate view of overall financial and commercial performance.

### 2. Which products and markets are contributing most to business performance?

Product and country performance were compared using Revenue and Net Profit to identify stronger-performing products and markets and areas requiring further investigation.

### 3. How is business performance changing over time?

Monthly and quarterly analysis was used to examine changes in Revenue and Net Profit across 2024 and 2025 and identify periods of stronger or weaker performance.

### 4. Where are the major operational opportunities or problems?

Shipping Cost, Shipping Method, Processing Time, Delivery Delay, and Customer Satisfaction were examined to identify operational patterns that could influence business performance and customer experience.

---

# Objectives

The main objectives of the project were to:

- Understand the business problem before beginning the technical analysis.
- Study and familiarize myself with the available dataset.
- Structure the dataset for analytical use.
- Clean and transform the data using Power Query.
- Identify and resolve important data-quality issues.
- Validate business-critical financial calculations.
- Create calculated columns required for analysis.
- Define business-focused KPI cards, charts, and slicers.
- Use PivotTables to investigate the dataset beyond the initial dashboard requirements.
- Identify important patterns and relationships within the data.
- Design and build an interactive executive dashboard in Excel.
- Present the most important findings in a clear, business-focused format.
- Document the analytical process, challenges, decisions, assumptions, and lessons learned.

---

# Project Workflow

The project followed a structured analytical workflow consisting of eight major stages.

1. **Understand the Business Problem**
2. **Study and Familiarize With the Dataset**
3. **Data Cleaning and Transformation**
4. **Create Calculated Columns**
5. **Define the Analytical Framework**
6. **Exploratory Analysis Using PivotTables**
7. **Dashboard Wireframe and Design**
8. **Build, Analyze, and Document the Executive Dashboard**

The workflow was intentionally iterative. Although the initial business problem established the analytical direction, the final framework evolved as I learned more about the dataset during cleaning, transformation, calculated-column development, and PivotTable exploration.

Detailed documentation for every stage is available in the **documentation** directory.

---

# Dashboard Features

The completed Excel dashboard enables users to:

- Monitor overall financial performance.
- Compare product performance.
- Compare performance across countries and markets.
- Analyze monthly and quarterly trends.
- Evaluate shipping methods and shipping costs.
- Review processing and delivery performance.
- Monitor customer satisfaction.
- Filter results using interactive slicers.
- Explore different business dimensions without rebuilding the analysis.

---

# Key Performance Indicators

The dashboard includes six primary KPI cards:

- **Total Revenue**
- **Total Net Profit**
- **Profit Margin (%)**
- **Total Orders**
- **Average Delivery Delay**
- **Average Satisfaction Score**

These KPIs were selected to provide a concise view of the business's financial performance, transaction activity, operational efficiency, and customer experience.

The KPI values are dynamic and respond to the user's slicer selections, allowing the same dashboard to be used for overall performance as well as filtered analysis by year, quarter, product, country, shipping method, and supplier.

---

# Project Highlights

- Processed and transformed an agricultural export dataset containing **5,050 transaction records across 30 fields**.
- Used Power Query to perform structured data cleaning and transformation.
- Identified **101 missing Customer Name values** and preserved the affected transactions by replacing missing values with `Unknown`.
- Identified **152 missing Shipping Cost values** and investigated potential business drivers before selecting a product-based estimation methodology.
- Tested Shipping Method as a possible Shipping Cost driver by investigating Air, Road, and Sea separately.
- Recalculated and validated key financial metrics including Gross Revenue, Net Revenue, Net Profit, and Profit Margin.
- Created calculated fields to support time-based, operational, delivery, and customer-experience analysis.
- Used PivotTables as an exploratory analytical tool to investigate patterns beyond the initial dashboard requirements.
- Designed the dashboard around business questions rather than selecting visuals independently of the analytical purpose.
- Built an interactive Excel executive dashboard using KPI cards, charts, and slicers.
- Documented the analytical reasoning, challenges, assumptions, findings, recommendations, and lessons learned throughout the project.

---

# Key Findings

The analysis identified several important patterns across financial performance, product and market performance, and operational efficiency.

Rather than listing every observation generated during the exploratory analysis, the final report focuses on findings with stronger business relevance.

### Financial Performance

The business generated approximately **$1.22 billion in Revenue** and **$360.8 million in Net Profit**, resulting in an overall Profit Margin of approximately **20%**.

### Year-over-Year Performance

Although the business remained profitable overall, **2025 recorded lower Revenue and Net Profit than 2024**, indicating that the overall financial position was stronger than the recent performance trend suggested.

### Product Performance

Product analysis showed that strong Revenue performance could be influenced significantly by **Order Quantity**, reinforcing the importance of evaluating Revenue alongside Net Profit and Profit Margin rather than treating Revenue as the only indicator of product performance.

### Country Performance

The **United Kingdom** was one of the strongest financial contributors, generating approximately **$136.1 million in Revenue** and **$39.5 million in Net Profit**.

### Quarterly and Monthly Performance

The quarterly analysis showed that the weaker 2025 performance became more apparent during the later part of the year. Monthly analysis also identified an unusually weak result in **December 2025**, which should be validated before being treated as a confirmed business problem.

### Operational Analysis

The analysis showed that Shipping Method alone was not sufficient to explain differences in Shipping Cost. Operational performance therefore needs to be considered using multiple measures, including Shipping Cost, Processing Time, Delivery Delay, and Customer Satisfaction.

Additional findings and supporting analysis are documented in the project documentation.

---

# Recommendations

Based on the most important findings, the following recommendations were developed:

### 1. Investigate the 2025 Financial Decline

Break down the decline by quarter, product, country, supplier, and order volume to identify the primary contributors.

### 2. Monitor Product Profitability Alongside Sales Volume

Evaluate Revenue, Quantity, Net Profit, and Profit Margin together to distinguish high-volume products from genuinely high-performing products.

### 3. Investigate Strong and Weak Markets

Examine the characteristics behind stronger-performing markets and determine whether successful product, pricing, demand, or operational patterns can be replicated elsewhere.

### 4. Strengthen Logistics Data Collection

Capture additional logistics variables such as shipment weight, distance, freight agreements, and other transportation costs to support more accurate shipping analysis.

### 5. Improve Customer Feedback Data

Introduce structured customer feedback categories, complaint types, and reasons for dissatisfaction to help identify the causes behind changes in customer satisfaction.

Detailed findings and recommendations are documented in the [Findings and Recommendations](documentation/07_Findings_and_Recommendations.md) document.

---

# Repository Structure

```text
agricultural-export-analysis-excel/
│
├── dashboard/
│   └── Agricultural Export Analysis.xlsx
│
├── data/
│   └── README.md
│
├── documentation/
│   ├── 01_Project_Overview.md
│   ├── 02_Data_Preparation.md
│   ├── 03_Analytical_Framework.md
│   ├── 04_PivotTable_Analysis.md
│   ├── 05_Dashboard_Design.md
│   ├── 06_Dashboard_Analysis.md
│   ├── 07_Findings_and_Recommendations.md
│   └── 08_Project_Reflection.md
│
├── images/
│   ├── executive-dashboard.png
│   ├── dashboard-wireframe.png
│   ├── missing-shipping-cost.png
│   ├── filter-shipping-method-air.png
│   ├── filter-shipping-method-road.png
│   ├── filter-shipping-method-sea.png
│   ├── shipping-cost-lookup-merge.png
│   ├── shipping-cost-calculation.png
│   └── recalculated-profit-margin.png
│
├── .gitignore
├── LICENSE
└── README.md

# Project Documentation

The complete project documentation is available in the **documentation** folder.

- [01 — Project Overview](documentation/01_Project_Overview.md)
- [02 — Data Preparation](documentation/02_Data_Preparation.md)
- [03 — Analytical Framework](documentation/03_Analytical_Framework.md)
- [04 — PivotTable Analysis](documentation/04_PivotTable_Analysis.md)
- [05 — Dashboard Design](documentation/05_Dashboard_Design.md)
- [06 — Dashboard Analysis](documentation/06_Dashboard_Analysis.md)
- [07 — Findings and Recommendations](documentation/07_Findings_and_Recommendations.md)
- [08 — Project Reflection](documentation/08_Project_Reflection.md)

---

# Data Source

The dataset used in this project is a **generic, AI-generated dataset created for analytical and portfolio-development purposes**.

It does not represent the actual transactions, financial records, customers, suppliers, or operations of a real agricultural export company.

The dataset was designed to simulate a realistic agricultural export business environment containing financial, operational, logistics, supplier, customer, and product information.

Because the data is synthetic, the findings presented in this project should be interpreted as an analytical demonstration rather than actual business performance results.

The purpose of using this dataset was to demonstrate the complete data analytics workflow, including data preparation, validation, exploratory analysis, dashboard development, and business-oriented interpretation.

---

# Future Improvements

Potential enhancements for future versions include:

- Incorporating additional historical export data for longer-term trend analysis.
- Adding shipment weight and distance information.
- Adding detailed freight and transportation cost components.
- Expanding supplier and customer-level analysis.
- Introducing structured customer feedback and complaint categories.
- Developing automated refresh workflows for recurring reporting.
- Expanding operational efficiency metrics.
- Exploring advanced analytical techniques as additional data becomes available.

---

# About the Author

**Chukwuemeka Onyekaodiri**

Data Analyst

---

## Connect With Me
![My Portrait](images/my-portrait.png)

**Portfolio:** https://www.chukwuemekaonyekaodiri.com/

**LinkedIn:** https://linkedin.com/in/chukwuemeka-onyekaodiri-53881560

**GitHub:** https://github.com/CDatacentric/CDatacentric

---

Thank you for taking the time to explore this project. Feedback and suggestions are always welcome.

---

# License

This project is licensed under the MIT License.
