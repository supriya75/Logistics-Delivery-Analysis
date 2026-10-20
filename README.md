# Logistics Delivery Performance Analysis

An end-to-end data analytics project investigating late deliveries in a hypothetical GCC e-commerce / 3PL operation, using SQL, Python, Excel, and Power BI.

> **Note on data:** The records come from a public benchmark dataset (DataCo), not from a UAE company. The Dubai / Jebel Ali setting is a business scenario used to frame the analysis.

## Key Findings

*To be added after the analysis is validated against the source data.*

## 1. Project Overview

| | |
|---|---|
| **Project type** | End-to-end data analytics |
| **Domain** | E-commerce logistics and supply chain |
| **Business context** | Hypothetical regional operation centered on Dubai and Jebel Ali |
| **Tools** | Excel, SQL, Python (pandas), Power BI |

The goal is to understand delivery delays, identify operational patterns, quantify the sales value associated with late deliveries, and recommend practical improvements.

## 2. Business Problem

You are a data analyst supporting a regional logistics operation. Management is receiving customer complaints about delayed deliveries and wants answers to three questions:

1. Why are deliveries arriving later than promised?
2. How much sales value is associated with late deliveries?
3. What operational changes could improve delivery reliability?

**Objective:** Analyze delivery performance to identify patterns associated with late deliveries, quantify their scale, and develop evidence-based recommendations.

## 3. Key Performance Indicators

**Eligible delivery (provisional):** a delivered order, excluding cancelled orders. The exact rule will be confirmed during data profiling and documented here.

| KPI | Definition | Purpose |
|---|---|---|
| On-Time Delivery Rate | Eligible deliveries meeting the promised date ÷ all eligible deliveries | Measures reliability |
| Late Delivery Rate | Eligible deliveries arriving after the promised date ÷ all eligible deliveries | Measures frequency of lateness |
| Average Delay (days) | Average delay among late deliveries only | Measures severity |
| Sales Value Associated with Late Deliveries | Sales value of orders classified as late | Quantifies commercial exposure |
| Late Rate by Shipping Mode / Region / Category | Late deliveries ÷ eligible deliveries within each segment | Locates the problem |
| Monthly Late Delivery Rate | Late deliveries ÷ eligible deliveries per month | Shows trends over time |

**Measurement principles**

- Use rates as well as counts, so segments of different sizes can be compared fairly.
- Define the unit of analysis (grain) first, to avoid double-counting orders with multiple items.
- Separate actual delivery outcomes from predicted risk flags such as `Late_delivery_risk`.
- Report cancelled orders separately.
- Document assumptions, limitations, and any proxy measures.

## 4. Business Questions

1. What proportion of eligible deliveries arrive late?
2. How many days beyond the promise are late deliveries?
3. How does performance vary by shipping mode?
4. Which regions and product categories have the highest late rates?
5. Do specific shipping mode and region combinations perform worse?
6. Does performance change over time?
7. What sales value is associated with late deliveries?
8. Which operational changes could plausibly improve reliability?
9. How could management estimate the benefit of reducing late deliveries?

## 5. Analysis Roadmap

| Phase | Focus |
|---|---|
| **1. Business understanding and Excel quick look** | Define the problem and KPIs, inspect columns, find the grain, check delivery status values, cross-check late flags |
| **2. Data profiling and cleaning (Python)** | Missing values, duplicates, date validity, inconsistent columns; build a documented analytical dataset |
| **3. SQL analysis** | Table design, KPI queries, segment comparisons, validation against Python results |
| **4. Exploratory analysis (Python)** | Delay patterns, relationships between operations and outcomes, outliers; descriptive findings kept separate from causal claims |
| **5. Power BI dashboard** | Data model, DAX measures, interactive management views |
| **6. Recommendations and impact** | Actionable recommendations, scenario estimates with stated assumptions, limitations |

## 6. Data Source and Limitations

**Dataset:** [DataCo Smart Supply Chain for Big Data Analysis](https://data.mendeley.com/datasets/8gx2fvg2k6/5) (order, product, customer, shipping, and delivery information)

**UAE / GCC context:** Dubai and Jebel Ali are used as the scenario setting. Any additional UAE reference data (for example, Dubai Pulse customs datasets) or simulated assumptions will be identified separately with their sources.

**Limitations**

- The dataset may not include transport costs, fuel, warehouse capacity, or other factors that explain delays.
- Sales value associated with late deliveries does not mean revenue was lost.
- Observed relationships do not prove causation.
- Estimated impacts are scenarios based on stated assumptions, not measured results.

## 7. Repository Structure

```
logistics-delivery-analysis/
├── data/           raw and cleaned data (or download links)
├── excel/          quick_look.xlsx
├── notebooks/      Python cleaning, EDA, (optional) modeling
├── sql/            table creation and analysis queries
├── dashboards/     Power BI file, screenshots
└── README.md
```

## 8. How to Reproduce

1. Download the dataset from the source link above and place it in `data/raw/`.
2. Run the notebooks in `notebooks/` in numbered order.
3. Load the cleaned data into your SQL database and run the queries in `sql/`.
4. Open the Power BI file in `dashboards/`.

*(Update these steps with exact commands and versions as the project develops.)*

## 9. Project Status

- [x] Business problem and KPIs defined
- [ ] Excel quick look
- [ ] Data profiling and cleaning
- [ ] SQL analysis
- [ ] Python EDA
- [ ] Power BI dashboard
- [ ] Recommendations and impact assessment
- [ ] Final write-up and LinkedIn post

Findings and recommendations will be added after they have been validated against the source data.
