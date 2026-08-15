# Dashboard Design | Excel Executive Dashboard

## Overview

After completing the data preparation, calculated columns, and exploratory analysis, I moved into the dashboard design stage. At this point, the objective was no longer to discover what the data contained, but to determine how the most important information should be communicated to a management audience.

I had already identified the main business questions, selected the KPIs and analytical visuals, and used PivotTables to understand the data more deeply. The next challenge was to bring these elements together into a dashboard that was informative without becoming visually crowded.

I therefore approached the dashboard as a communication tool rather than simply a collection of Excel charts. Every major component was positioned with a purpose, and the layout was designed to help a reader move naturally from overall performance to specific areas requiring attention.

---

# From Analytical Framework to Dashboard

The analytical framework established the measures and dimensions that needed to appear in the final solution. However, knowing what needed to be displayed was different from deciding how it should be displayed.

I first considered the amount of information that could realistically fit into one executive dashboard without making the page difficult to read. This required balancing the number of KPI cards, charts, slicers, navigation elements, and supporting information against the available screen space.

The final dashboard was therefore designed around an information hierarchy:

**Overall Performance → Business Drivers → Operational Performance → Detailed Investigation**

This hierarchy helped determine where each element should be placed.

---

# Dashboard Wireframe

Before building the final dashboard, I created a wireframe to establish the layout and positioning of the main components.

![Dashboard Wireframe](../images/Agricultural_Export_Logistics_Analysis WireFrame.png)

The wireframe allowed me to make decisions about the dashboard structure before spending time on formatting, colors, chart styling, and other visual details.

It also helped identify potential spacing problems early. Rather than moving charts around repeatedly after they had already been formatted, I could first determine where the KPI cards, charts, slicers, navigation area, and supporting information would fit.

The wireframe became the bridge between the analytical framework and the finished dashboard.

---

# Dashboard Information Hierarchy

The dashboard was organized into several visual areas, each with a different purpose.

### Navigation Area

The navigation area provides the company identity and access to the main dashboard information, including the company logo and name, profile/support information, and analysis-related navigation.

The purpose was to create a structure that felt closer to an executive reporting interface rather than a collection of independently created Excel visuals.

### KPI Area

The KPI cards were positioned prominently because they provide the fastest way to understand the current business position.

The six KPI cards communicate:

- Total Revenue
- Total Net Profit
- Profit Margin
- Total Orders
- Average Delivery Delay
- Average Satisfaction Score

The KPI cards were intentionally given enough visual separation to allow each measure to be read independently without making the dashboard feel fragmented.

### Analytical Chart Area

The charts occupy the main analytical space because they provide the context behind the KPI results.

The reader can move from the high-level numbers into:

- Product performance
- Country performance
- Monthly performance
- Shipping Cost
- Processing and delivery performance

### Filtering Area

Slicers were positioned so that users could filter the dashboard without competing excessively with the main analytical visuals.

The objective was to make filtering available when needed while allowing the charts and KPI cards to remain the primary focus of the dashboard.

---

# KPI Card Design

The six KPI cards were designed to provide a quick executive summary rather than overwhelming the reader with too many measures.

The selected KPIs cover three broad areas:

### Financial Performance

- Total Revenue
- Total Net Profit
- Profit Margin

### Business Activity

- Total Orders

### Operational and Customer Performance

- Average Delivery Delay
- Average Satisfaction Score

This combination allows a reader to understand not only how much the business is generating, but also whether operational performance and customer experience require attention.

The KPI cards were also designed to remain dynamic. Their values change according to the slicers selected by the user, meaning that the dashboard can move from an overall business view into a filtered view of a particular year, quarter, product, country, supplier, or shipping method.

For this reason, I avoided using static percentage statements such as "20% above target" that would become misleading when the user changed the filters. Instead, the supporting labels were designed to communicate the general meaning of the KPI while allowing the actual value to respond dynamically to the selected data.

---

# Chart Selection

The charts were selected based on the analytical questions established earlier rather than simply selecting visuals because the dataset contained suitable columns.

## Product Performance

The Product Performance visual compares Revenue and Net Profit across products.

The purpose is to allow the reader to identify products that contribute strongly to financial performance and then investigate whether their Revenue performance is supported by corresponding profitability.

## Country Performance

The Country Performance visual compares Revenue and Net Profit across markets.

This allows the dashboard to communicate where the business is generating financial activity and whether the strongest Revenue markets are also strong contributors to Net Profit.

## Monthly Performance

The Monthly Performance visual shows Revenue and Net Profit across the reporting period.

The visual was designed to make changes over time easier to recognize and provides a starting point for investigating specific months, quarters, or years.

## Shipping Cost

The Shipping Cost visual compares the cost associated with the different Shipping Methods.

This provides visibility into logistics expenditure and supports further investigation when combined with the Shipping Method slicer.

## Processing and Delivery Performance

The operational chart compares Average Processing Time and Average Delivery Delay across Shipping Methods.

The purpose is to show that operational performance cannot be evaluated through a single measure. A shipping method may perform differently when cost, processing time, and delivery delay are considered together.

