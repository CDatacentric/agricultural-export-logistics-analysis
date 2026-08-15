# Analytical Framework

## From Prepared Data to Business Questions

Once the dataset had been cleaned and validated, the next stage was to make the data analytically useful. At this point, I had a much better understanding of the fields available, the relationships between them, and the types of business questions that could realistically be answered from the dataset.

I did not want to select charts simply because certain columns were available. The objective was to build an analytical framework where each KPI, chart, and slicer had a clear purpose and contributed to answering the business questions identified at the beginning of the project.

Before defining the dashboard visuals, I first created several calculated columns that would make the dataset easier to analyze across time, operations, delivery performance, and customer satisfaction.

---

# Calculated Columns

The calculated columns were created to support the analytical questions that emerged from understanding and cleaning the dataset. Some of these fields were not directly available in the original data but could be derived from existing fields and were useful for grouping, filtering, and calculating business metrics.

The main calculated fields included:

- Order Date Year
- Order Date Month
- Order Date Days
- Ship Date Year
- Ship Date Month
- Ship Date Days
- Delivery Date Year
- Delivery Date Month
- Delivery Date Days
- Delivery Time
- Order Processing Time
- Order Month & Year
- Quarterly (2024 and 2025)
- Satisfaction Score
- Overall Average Delivery Delay Days

These calculations helped transform individual transaction-level fields into analytical dimensions and measures that could be used in PivotTables, charts, KPI calculations, and slicers.

---

## Building Time-Based Fields

The original date fields provided the individual transaction dates, but analyzing business performance over time required more structured time dimensions.

I therefore created separate Year, Month, and Day fields for Order Date, Ship Date, and Delivery Date. I also created an **Order Month & Year** field to provide a chronological period that could be used to analyze monthly Revenue and Net Profit.

A quarterly field was also created to support comparison across quarters in 2024 and 2025.

These fields became particularly useful later when analyzing whether business performance was changing over time rather than looking only at the overall totals.

The objective was not simply to create additional columns. Each calculated field was created because it supported a specific analytical requirement.

---

## Measuring Operational Time

The dataset contained several dates that made it possible to investigate the time taken between different stages of the order and delivery process.

I created **Delivery Time** and **Order Processing Time** fields so that operational performance could be measured rather than relying only on the original date fields.

These calculations later supported the analysis of processing time and delivery delay by Shipping Method, allowing me to compare operational performance across Air, Road, and Sea.

This was important because a business can have strong financial performance while still experiencing operational inefficiencies that may affect customer experience or future profitability.

---

## Customer Satisfaction

Customer satisfaction was another area that required a consistent analytical measure.

I created the **Satisfaction Score** field and used it to support the overall customer-experience analysis. The resulting metric was incorporated into the dashboard as **Average Satisfaction Score**, allowing customer feedback to be monitored alongside financial and operational performance.

This helped ensure that the dashboard did not focus exclusively on Revenue and Profit while ignoring the customer experience.

---

# Defining the Analytical Framework

With the calculated fields available, I could now determine which measures were most important for the executive dashboard.

The analytical framework was built around three main components:

1. **KPI Cards** — provide an immediate summary of business performance.
2. **Charts** — provide context, comparison, and trends behind the KPI results.
3. **Slicers** — allow users to investigate the results across important business dimensions.

The selection of each component was connected to the business questions rather than being based solely on what could be visualized in Excel.

---

# KPI Cards

The KPI cards were designed to answer the most important high-level questions immediately when the dashboard is opened.

The final KPI cards were:

| KPI | Purpose |
|---|---|
| Total Revenue | Measures overall business revenue. |
| Total Net Profit | Measures the profit remaining after the relevant costs. |
| Profit Margin (%) | Measures profitability relative to Net Revenue. |
| Total Orders | Provides a view of overall transaction activity. |
| Average Delivery Delay | Measures delivery performance and operational reliability. |
| Average Satisfaction Score | Provides an immediate view of customer experience. |

These six KPIs were intentionally limited to the measures that management would most likely need to understand the overall business position before investigating specific areas.

The objective was to make the dashboard understandable **at a glance** without requiring the reader to study every chart first.

---

