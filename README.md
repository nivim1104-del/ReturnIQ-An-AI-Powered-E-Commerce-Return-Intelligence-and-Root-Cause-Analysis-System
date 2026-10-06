# ReturnIQ – AI-Powered E-Commerce Return Intelligence and Root-Cause Analysis System

## Project Overview

**ReturnIQ** is a Python-based data analysis project focused on the **E-Commerce** industry. The project analyses e-commerce order, product, seller, delivery, payment, review, and complaint data to understand patterns related to product returns and customer complaints.

The analysis is intended to help identify potential problem areas across products, sellers, order fulfilment, delivery, and customer experience.

---

## Industry

**E-Commerce**

---

## Problem Statement

E-commerce businesses receive many product returns and customer complaints related to wrong products, defective or damaged products, missing products, delivery delays, non-delivery, and refund or replacement issues. These problems can originate from different stages of the e-commerce process, including the product, seller, order fulfilment, delivery, or customer claim.

Traditional return-management systems mainly process return, refund, or replacement requests, but they lack the intelligence to identify why problems occur or which factors contribute to repeated complaints and returns.

Therefore, there is a need for an intelligent system that can analyse order, product, seller, delivery, payment, review, and complaint data to identify patterns associated with e-commerce returns and complaints.

ReturnIQ is proposed as an AI-powered system that analyses e-commerce data to identify potential root causes of returns and complaints, detect recurring patterns, and provide useful insights through an administrative dashboard. The system is designed to support better investigation of return requests and help businesses understand product-, seller-, and logistics-related issues.

---

## Proposed Solution / Analysis

The project uses Python-based data analysis to examine:

- Order status and order fulfilment patterns
- Delivery performance and delivery delays
- Customer review scores
- Product-category performance
- Seller performance
- Product price and freight characteristics
- Seller-to-customer distance and logistics
- Transit speed
- Single-item and multi-item orders
- Relationships between numerical features
- E-commerce complaint categories from the NCH dataset
- Return-related signals in the Online Retail II dataset

The analysis is performed before the machine-learning stage so that the available data, patterns, and potential modelling features can be understood.

---

## Datasets

### 1. Olist Brazilian E-Commerce Public Dataset

Used for analysis of:

- Customers
- Geolocation
- Orders
- Order items
- Payments
- Reviews
- Products
- Sellers
- Product-category translation

### 2. Online Retail II

Used to examine retail transaction data and identify transaction-level signals such as negative quantities that may represent returns or cancellations. Negative quantities were retained as signals and were not automatically treated as confirmed returns.

### 3. National Consumer Helpline (NCH) E-Commerce Complaint Dataset

Used for aggregate complaint-category analysis.

The dataset contains complaint categories such as:

- Delivery of Wrong Product
- Delivery of Defective / Damage Product
- Paid amount not refunded
- Non-Delivery of Product
- Delay in Delivery of Product
- Replacement / Refund not provided - As per policy
- Product / Product Accessories Missing
- Other complaint categories

The NCH dataset is aggregate category-level complaint data and is not treated as individual complaint records.

---

## Dataset Sources

- Olist Brazilian E-Commerce Public Dataset
- Online Retail II
- National Consumer Helpline (NCH) E-Commerce Complaint Dataset

---

## Tools & Technologies

- Python
- Jupyter Notebook
- NumPy
- Pandas
- Matplotlib

---

## Project Workflow

**Industry Selection → Problem Identification → Dataset Collection → Data Cleaning → Data Transformation → Data Analysis → Data Visualization → Insights → Recommendations**

---

## Project Structure

The current project is organized into separate data-processing and visualization stages.

```text
ReturnIQ/
│
├── README.md
│
├── Data/
│   ├── Cleaned_Dataset/
│   └── Raw_Dataset/
│
├── Notebook/
│   └── data_analysis_EDA.ipynb
│
├── Python/
│   ├── 01_Data_Loading.ipynb
│   ├── 02_Data_Cleaning.ipynb
│   ├── 03_Exploratory_Analysis.ipynb
│   └── 04_Data_Visualization.ipynb
│
├── Visualizations/
│   ├── category_analysis.png
│   ├── correlation_analysis.png
│   ├── distribution_analysis.png
│   ├── trend_analysis.png
│   └── Visualization.ipynb
│
└── .gitignore
```

---

## Data Analysis Performed

The following analysis was actually performed on the project data:

### Dataset Overview

The integrated Olist analytical dataset contains **112,650 rows and 71 columns** at the order-item level.

The analysis included examination of:

- Dataset dimensions
- Data types
- Missing values
- Feature availability
- Integrated order-item data

### Order Status Analysis

Order-status distribution was analysed across delivered, shipped, cancelled, invoiced, processing, unavailable, and approved orders.

### Delivery Performance Analysis

The project analysed:

- Delivery days
- Estimated delivery days
- Delivery delay days
- Delayed versus non-delayed delivered records

### Delivery Delay Analysis

Delivered records were examined according to whether they were:

- Delivered early
- Delivered on the estimated date
- Delivered late