---

# Slicer Design

The dashboard uses slicers to make the analysis interactive.

The main slicers include:

- Year
- Quarter
- Product
- Country
- Shipping Method
- Supplier

The slicers were selected because they represent important dimensions through which management may want to investigate performance.

For example, selecting a specific year and quarter allows the user to investigate a particular reporting period, while combining Product and Country filters can reveal how a particular product is performing within a specific market.

The Year and Quarter slicers were particularly useful because the dataset covers **January–December 2024 and January–December 2025**. Keeping both dimensions available makes it easier during a presentation to move directly to a particular period rather than relying only on a continuous date filter.

---

# Slicer Placement and Space Utilization

One of the design challenges was balancing functionality with the limited space available on a single dashboard page.

Rather than giving every slicer a large independent area, related slicers were grouped together. This reduced unnecessary whitespace and allowed more room for the analytical charts.

The intention was not to make the slicers visually dominant. They are an interaction mechanism rather than the primary content of the dashboard.

For that reason, the slicers were given a lighter visual treatment so that the KPI cards and analytical charts remain the first elements that attract attention.

---

# Color System

The dashboard color system was designed to communicate meaning while maintaining visual consistency.

Green was used primarily to represent positive financial performance such as Revenue and Profit, while red was reserved for negative or unfavorable conditions where appropriate.

The color system was intentionally restrained rather than assigning a different strong color to every chart. Using too many unrelated colors would make the dashboard visually noisy and reduce the ability of color to communicate meaning.

The objective was to create a consistent visual language where the reader could gradually understand what the colors represented without having to interpret a new color system for every chart.

---

# Financial Color Logic

Green was used as the primary positive financial indicator because it communicates favorable financial performance and aligns naturally with Profit and positive business outcomes.

Red was reserved for negative or unfavorable conditions, such as losses or adverse operational indicators where applicable.

This distinction was particularly useful when displaying financial measures because the visual treatment reinforced the difference between positive and negative performance without requiring additional explanation.

---

# Visual Emphasis

Not every element on the dashboard was given the same visual weight.

The dashboard was designed so that:

1. **KPI cards** attract the first level of attention.
2. **Main analytical charts** provide the next level of detail.
3. **Slicers** remain accessible but visually quieter.
4. **Navigation and supporting information** provide structure without competing with the analysis.

This helped prevent the dashboard from becoming visually cluttered even though it contains several analytical components.

---

# Interactive Dashboard Behavior

The dashboard was designed to respond dynamically to slicer selections.

When a user selects a different Year, Quarter, Product, Country, Shipping Method, or Supplier, the KPI values and charts update to reflect the selected context.

This means that the dashboard does not communicate one fixed business result. Instead, it provides a flexible analytical environment where the same visual structure can be used to investigate different segments of the business.

This was also an important reason for keeping the supporting KPI labels general. A label that is accurate for the overall dataset may become inaccurate after a user applies a filter.

The final dashboard therefore focuses on communicating what the current KPI represents rather than making static claims about the value.

---

# Dashboard Design Philosophy

The main design principle was:

> **At a glance, a reader should understand what is happening, where it is happening, and where further investigation may be required.**

The dashboard was therefore designed to move the reader through the analysis without requiring them to understand the underlying PivotTables first.

The KPI cards provide the immediate answer to **what is happening**.

The charts help answer **where it is happening**.

The slicers and supporting analysis allow the user to investigate **why it may be happening or where to look next**.

This structure allowed the final dashboard to function both as an executive reporting tool and as an entry point into deeper analysis.

---

# Dashboard Development

After the wireframe and visual decisions were finalized, I built the dashboard in Excel by connecting the selected PivotTables, charts, KPI calculations, and slicers.

The development process involved repeated formatting and positioning adjustments to make the elements work together within the available space.

I paid particular attention to:

- Consistent spacing
- Alignment
- KPI card hierarchy
- Chart readability
- Slicer visibility
- Text hierarchy
- Color consistency
- Navigation structure
- Overall visual balance

The final dashboard was not simply a reproduction of the wireframe. The wireframe provided the structural foundation, while the actual build required adjustments based on how the components interacted visually.

---

# Final Dashboard

![Executive Dashboard](../images/dashboard-preview.png)

The completed dashboard brings together the analytical framework developed throughout the project into a single interactive reporting environment.

The final design allows management to begin with the overall business position and then use the charts and slicers to investigate specific areas of interest without leaving the dashboard.

---

# Dashboard Design Outcome

The final dashboard successfully connects the analytical work completed during the earlier stages of the project with a practical reporting interface.

The dashboard combines:

- 6 KPI cards
- Financial and operational charts
- Interactive slicers
- Company navigation and identity
- A structured visual hierarchy
- Consistent financial color logic
- Dynamic filtering

The result is an executive dashboard that prioritizes clarity and analytical usefulness while still taking advantage of Excel's interactive capabilities.

The next stage was to use the completed dashboard together with the PivotTable analysis to review the most important findings and determine which observations should be communicated as business insights.