# Charts

The charts were selected to provide the context behind the KPI cards and answer the next level of business questions.

## Product Performance

**Chart:** Revenue & Profit by Product

This chart compares Revenue and Net Profit across products to identify which products contribute most strongly to financial performance.

The visual supports the question:

> Which products are contributing most to business performance?

It also provides a starting point for deeper investigation using PivotTables where necessary.

---

## Market Performance

**Chart:** Market Performance by Country

Revenue and Net Profit were compared across all countries in the dataset.

This allows the analysis to move beyond the overall company result and examine where business activity is concentrated and which markets contribute more strongly to financial performance.

The visual supports the question:

> Which markets are contributing most to the business?

---

## Monthly Performance

**Chart:** Monthly Performance

Revenue and Net Profit were plotted across the reporting period using the calculated Month & Year field.

This visual was included because an overall Revenue or Profit figure can hide changes occurring throughout the year. Monthly analysis makes it possible to identify periods of stronger or weaker performance and provides a basis for further quarterly investigation.

The visual supports the question:

> How is business performance changing over time?

---

## Shipping Cost by Method

**Chart:** Shipping Cost by Method

Shipping Cost was compared across Air, Road, and Sea.

The purpose of this chart was to provide visibility into the logistics cost associated with the different shipping methods and support further investigation of operational performance.

The visual supports the question:

> Where are there potential differences in shipping cost across transportation methods?

---

## Processing Time vs. Delivery Delay

**Chart:** Processing Time vs. Delivery Delay Days

Average Processing Time and Average Delivery Delay were compared across Shipping Method.

This chart was designed to examine operational performance from two related perspectives: how long orders take to process and how long delivery delays average across the different shipping methods.

The visual supports the question:

> Which shipping methods show different processing and delivery performance?

---

# Slicers

The slicers were selected to allow users to move from the overall business view into specific segments of the data.

The final dashboard includes:

- **Year**
- **Quarter**
- **Product**
- **Country**
- **Shipping Method**
- **Supplier**

Each slicer provides a different analytical perspective.

### Year and Quarter

These allow users to investigate performance across different reporting periods and compare changes over time.

### Product

Allows users to isolate individual products and examine their financial and operational performance.

### Country

Allows market-level investigation and comparison.

### Shipping Method

Allows users to examine Air, Road, and Sea separately and investigate differences in shipping cost, processing time, and delivery delay.

### Supplier

Allows supplier-level filtering where further investigation is required.

---

# Connecting the Framework to the Business Questions

The analytical framework was designed so that the KPI cards provide the immediate answer while the charts provide the explanation and the slicers provide the ability to investigate further.

For example, the KPI cards can immediately show whether Revenue and Net Profit are strong while Average Delivery Delay and Satisfaction Score indicate potential operational or customer-experience concerns. The charts then provide context by showing which products, countries, months, or shipping methods may be contributing to those results.

This approach helped prevent the dashboard from becoming a collection of unrelated visuals. Each component has a role in moving the reader from the overall result toward the underlying business story.

---

# Dashboard Information Hierarchy

The dashboard was therefore designed around three levels of analysis:

### Level 1 — What is happening?

The KPI cards provide the immediate overall performance picture.

### Level 2 — Where is it happening?

The charts break the performance down by Product, Country, Month, and Shipping Method.

### Level 3 — What should I investigate further?

The slicers and PivotTables allow the user to investigate specific products, markets, periods, suppliers, and shipping methods.

This structure helped create a dashboard that could function as an executive overview while still supporting deeper analysis when required.

---

# Analytical Framework Outcome

By the end of this stage, the dataset had been transformed from a collection of transaction records into a structured analytical foundation.

The calculated columns provided the required analytical dimensions, while the KPI cards, charts, and slicers provided the framework for communicating the most important business questions.

The next stage was to use **PivotTables as an exploratory analysis tool**. This was particularly important because the dashboard could answer the predefined questions, but I wanted to investigate whether the dataset contained additional patterns that were not immediately visible through the initial dashboard structure.

That exploratory process became one of the most valuable parts of the project because it allowed me to move beyond simply reporting what was already visible and start asking deeper analytical questions.
