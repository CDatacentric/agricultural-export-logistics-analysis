# PivotTable Analysis | Exploratory Investigation

## Overview

After completing the data preparation and defining the initial analytical framework, I moved into exploratory analysis using Excel PivotTables.

This stage was different from simply producing the charts required for the dashboard. The dashboard was designed to communicate the most important business questions clearly, while PivotTables gave me the flexibility to investigate the data from different angles and ask additional questions as patterns appeared.

For me, this became one of the most valuable stages of the project because PivotTables allowed me to keep changing the dimensions, measures, filters, and comparisons until I understood what was happening in the data. Instead of stopping after finding an obvious result, I could continue asking what was behind it and whether another dimension provided a different explanation.

I did not intend to include every observation from this exploration in the final report. The purpose of the exploratory stage was to investigate broadly and then select only the findings that had meaningful business relevance.

---

# From Reporting to Exploration

The initial dashboard framework provided a structured view of Revenue, Net Profit, Profit Margin, Orders, Delivery Delay, and Satisfaction. However, a dashboard alone does not necessarily reveal every relationship within a dataset.

I therefore used PivotTables to investigate performance across different combinations of:

- Product
- Country
- Supplier
- Shipping Method
- Year
- Quarter
- Month
- Revenue
- Net Profit
- Profit Margin
- Shipping Cost
- Processing Time
- Delivery Delay
- Satisfaction Score

The ability to rearrange these dimensions quickly made it possible to test different analytical questions without rebuilding the underlying data.

---

# My PivotTable Exploration Process

My approach to PivotTable analysis was iterative.

I would begin with a straightforward business question, build a PivotTable around it, and then examine the result. If something appeared unusual or particularly important, I would change the structure of the PivotTable and investigate the same result from another perspective.

For example, a high Revenue figure would lead to questions such as:

- Was the Revenue driven by a high number of orders?
- Was it driven by higher order quantities?
- Did the product also generate strong Net Profit?
- Was the Profit Margin equally strong?
- Was the performance consistent across different years or quarters?

This process helped me move from simply identifying **what happened** toward investigating **what might be contributing to what happened**.

That became one of the most important analytical lessons from this project: a PivotTable can be more than a reporting tool. It can become a way of thinking through a dataset.

---

# Overall Business Performance

The first level of exploration was to understand the overall financial position of the business before breaking it down into individual segments.

The analysis showed that the company generated approximately:

- **$1.22B in Revenue**
- **$360.8M in Net Profit**
- Approximately **20% overall Profit Margin**

These figures provided the baseline against which the subsequent product, country, supplier, and time-based analysis could be compared.

The overall result indicated that the business was profitable, but the overall totals alone did not explain how that performance was distributed across the business.

This led to the next level of investigation.

---

# Product Performance

I then explored the performance of individual products using Revenue, Net Profit, and Profit Margin.

One important observation was that high Revenue did not automatically mean that a product was the strongest performer across every financial measure. Product performance needed to be viewed using multiple measures rather than Revenue alone.

For example, the analysis showed that strong Revenue performance could be influenced by **Order Quantity**, meaning that a product could generate substantial Revenue partly because a large volume of units was sold.

This reinforced the importance of comparing Revenue with Net Profit and Profit Margin rather than treating Revenue as the only measure of success.

### Analytical Question

> **Is high Revenue being driven by strong profitability, high order quantity, or both?**

This question helped prevent the analysis from stopping at the first positive-looking number.

---

# Country Performance

Country-level PivotTables were used to compare Revenue and Net Profit across markets.

The analysis showed that market contribution was not evenly distributed. Some countries generated considerably stronger financial contributions than others, making country-level analysis important for understanding where the company's performance was concentrated.

One of the stronger markets identified was the **United Kingdom**, which generated approximately:

- **$136.1M in Revenue**
- **$39.5M in Net Profit**

The country analysis therefore provided more context than the overall company totals by showing where financial performance was being generated.

### Analytical Question

> **Which markets are contributing most strongly to overall Revenue and Net Profit, and where might further investigation be required?**

---

# Supplier Performance

Supplier-level analysis was used to investigate whether financial performance varied across suppliers.

Revenue and Net Profit were compared across suppliers to identify major contributors and differences in financial performance.

The purpose was not simply to rank suppliers but to investigate whether supplier performance could help explain differences observed in the broader business results.

Supplier analysis also provided another dimension through which unusual or strong product and market results could be investigated.

### Analytical Question

> **Which suppliers contribute most to financial performance, and are there meaningful differences between supplier-level Revenue and Profitability?**

---

# 2024 vs. 2025 Performance

The year-level PivotTable analysis became one of the most important parts of the exploration.

Although the overall business remained profitable, the comparison between 2024 and 2025 showed a decline in both Revenue and Net Profit.

This changed the analytical direction because the overall business result initially appeared healthy, but the year-over-year comparison revealed that performance was moving in a less favorable direction.

The next question therefore became:

> **When did the decline occur?**

This led to further quarterly and monthly investigation.

---

# Quarterly Performance

