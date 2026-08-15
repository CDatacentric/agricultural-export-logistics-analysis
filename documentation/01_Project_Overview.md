# Project Overview

## Agricultural Export Analysis | Excel Analytics Dashboard

The Agricultural Export Analysis project was developed to investigate the financial and operational performance of an agricultural export business using transactional data covering products, customers, suppliers, markets, shipping methods, costs, delivery performance, and customer feedback.

The project started with a business problem rather than a predefined set of charts. Management believed that valuable business opportunities and operational problems were hidden within the available data, creating a need for a structured analytical approach that could reveal where the business was performing well and where further attention might be required.

Before working directly with the dataset, I first studied the project overview and business problem to understand what the analysis was expected to answer. I then reviewed the dataset to understand the story behind the available fields and considered how the information could be connected to the business questions. This helped establish the analytical direction before moving into data preparation.

The dataset was subsequently prepared and transformed using Power Query. During this stage, I encountered several data-quality challenges, including missing customer information, 152 missing Shipping Cost values, inconsistent data formatting, and financial calculations that required independent validation. Rather than treating cleaning as a purely technical exercise, I investigated the business context behind the issues and used the available data to determine the most defensible solutions.

After the data was prepared, calculated columns were created to support time-based, operational, delivery, and customer-satisfaction analysis. The cleaned dataset was then explored using PivotTables. This became an important part of the project because it allowed me to investigate the data beyond the initial dashboard requirements and identify patterns that were not immediately obvious from the raw dataset.

The analytical findings from this process were then used to define the dashboard's KPI cards, charts, and slicers. A wireframe was created before building the final executive dashboard, ensuring that the visual structure supported the analytical story rather than simply displaying available fields.

The final solution combines data preparation, exploratory analysis, business-focused KPI development, PivotTable investigation, and interactive dashboard design into a single Excel-based analytical workflow.

---

## Business Problem

Management believed that valuable business opportunities and operational problems were hidden within the available export data. However, without a structured analytical approach, it was difficult to determine how the business was performing financially, which products and markets were contributing most to performance, and where operational issues could be affecting profitability and customer experience.

The purpose of this project was to transform the available transaction data into an analytical solution that could provide management with a clear view of financial performance while also helping identify important operational patterns across products, markets, shipping methods, delivery performance, and customer satisfaction.

The analysis therefore focused on connecting the available data to practical business questions rather than simply producing charts from the dataset.

---

# Key Business Questions Explored

The analysis was guided by a small number of important questions that the KPI cards and dashboard visuals were designed to answer quickly.

### 1. How is the business performing financially?

The analysis examines Total Revenue, Total Net Profit, Profit Margin, and Total Orders to provide an immediate view of overall financial and commercial performance.

### 2. Which products and markets are contributing most to business performance?

Product and country performance were compared using Revenue and Net Profit to identify stronger-performing markets and products and areas requiring further investigation.

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
- Present the most important findings in a concise, business-focused format.
- Document the analytical process, challenges, decisions, and lessons learned.

---

# Dataset Overview

The Agricultural Export Analysis dataset contains **5,051 records, including the header row, across 30 fields** representing transactional activity for an agricultural export company.

The available information covers several areas of the business, including:

- Customer information
- Supplier information
- Product and product category
- Quantity
- Unit Price
- Revenue
- Discounts
- Production Cost
- Shipping Cost
- Insurance Cost
- Taxes
- Shipping Method
- Port
- Order and delivery dates
- Processing and delivery performance
- Customer satisfaction

The combination of financial, operational, logistics, and customer-related information made it possible to investigate the business from multiple analytical perspectives rather than focusing on financial performance alone.

---

# Analytical Scope

The project focused on five major analytical areas:

### Financial Performance

Revenue, Net Revenue, Net Profit, Profit Margin, and Order activity were analyzed to understand the overall financial performance of the business.

### Product Performance

Products were compared based on Revenue and Net Profit to understand their contribution to the business.

### Market Performance

Country-level Revenue and Net Profit were analyzed to identify stronger and weaker markets.

### Operational and Shipping Performance

Shipping Method, Shipping Cost, Processing Time, and Delivery Delay were examined to identify potential operational differences.

### Customer Experience

Customer Satisfaction Score was included as an important measure of customer experience and was analyzed alongside the broader operational performance of the business.

---

# Project Scope

The project covers the complete analytical process from initial business understanding through data preparation, exploratory analysis, dashboard development, and interpretation of findings.

The primary tools used were:

- **Microsoft Excel**
- **Power Query**
- **PivotTables**
- **Excel Charts**
- **Excel Slicers**

The final output is an interactive executive dashboard designed to provide a concise view of business performance while allowing users to investigate specific periods, products, countries, shipping methods, and suppliers.

---

# Project Outcome

The completed project provides an interactive Excel dashboard that brings together financial, product, market, logistics, and customer-experience measures in one reporting environment.

More importantly, the project demonstrates an analytical workflow in which the dashboard was not treated as the starting point. The analytical direction evolved through understanding the business problem, studying and cleaning the dataset, creating supporting calculations, exploring the data with PivotTables, and using the resulting insights to determine what the final dashboard needed to communicate.

The project therefore represents both an Excel analytics solution and a documented demonstration of how I approach a real-world data analysis problem from the initial business question through to the final presentation of insights.

---

# Related Documentation

The following documents provide more detail about each stage of the project:

- [Data Preparation](02_Data_Preparation.md)
- [Analytical Framework](03_Analytical_Framework.md)
- [PivotTable Analysis](04_PivotTable_Analysis.md)
- [Dashboard Design](05_Dashboard_Design.md)
- [Dashboard Analysis](06_Dashboard_Analysis.md)
- [Project Reflection](07_Project_Reflection.md)
