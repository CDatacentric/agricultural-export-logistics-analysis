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

## Air Shipping Investigation
![Filtered Shipping Method by Air](images/filtered-shipping-method-by-air.png)

## Road Shipping Investigation
![Filtered Shipping Method by Road](images/filtered-shipping-method-by-road.png)

## Sea Shipping Investigation
![Filtered Shipping Method by Sea](images/filtered-shipping-method-by-sea.png)


The investigation showed that Shipping Cost varied considerably even within the same shipping method. Similar quantities could have significantly different shipping costs, and the observed values did not provide a sufficiently consistent unit-cost relationship that would allow Shipping Method alone to be used as a reliable estimator.

This was an important analytical discovery because it prevented me from applying an assumption that appeared reasonable at first but was not sufficiently supported by the data. The investigation also suggested that Shipping Cost was likely influenced by additional factors that were not available in the dataset, such as shipment characteristics, transportation conditions, route-specific costs, or other operational factors. Because Shipping Method alone did not provide a reliable basis for estimating the missing values, I needed another approach.

# Developing a Product-Based Estimation Method

After investigating Shipping Method, I looked for a variable that could provide a more consistent basis for estimating shipping cost.

I selected Product Name because products can have different handling, packaging, and transportation characteristics. Rather than assuming that all shipments using the same transportation method would have comparable costs, I investigated whether the existing Shipping Cost records could be used to calculate an average unit shipping cost for each product.

The first step was to calculate:
```Unit Shipping Cost = Shipping Cost ÷ Quantity
```
![Unit Shipping Cost](images/unit-shipping-cost.png)
This converted the available Shipping Cost values into a comparable per-unit measure.

I then created a duplicate query and grouped the available records by Product Name to calculate the **Average Unit Shipping Cost** for each product. This created a product-level lookup table that could be used to estimate the missing values.

The resulting calculation created fields including **Unit Shipping Cost, Average by Product, Estimated Shipping Cost, and Final Shipping Cost**. The screenshot demonstrates how the calculated values were brought together during the transformation process.

# Merging the Product-Level Lookup Table
![Merged Unit Shipping Cost](images/merged-unit-shipping-cost.png)
Once the average unit shipping cost had been calculated for each product, I needed to bring those values back into the main dataset.

I used a Merge Queries operation based on `Product_Name`, using a Left Outer Join so that every record in the main dataset would remain available while matching product-level averages were retrieved from the lookup table.

The merge operation matched 5,050 of 5,050 rows in the main table, confirming that every transaction had a corresponding product-level average available from the lookup table.

This step was important because it allowed the estimation process to use information derived from the existing records rather than introducing an arbitrary value across the entire dataset.

# Estimating the Missing Shipping Costs

After merging the product-level average unit shipping cost into the main dataset, I created an estimated Shipping Cost using:
```Estimated Shipping Cost = Quantity × Average Unit Shipping Cost for Product
```
![Estimating Shipping Cost](images/estimating-shipping-cost.png)
The purpose of this calculation was not to replace the original Shipping Cost values. It was specifically designed to estimate values only where the original Shipping Cost was missing.

I therefore created a final conditional field that preserved existing Shipping Cost values and used the estimated value only when the original field contained a null value.

Conceptually, the logic was:
```If Shipping Cost is null
    → use Estimated Shipping Cost
Otherwise
    → retain the original Shipping Cost
```
![Final Shipping Cost](images/final-shipping-cost.png)
This resulted in a Final Shipping Cost field that combined the valid original values with the estimates required for the previously missing records.

This approach allowed me to preserve the original source information wherever it existed while providing a transparent and consistent method for addressing the missing values.

# Why I Did Not Use a Simple Overall Average

A simple overall average would have been easier to apply, but it would have ignored differences between products and potentially introduced unnecessary distortion into the logistics and profitability analysis.

I also did not remove the 152 affected records because doing so would have reduced the completeness of the dataset and could have affected subsequent analysis.

The product-based approach was therefore chosen because it was supported by an identifiable business dimension in the dataset and was more specific than applying one average value across all transactions.

The approach is based on the assumption that shipments of the same product generally have comparable transportation and handling characteristics. This does not mean that the estimated values perfectly represent the actual operational costs. The dataset does not contain enough logistics information to guarantee that. However, the method provides a transparent, consistent, and business-justifiable approach using information already available in the dataset.

# Recalculating Net Profit

Once the Shipping Cost issue had been addressed, I revisited Net Profit because the value depends directly on several cost components.

I recalculated Net Profit using:
```Net Profit = Net Revenue - (Shipping Cost + Production Cost + Insurance Cost + Taxes)
```
![Re-Calculated Net Profit](images/recalculated-net-profit.png)
This ensured that the profitability analysis reflected the final Shipping Cost values after the missing-value treatment.

