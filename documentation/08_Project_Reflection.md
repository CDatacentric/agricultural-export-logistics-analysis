# Project Reflection

## Overview

This project was more than an exercise in building an Excel dashboard. It gave me an opportunity to document how I approach a data analysis problem from the point where I receive a dataset and business problem through to data preparation, exploratory analysis, dashboard development, and communicating findings.

One of the main things I wanted to demonstrate was that data analysis does not begin with charts. It begins with understanding the problem, understanding the data, and gradually building enough context to know what questions are worth asking.

---

# Starting With the Business Problem

When I receive a dataset, my first step is not to immediately open the data and start creating PivotTables or charts. I first study the project overview and business problem, usually reading through it more than once so that I understand what the analysis is expected to accomplish.

For this project, the initial business problem was centered around the belief that valuable financial and operational opportunities were hidden within the agricultural export data.

Keeping that problem in mind while reviewing the dataset helped me look at the available fields differently. Instead of seeing 30 columns as separate pieces of information, I started thinking about how they could connect to the business questions.

This initial understanding became the foundation for the rest of the project.

---

# Understanding the Dataset Before Cleaning

After studying the business problem, I moved into the dataset itself.

I wanted to understand what story the data could potentially tell before deciding exactly how I would analyze it. This involved reviewing the fields, understanding which information was descriptive and which information could be measured or aggregated, and thinking about how the different fields could interact.

This was also where I began separating the information conceptually into areas such as customer, supplier, product, and country information on one side and financial, logistics, operational, and customer-feedback measures on the other.

This helped me understand how the dataset could eventually be transformed into an analytical model rather than simply treating it as a spreadsheet of transactions.

---

# Data Cleaning Became Part of the Analysis

One of the biggest lessons from this project was that data cleaning and analysis are not completely separate stages.

While working in Power Query, I encountered several issues that required analytical thinking before I could decide how to fix them.

The most significant example was the **152 missing Shipping Cost values**.

At first, the problem appeared straightforward: determine how to fill the missing values. However, once I considered the importance of Shipping Cost to profitability and logistics analysis, I realized that simply applying an overall average would not be a sufficiently thoughtful solution.

I investigated Shipping Method and compared Air, Road, and Sea shipments before concluding that Shipping Method did not provide a consistent enough basis for estimating the missing values. That investigation eventually led me to use Product Name and calculate an average Unit Shipping Cost by product.

This experience reinforced something important for me:

> **A data-cleaning decision can require the same level of reasoning as an analytical decision.**

The question was not simply *how to fill a blank*. It was *what information already available in the dataset could provide a reasonable explanation for the missing value?*

---

# Validation Changed My Approach to Source Data

Another important lesson was the need to validate business-critical figures instead of assuming that the source dataset was automatically correct.

I independently recalculated Gross Revenue, Net Revenue, Net Profit, and Profit Margin.

This made me more conscious of the fact that a dataset can contain values that look reasonable but still require verification before they are used to support business decisions.

Recalculating these measures also gave me more confidence in the financial analysis because I understood how the numbers were being produced rather than simply accepting them as supplied.

---

# Calculated Columns and Analytical Thinking

Creating calculated columns was another stage where I began thinking more deliberately about the questions I wanted the data to answer.

Fields such as Order Month & Year, Quarterly, Delivery Time, Order Processing Time, Satisfaction Score, and Average Delivery Delay were not created simply to add more columns to the dataset.

They were created because I had identified analytical questions that required those fields.

For example, the original Order Date could tell me when a transaction occurred, but creating Year, Month, Month & Year, and Quarter fields made it possible to investigate how financial performance changed over time.

Similarly, the original order, shipping, and delivery dates became much more useful once they could be transformed into measures of processing and delivery performance.

This helped me understand that calculated columns should have a purpose. The goal is not to create as many derived fields as possible, but to create the fields that make meaningful analysis possible.

---

# PivotTables Brought Out the Analytical Side of the Project

The PivotTable stage was probably the part of the project where I felt the strongest connection with analytical thinking.

Whenever I used a PivotTable, I could keep changing the dimensions and measures, asking another question, and then digging further into the result.

A result that initially looked straightforward could lead to another question.

For example:

**Which product has the highest Revenue?**

could become:

**Is that Revenue driven by Quantity?**

Then:

**Does the same product also have strong Net Profit?**

Then:

**How does its Profit Margin compare with other products?**

Then:

**Does the performance remain consistent across 2024 and 2025?**

This process made the analysis feel less like filling a report and more like investigating a business problem.

One of the biggest lessons I took from this stage was:

> **Do not stop when you find an answer. Ask what that answer makes you investigate next.**

That mindset helped me discover patterns that would not necessarily have been visible from the initial dashboard requirements.

---

# Learning to Separate Findings From Observations

The exploratory analysis produced many observations.

However, I learned that not every observation deserves to become a finding in the final report.

Some results were useful for understanding the dataset but did not have enough business significance to communicate to management. Others raised interesting questions but could not be explained confidently with the available data.

I therefore became more selective about what I considered a final finding.