I compared performance across quarters for both 2024 and 2025 to determine whether the year-over-year decline was distributed evenly throughout the year or concentrated in specific periods.

The quarterly analysis showed that the weaker 2025 performance became more noticeable in the later part of the year.

This was important because an annual comparison alone could show that performance declined without showing when the change became significant.

The quarterly investigation therefore provided a more focused starting point for management to investigate the underlying causes of the weaker performance.

### Analytical Question

> **Which quarters contributed most to the change in performance between 2024 and 2025?**

---

# Monthly Performance

The monthly analysis provided another level of detail.

Rather than treating each year as one total, I examined the monthly Revenue and Net Profit pattern to identify periods of unusually strong or weak performance.

One observation that required particular caution was the unusually low performance observed in **December 2025**.

This type of result should not immediately be interpreted as proof of a business problem. Before management acts on an unusually low monthly figure, the underlying transactions and reporting process should be validated to determine whether the result reflects an actual business event or a potential data/reporting issue.

This reinforced another important analytical principle from the project:

> **An unusual number is a reason to investigate, not automatically a reason to conclude.**

---

# Logistics Performance Exploration

I also used PivotTables to investigate logistics performance beyond the high-level dashboard view.

The analysis considered:

- Shipping Method
- Shipping Cost
- Processing Time
- Delivery Delay
- Satisfaction Score
- Supplier
- Warehouse-related information where applicable

The objective was to determine whether operational performance appeared to be consistently stronger or weaker under particular logistics conditions.

The analysis did not support a simple conclusion that one Shipping Method was automatically the best across all measures. Shipping Cost, Processing Time, Delivery Delay, and Customer Satisfaction needed to be considered together.

This was consistent with the earlier investigation performed during data preparation, where Shipping Method was tested as a possible driver of Shipping Cost but did not provide a sufficiently consistent basis for estimating the missing values.

---

# Customer Satisfaction Exploration

Customer satisfaction was investigated alongside logistics and financial performance to determine whether operational performance was reflected in the customer experience.

The overall satisfaction result was slightly above the calculated average reference point, but the analysis still showed that customer satisfaction was not strong enough to ignore.

More importantly, the available dataset provided a satisfaction score but did not contain sufficient detail about **why** customers were satisfied or dissatisfied.

This created an important limitation in the analysis.

The data could help identify where satisfaction was lower, but it could not reliably explain the underlying customer problems.

This led to one of the recommendations developed later in the project: introducing more detailed customer feedback or complaint categories so that future analysis can investigate the causes behind satisfaction scores rather than only measuring the scores themselves.

---

# Further Questions Generated During Exploration

The PivotTable analysis also demonstrated that answering one question often created another.

Examples included:

| Initial Observation | Follow-Up Question |
|---|---|
| High Revenue by Product | Is the result driven by Quantity or stronger pricing? |
| Strong Country Performance | Is the market also generating strong Net Profit? |
| 2025 performance declined | Which quarters contributed most to the decline? |
| Shipping Costs differ | What other variables could explain the difference? |
| Satisfaction is relatively weak | What is causing customer dissatisfaction? |
| Unusual monthly performance | Is this a real business pattern or a data/reporting issue? |

This was one of the most valuable parts of the project because the analysis became increasingly question-driven rather than simply chart-driven.

---

# Selecting the Findings

The exploratory stage produced more observations than could reasonably be included in an executive dashboard or final report.

I therefore separated the findings into two groups:

### Exploratory Observations

These were useful discoveries that helped me understand the dataset or generate additional questions but were not necessarily important enough to communicate to management.

### Key Business Findings

These were the observations that had stronger business relevance, could be supported by the available data, and could lead to a meaningful business implication or recommendation.

Only the second group was carried forward into the final findings and recommendations.

This distinction helped keep the final analysis focused rather than turning the report into a collection of every number discovered during exploration.

---

# Key Analytical Lesson

The biggest lesson from the PivotTable stage was that exploration is not simply about finding the largest number or creating the most attractive chart.

The real value came from repeatedly questioning the result.

A PivotTable could show me that one product generated the most Revenue, but that was only the starting point. I could then compare its Quantity, Net Profit, Profit Margin, customer satisfaction, or performance across years and quarters.

That process helped me develop a stronger analytical habit:

> **Do not stop when you find an answer. Ask what the answer leads you to investigate next.**

For this project, PivotTables became the bridge between the cleaned dataset and the final business findings because they allowed me to investigate the data deeply enough to understand which patterns were worth communicating.

---

# Exploratory Analysis Outcome

The PivotTable exploration provided the evidence needed to refine the initial dashboard story and identify the most important findings for management.

The analysis established that:

- Overall financial performance was strong, but year-over-year performance required attention.
- Product performance varied across Revenue, Quantity, Net Profit, and Profit Margin.
- Country contribution was uneven.
- Supplier performance varied across financial measures.
- Logistics performance could not be evaluated reliably using Shipping Method alone.
- Customer satisfaction required deeper investigation because the available score did not explain the underlying causes.
- Unusual results required validation before being treated as confirmed business problems.

These findings were then carried forward into the **Key Findings and Recommendations** stage of the project.