The recalculation was important because an incomplete Shipping Cost field could otherwise flow into Net Profit and produce misleading profitability results.

# Recalculating Profit Margin

I also identified inconsistencies in the Profit Margin values and therefore recalculated the metric rather than relying on the original values.

The calculation used was:
```text
Profit Margin (%) = Net Profit ÷ Net Revenue
```
![Re-Calculated Profit Margin](images/recalculated-profit-margin.png)
This created a consistent profitability measure that could be aggregated and used in the final analytical framework.

# Removing Duplicate Records

As part of the final data-quality checks, I also investigated duplicate records and removed duplicates where identified.

This step was completed toward the end of the transformation workflow so that the final dataset used for analysis would contain unique transaction records.

The Applied Steps pane records this stage as Removed Duplicates, followed by a final data-type adjustment.

# Organizing the Power Query Workflow

During the transformation process, I noticed that changing data types after multiple individual transformations created several redundant **Changed Type** steps in the Applied Steps pane.

Rather than leaving these intermediate steps throughout the workflow, I removed the unnecessary type-conversion steps and applied the required data types after the main cleaning and transformation activities had been completed.

This resulted in a cleaner sequence of Applied Steps that was easier to review and maintain. The final workflow included transformations such as source preparation, text cleaning, value replacement, calculated fields, query merging, shipping-cost estimation, financial recalculation, duplicate removal, and final data-type conversion.

Although the dataset itself is not large enough for this optimization to create a major performance difference, organizing the transformation pipeline this way made the ETL process more readable and maintainable.

# Power Query Transformation Workflow

The final Applied Steps pane reflected the progression of the data preparation process, including:
Source
↓
Reordered Columns
↓
Changed Type with Locale
↓
Changed Type with Locale1
↓
Changed Type with Locale2
↓
Cleaned Text
↓
Trimmed Text
↓
Capitalized Each Word
↓
Replace Value steps
↓
Gross Revenue
↓
Net Revenue
↓
Calculated Shipping Cost fields
↓
Merged Queries
↓
Expanded Average Shipping Cost
↓
Estimated Shipping Cost
↓
Final Shipping Cost
↓
Recalculated Net Profit
↓
Recalculated Profit Margin
↓
Removed Duplicates
↓
Final Data Type Adjustment

The exact transformation sequence evolved during development as new issues were identified and resolved. This was intentional because data preparation is often an iterative process: investigating one issue can reveal information that changes how another issue should be handled.

# Data Validation Philosophy

Throughout the preparation process, I treated data validation as part of the analytical workflow rather than as a final technical check.

Instead of assuming that the source data was correct, I validated important financial calculations, investigated missing values, tested assumptions about Shipping Cost, checked for duplicate records, and documented the reasoning behind the decisions made during transformation.

This approach was particularly important for business-critical fields such as Revenue, Shipping Cost, Net Profit, and Profit Margin because errors in these fields could affect almost every downstream finding.

The goal was not simply to produce a clean-looking dataset. The goal was to produce a dataset that was analytically defensible, transparent, and suitable for business decision-making.

# Key Lessons From Data Preparation

The cleaning process changed the way I viewed the dataset. Initially, some problems appeared to be straightforward data-cleaning tasks, but investigating them from a business perspective often required much more reasoning.

The missing Shipping Cost values were the clearest example. The first question was not simply "How do I fill these blanks?" but rather **"What business factor can reasonably explain the variation in Shipping Cost, and does the available data support that assumption?"**

The investigation showed me the importance of testing assumptions before applying a transformation. It also reinforced the idea that preserving valid records is often preferable to deleting them when a transparent and defensible solution can be developed.

Another important lesson was that the cleaning stage itself became part of the analytical discovery process. Spending time understanding the structure, inconsistencies, relationships, and measurable fields in the dataset gave me a much clearer understanding of what the data could eventually tell me.

# Data Preparation Outcome

After the Power Query transformation process, the dataset was prepared for the next stage of the project: creating the calculated fields required for analysis and defining the analytical framework.

The final preparation process ensured that:

- Missing Customer Names were transparently identified as Unknown.
- Missing Shipping Cost values were investigated and addressed using a product-based estimation method.
- Gross Revenue and Net Revenue were recalculated.
- Net Profit was recalculated using the final cost structure.
- Profit Margin was recalculated consistently.
- Text fields were cleaned and standardized.
- Duplicate records were removed.
- Data types were organized.
- The transformation workflow was structured for maintainability.

With the dataset prepared, the next stage was to create the calculated columns that would support time-based, operational, delivery, and customer-experience analysis.