A strong finding should ideally be:

- Relevant to the business problem.
- Supported by the data.
- Important enough to influence a decision or investigation.
- Clear enough to communicate.
- Capable of leading to a reasonable recommendation.

This helped prevent the final report from becoming a long list of numbers.

---

# Learning to Distinguish Evidence From Assumption

The project also taught me to be more careful about the difference between what the data demonstrates and what I think might be causing a result.

The December 2025 performance was a good example.

The data showed an unusually weak result, but the dataset did not provide enough information to confidently explain why it happened.

Rather than assigning a cause without evidence, I treated it as an investigation point.

The same principle applied to Shipping Method and Shipping Cost. I initially considered Shipping Method as a possible explanation, but the data did not support using it as a sufficiently reliable estimator.

This reinforced the importance of being comfortable saying:

> **The data shows this happened, but the available information is not sufficient to explain why.**

That is a more responsible analytical conclusion than creating a confident explanation that the data cannot support.

---

# Designing the Dashboard After Understanding the Data

Another lesson from this project was the importance of delaying final visualization decisions until the data and analysis had developed sufficiently.

The initial business problem provided the direction, but the cleaning process, calculated columns, and PivotTable exploration gave me a much better understanding of what the dashboard actually needed to communicate.

Only then did I finalize the KPI cards, charts, and slicers.

This made the dashboard more purposeful because the visuals were connected to actual analytical questions rather than selected simply because they were available in Excel.

---

# Wireframing Before Building

Creating the wireframe before completing the final dashboard helped me think about the dashboard as a user interface rather than a collection of charts.

I had already decided how many KPI cards, charts, and slicers were required, so the wireframe allowed me to test how they could fit together while maintaining a clear hierarchy.

It also forced me to think about what deserved the most visual attention.

The final dashboard therefore followed a simple hierarchy:

**What is happening? → Where is it happening? → Where should I investigate further?**

The KPI cards answer the first question, the charts provide the second level of context, and the slicers allow deeper investigation.

---

# Balancing Information and Visual Clutter

One of the practical challenges was working within the limited space of a single executive dashboard.

There was always a temptation to include another chart, another slicer, or another KPI because the dataset contained many potentially useful fields.

However, adding more information does not automatically make a dashboard more useful.

I had to make decisions about what deserved space and what could remain available through PivotTable exploration.

This helped me understand that dashboard design is partly an exercise in prioritization. A good dashboard should not attempt to display everything discovered during analysis.

It should display what the audience needs first and provide a path to investigate further.

---

# What I Would Improve in a Future Version

If I were developing a future version of this project, I would improve the analysis by collecting additional business variables that were not available in the original dataset.

For logistics analysis, variables such as shipment weight, distance, freight contract, fuel surcharge, and other transportation costs would make it possible to investigate Shipping Cost more accurately.

For customer analysis, structured feedback categories, complaint types, and customer comments would make it possible to investigate the reasons behind Satisfaction Score rather than simply reporting the score.

I would also extend the reporting period where possible so that longer-term trends could be distinguished from short-term fluctuations.

These improvements would not replace the current analysis. They would provide additional information that could help answer the questions that the current dataset cannot fully explain.

---

# Skills Developed

This project strengthened several practical skills across the Excel analytics workflow.

### Excel

- Executive dashboard development
- PivotTable analysis
- Interactive slicers
- Chart design
- KPI development
- Data-driven formatting
- Dashboard layout and visual hierarchy

### Power Query

- Data cleaning
- Text transformation
- Missing-value handling
- Query duplication
- Grouping
- Merge Queries
- Conditional transformations
- Calculated columns
- ETL workflow organization

### Analytical Thinking

- Translating business problems into analytical questions
- Testing assumptions against data
- Investigating unexpected results
- Comparing multiple business dimensions
- Distinguishing observations from findings
- Connecting findings to recommendations
- Recognizing when the available data is insufficient to establish causation

### Business Communication

- Presenting complex analysis in a concise format
- Designing an executive-level dashboard
- Selecting only the most important findings
- Communicating limitations and assumptions
- Connecting analytical results to practical business questions

---

# Final Reflection

The most valuable outcome of this project was not simply completing an Excel dashboard. It was developing a clearer understanding of how I want to approach data analysis.

I learned that the strongest analysis does not necessarily come from having the most charts or the most complicated formulas. It comes from understanding the business problem, becoming familiar with the data, questioning assumptions, investigating unexpected results, and being selective about what deserves to become a business finding.

The project also showed me that the analytical process is rarely completely linear. A discovery during data cleaning can influence the analysis. A PivotTable result can lead to a new question. A dashboard requirement can expose a limitation in the available data. The important thing is to remain willing to revisit an earlier assumption when the evidence suggests a different direction.

For me, this project represents a step beyond learning individual Excel features. It demonstrates how I can combine those skills into a complete analytical workflow and document the reasoning behind the decisions I make.

The final dashboard is therefore not the end of the analysis. It is the result of the analytical thinking, investigation, and decision-making that happened behind it.
