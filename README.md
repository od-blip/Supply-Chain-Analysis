# Supply Chain Dataset Analysis

## Table of Contents
1. [Project Overview](#project-overview)  
2. [Data Sources](#data-sources)  
3. [Tools Used](#tools-used)  
4. [Data Cleaning and Preparation](#data-cleaning-and-preparation)  
5. [Analysis](#analysis)  
   - [Sales Performance](#sales-performance)  
   - [Demand](#demand)  
   - [Shipment](#shipment)  
   - [Customer Segmentation](#customer-segmentation)  
   - [Product/Department Sales](#productdepartment-sales)  
   - [Cumulative Product Sales](#cumulative-product-sales)  
   - [Correlation](#correlation)  
   - [Revenue by Category](#revenue-by-category)  
6. [Recommendations](#recommendations)  
7. [Limitations Encountered](#limitations-encountered)  
8. [References](#references)  

---

## Project Overview
The goal of this project was to analyze a supply chain dataset to gain insights into sales, demand, shipment, customer behavior, and product performance. This analysis helps businesses make data-driven decisions to optimize operations and enhance profitability.  

---

## Data Sources
**CSV files from Kaggle.**  

---

## Tools Used
- **Python**: For data cleaning, preparation, and preprocessing.  
- **Power BI**: For further cleaning, building relationships, modeling, and creating visualizations.  
- **ChatGPT**: For assistance with insights, documentation, and report formatting.  

---

## Data Cleaning and Preparation
- **Python**: 
  - Preprocessing involved renaming columns, removing duplicates, and eliminating empty rows.  
  - The dataset was split into 9 tables for easier analysis:
    - `fact_table`
    - `dim_order`
    - `dim_order_item`
    - `dim_customer`
    - `dim_product`
    - `dim_category`
    - `dim_department`
    - `dim_order_date`
    - `dim_shipping_date`  
  - Each table was exported as a CSV file for further processing.  

- **Power BI**:  
  - Additional cleaning was performed, such as renaming columns with snake_case to a more readable format.  
  - Relationships were modeled using a **snowflake schema**, linking fact and dimension tables.  
  - A new table called `Color Theme` was created to enable **dark/night mode switching**.  

---

## Analysis

### Sales Performance
- **Profit by Category**:  
  - Fishing: **$1.71M**  
  - Cleats: **$1.08M**  
  - Camping and Hiking: **$1.01M**  
  - **Total Profit**: **$33.05M**  

- **Total Sales**: **$36.78M**  
- **Top Customers**:  
  - Smith Mary contributed **82.75%** of total sales.  
- **Sales Trends**:  
  - Steady throughout the year, but peak sales occur in **October**.  

### Demand
- **Sales by Year**:  
  - 2015: **$12.3M**  
  - 2016: **$12.3M**  
  - 2017: **$11.8M**  

- **Sales by Market (Continent)**:  
  - Europe: **$10.8M**  
  - LATAM: **$10.3M**  
  - Pacific Asia: **$8.3M**  
  - USCA: **$5M**  
  - Africa: **$2.3M**  

### Shipment
- **Total Shipping Cost**: **$1.65M**  
  - Highest shipping costs occur in **January** each year.  
- **Average Shipping Cost**: **$9.2**  
- **Delivery Risk**:  
  - **54.83%** of shipments were at risk of late delivery.  

### Customer Segmentation
- **Retention Rates**:  
  - Consumers: **0.593**  
  - Corporate: **0.590**  
  - Home Office: **0.590**  

- **Revenue by Segment**:  
  - Consumers: **$19.1M**  
  - Corporate: **$11.2M**  
  - Home Office: **$6.5M**  

- **Payment Types**:  
  - Debit: **38.3%**  
  - Transfer: **27.7%**  

### Product/Department Sales
- **January Insights**:  
  - Discounts: **$350K**  
  - Sales: **$3.5M**  
  - Profit: **$3.01M**  

- **Sales Volume by Department**:  
  - Fan: **106K units**  
  - Golf: **99K units**  
  - Apparel: **98K units**  
  - Footwear: **43K units**  
  - Outdoor: **23K units**  

- **Profit Margin by Department**:  
  - Golf: **16.65%**  

- **Sales Volume by Market**:  
  - LATAM: **30%**  
  - Europe: **27%**  

### Cumulative Product Sales
- **Top 3 Products in Europe**:  
  - Lawn Mowers: **18.82% (258K)**  
  - Summer Dresses: **29.06% (140K)**  
  - Smartwatches: **37% (117K)**  

- **Overall Top Product**:  
  - Adidas F10 Messi TRX FG Soccer Cleats  
  - **Cumulative Sales**: **56K units**  
  - **Unit Price**: **$60**  

### Correlation
- **Discount Rate vs. Sum of Order Item Quantity**:  
  - Cleats: **73,734 units**  
  - Women’s Apparel: **62,956 units**  

### Revenue by Category
- **Fishing**:  
  - Sales: **$6.929M**  
  - Profit: **$6.2M**  

- **Cleats**:  
  - Sales: **$4.432M**  
  - Profit: **$3.98M**  

- **Camping and Hiking**:  
  - Sales: **$4.12M**  
  - Profit: **$3.7M**  

- **Least Performing Categories**: Toys and CDs.  

---

## Recommendations
1. Focus on increasing sales in **low-performing categories** like Toys and CDs.  
2. Improve **logistics and shipment planning** to reduce late delivery risks.  
3. Continue offering **discounts in January** to boost sales and customer retention.  
4. Develop targeted marketing strategies for **high-performing categories** (e.g., Fishing and Cleats).  

---

## Limitations Encountered
- **Data Quality Issues**: Missing values in some columns required imputation or exclusion.  
- **Ambiguous Column Names**: Some column names lacked clarity and needed renaming for analysis.  
- **Negative Profit Values**: Affected analysis for certain products.  
- **Time Constraints**: Limited time to explore more advanced analytics like machine learning forecasting.  

---

## References
- **Kaggle**: [Supply Chain Dataset](https://www.kaggle.com/)  