Actual delayed deliveries were also analysed by their delay duration.

### Review Score Analysis

Customer review scores were analysed to understand the distribution of customer ratings.

### Review Score vs Delivery Delay

Review groups were compared with observed delivery-delay rates to examine the relationship between delivery performance and customer review experience.

### Product Category Analysis

Product categories were analysed by:

- Order-item volume
- Average review score
- Average delivery time
- Observed delay percentage

### Seller Performance Analysis

Seller-level delivery and review patterns were examined, with attention to volume when comparing sellers.

### Price and Freight Analysis

The project analysed:

- Product price
- Freight value
- Freight-to-price ratio
- High freight-ratio items

### Distance and Logistics Analysis

Seller-to-customer distance was calculated using geographic coordinates and analysed using distance categories.

### Transit Speed Analysis

Transit time was grouped into project-defined categories:

- Fast
- Normal
- Slow
- Unknown

These groups were compared with delivery and review-related measures.

### Multi-Item and Order Value Analysis

Single-item and multi-item orders were compared using:

- Item count
- Order value
- Delivery time
- Review score
- Observed delay rate

### Correlation Analysis

Numerical feature relationships were examined, including relationships involving:

- Delivery delay
- Delivery days
- Transit days
- Review score
- Shipping preparation time
- Seller-customer distance
- Price
- Freight
- Order value

Correlations were treated as observed relationships and not as proof of causation.

### NCH Complaint Analysis

NCH complaint categories were analysed to identify complaint areas relevant to ReturnIQ, including wrong products, defective/damaged products, non-delivery, delivery delays, refund/replacement issues, and missing products.

---

## Data Visualization

The project contains separate visualization work for:

- Distribution Analysis
- Trend Analysis
- Category Analysis
- Correlation Analysis

The generated visualization files are stored in the `Visualizations/` folder.

---

## Key Insights

The following insights were obtained from the actual analysis:

- The integrated Olist dataset is heavily dominated by delivered orders.
- Among delivered records, most deliveries occurred before the estimated delivery date.
- **7,265 delivered order-item records were observed as delayed**, representing approximately **6.59% of delivered records**.
- The observed average delay among delayed deliveries was approximately **10.49 days**.
- Lower review-score groups showed higher observed delivery-delay percentages than higher review-score groups.
- Product categories showed differences in review scores, delivery times, and observed delay percentages.
- Longer seller-to-customer distances were associated with longer observed delivery times and higher observed delay percentages.
- The Slow transit group showed a substantially higher observed delay percentage than the Fast and Normal groups.
- Multi-item orders had higher average order values than single-item orders, while their review and delivery patterns differed.
- A subset of lower-priced items had relatively high freight-to-price ratios.
- NCH complaint data showed substantial complaint volumes related to wrong products, defective/damaged products, refund issues, non-delivery, delivery delays, and missing products.
- Correlation analysis identified relationships between several delivery, review, and logistics variables; these relationships were not interpreted as causal effects.

---

## Recommendations

Based on the actual findings, the following practical recommendations are proposed:

1. **Monitor delivery delays** and investigate orders with unusually long delivery or transit times.

2. **Investigate high-delay product categories** to identify recurring fulfilment or logistics issues.

3. **Review seller performance using sufficient order volume** rather than relying only on small-volume seller percentages.

4. **Investigate long-distance shipments** because longer seller-to-customer distances were associated with longer delivery times and higher observed delay rates.

5. **Monitor slow-transit shipments** as they showed a substantially higher observed delay percentage.

6. **Investigate categories and sellers associated with lower review scores** together with their delivery and fulfilment patterns.

7. **Use complaint-category information** to support root-cause investigation of wrong-product, defective/damaged-product, non-delivery, delay, refund/replacement, and missing-product issues.

8. **Use the EDA findings to guide the later machine-learning stage**, while avoiding assumptions about target labels that are not directly supported by the available data.

---

## Visualization Screenshots

The following visualization files are currently present in the project:

### Category Analysis

![Category Analysis](Visualizations/category_analysis.png)

### Correlation Analysis

![Correlation Analysis](Visualizations/correlation_analysis.png)

### Distribution Analysis

![Distribution Analysis](Visualizations/distribution_analysis.png)

### Trend Analysis

![Trend Analysis](Visualizations/trend_analysis.png)

---

## Project Notebooks

### Data Loading

`01_Data_Loading.ipynb`

Responsible for loading and initially inspecting the project datasets.

### Data Cleaning

`02_Data_Cleaning.ipynb`

Responsible for data cleaning, integration, preprocessing, and feature preparation.

### Exploratory Analysis

`03_Exploratory_Analysis.ipynb`

Responsible for statistical and analytical exploration of the prepared dataset.

### Data Visualization

`04_Data_Visualization.ipynb`

Responsible for the visualization stage, with visualization outputs maintained separately in the `Visualizations/` folder.

---

## Author

**Name:** Nivetha M  
**Student ID:** AF05313369  
**Organization:** Anudip Foundation  
**Course:** AIML  
**Batch Code:** ANP-D7444
