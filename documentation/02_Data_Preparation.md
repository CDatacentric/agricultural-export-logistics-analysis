# Data Preparation | Power Query

## Overview

Data preparation was one of the most important stages of the Agricultural Export Analysis project because the quality of the final analysis depended on the reliability of the underlying data. The dataset initially contained **5,051 records including the header row, representing 5,050 transaction records across 30 fields**. Before building the dashboard or performing deeper analysis, I used Power Query to assess the structure and quality of the dataset, identify inconsistencies, validate important financial fields, and prepare the data for analysis.

I did not approach cleaning as a process of simply removing blanks or changing formats. I first considered what each field represented and how it could affect the business questions I intended to answer. This became particularly important when I encountered missing Shipping Cost values because the field was directly connected to logistics analysis and profitability calculations. Instead of immediately deleting the affected records or filling the blanks with a simple overall average, I investigated the data and tested possible explanations before deciding how the missing values should be handled.

---

# Initial Data Assessment

Before making transformations, I reviewed the dataset to understand the fields available, the types of information they represented, and how they could contribute to the business problem.

The dataset contained a mixture of descriptive and measurable information. Customer, supplier, product, country, port, and shipping information provided the business context, while fields such as Quantity, Unit Price, Revenue, costs, delivery performance, and satisfaction provided the measurable information required for analysis.

This initial review helped me understand which fields would require cleaning, which fields could be used to create new analytical measures, and which fields could be grouped or aggregated during the exploratory analysis.

I also avoided making visualization decisions too early. At this stage, the priority was to understand and prepare the data properly because the cleaning and transformation process itself revealed additional information about the structure of the dataset and influenced the analytical direction later in the project.

---

# Data Structuring

One of the first decisions was to organize the dataset conceptually according to the type of information each field represented. I separated fields that primarily described the business entities involved in each transaction from fields that could be measured, aggregated, or used to calculate business metrics.

The first group included information such as customer, supplier, product, country, and other descriptive attributes. The second group included financial, operational, logistics, and customer-feedback fields such as Quantity, Revenue, costs, Shipping Cost, delivery performance, and Satisfaction Score.

This distinction helped me think about the dataset from an analytical perspective. Instead of viewing the 30 columns as an unrelated collection of fields, I began to understand how they could be connected to the business questions and how they would eventually support PivotTables, charts, KPI cards, and slicers.

---

# Cleaning Text and Standardizing Values

The dataset contained text fields that required standardization before they could be reliably used for grouping and analysis. I used Power Query transformations to clean and standardize these fields rather than manually editing individual records.

The transformation workflow included cleaning text, trimming unnecessary spaces, standardizing capitalization, and replacing inconsistent values where necessary. These steps were important because small differences in text values can cause what should be one category to appear as multiple categories during aggregation.

For example, a product, country, supplier, or other categorical field needs to be consistently represented before it can be reliably grouped in a PivotTable or filtered through a slicer. Power Query allowed these transformations to be applied systematically to the dataset instead of correcting individual cells manually.

The Applied Steps pane records this process through transformations including **Cleaned Text, Trimmed Text, Capitalized Each Word, and multiple Replace Value steps**.

---

# Handling Missing Customer Names

One of the first significant data-quality issues I encountered was missing customer information. The `Customer_Name` field contained **101 missing values**.

I considered whether these records should be removed, but the missing customer name did not prevent the transactions from being used for the financial, logistics, operational, or profitability analysis. Removing the records would therefore have meant losing valid business transactions simply because one descriptive field was incomplete.

I decided to replace the missing customer names with **"Unknown"**. This preserved the transaction records while making the missing information transparent rather than attempting to infer a customer name that was not available in the source data.

This decision allowed the dataset to remain complete for downstream analysis while still distinguishing records where customer information was unavailable.

---

# Validating Revenue Calculations

Another important part of the preparation process was validating the financial information rather than assuming that the values supplied in the dataset were automatically correct.

I independently recalculated **Gross Revenue** using Quantity and Unit Price:

```text
Gross Revenue = Quantity × Unit Price
```

I then recalculated Net Revenue after applying the recorded discount percentage:
```Net Revenue = Gross Revenue - (Gross Revenue × Discount Percentage)
```

These calculations were important because Revenue is a business-critical metric that feeds directly into profitability and performance analysis. Validating the figures before building the dashboard increased confidence that the subsequent analysis was based on internally consistent financial values.

The Power Query Applied Steps show the creation of **Gross Revenue** followed by the creation of **Net Revenue**, reflecting the progression from the original transactional fields into validated analytical measures.

# The Missing Shipping Cost Challenge

The most significant data-quality challenge I encountered during preparation involved the `Shipping_Cost` field.

The dataset contained **152 missing Shipping Cost values**. This represented a relatively small portion of the dataset, but the issue could not be ignored because Shipping Cost was required for logistics analysis and was also an important component of Net Profit.

The screenshot above shows the missing Shipping Cost values directly in Power Query. The blank values were visible while the other financial fields remained populated, which meant that simply removing these records would have resulted in the loss of otherwise usable transactions.

At this point, I had to determine whether the missing Shipping Cost values could be estimated using information already available in the dataset.

# Investigating Shipping Method as a Possible Driver

My first assumption was that Shipping Method might explain differences in Shipping Cost. The dataset contained three shipping methods: Air, Road, and Sea.

I therefore separated the records by Shipping Method and investigated the relationship between Quantity and Shipping Cost within each group. The purpose was to determine whether the shipping method produced a sufficiently consistent unit shipping cost that could be used to estimate missing values.

I investigated Air, Road, and Sea separately rather than assuming that the three methods followed the same pricing pattern.

# Air Shipping Investigation

# Road Shipping Investigation

# Sea Shipping Investigation
