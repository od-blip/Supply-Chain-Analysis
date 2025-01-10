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
8. [Code Snippet](#code-snippet)
9. [References](#references)  

---

## Project Overview
The goal of this project was to analyze a supply chain dataset to gain insights into sales, demand, shipment, customer behavior, and product performance. This analysis helps businesses make data-driven decisions to optimize operations and enhance profitability.  
![image](https://github.com/user-attachments/assets/c5b8d224-8384-4dc0-a0e3-56811a06711c)

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
 
- **Snowflake Model with color theme table**: ![image](https://github.com/user-attachments/assets/203b9940-293f-44c0-8991-b5906ecf7448)

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

## Code Snippet
 
 ``` Python
-- #Libs
import pandas as pd
import numpy as np
import scipy as sp

-- #Dataset import
Supply_chain = pd.read_csv(r'C:\Users\HomePC\Desktop\InspectedDataCoSupplyChainDataset.csv', encoding = 'latin1')

-- #Checking Na
print(supply_chain.isna().any().any())

-- #Checking empty cells
# Check which columns have empty cells
print(supply_chain.isna().any())
# Count empty cells for each column
print(supply_chain.isna().sum())

# Total number of empty cells in the entire DataFrame
print(supply_chain.isna().sum().sum())

-- #filling non numeric empty cells
# Fill non-numeric empty values with "Unknown"
supply_chain.fillna(value={col: "Unknown" for col in supply_chain.select_dtypes(include='object').columns}, inplace=True)

# Converting order_date and shipping_date columns to datetime
supply_chain['order_date'] = pd.to_datetime(supply_chain['order date (DateOrders)'], errors='coerce')
supply_chain['shipping_date'] = pd.to_datetime(supply_chain['shipping date (DateOrders)'], errors='coerce')

# Extracting Year, Month, Day Name for both dates
for date_col in ['order_date', 'shipping_date']:
    supply_chain[f'{date_col}_year'] = supply_chain[date_col].dt.year
    supply_chain[f'{date_col}_month'] = supply_chain[date_col].dt.month
    supply_chain[f'{date_col}_day_name'] = supply_chain[date_col].dt.day_name()

# Calculate Order Item Subtotal
supply_chain['order_item_subtotal'] = supply_chain['Order Item Quantity'] * supply_chain['Order Item Product Price']

# Calculate Profit (Placeholder logic: Sales - Total Discounts)
supply_chain['profit'] = supply_chain['Sales'] - supply_chain['Order Item Discount']

# Shipping Cost: Placeholder (adjust if there’s specific logic)
supply_chain['shipping_cost'] = supply_chain['Order Item Total'] * 0.05  # Assuming 5% of the total is the shipping cost.

# View the updated DataFrame
supply_chain.head()

supply_chain

-- #Splitting tables
# fact table
fact_table = supply_chain[[
    'Order Id', 'Order Item Id', 'Customer Id', 'Product Card Id', 'Department Id', 'Order Item Quantity', 'Order Item Product Price', 
    'order_item_subtotal', 'Order Item Discount', 'Order Item Total', 
    'Sales', 'profit', 'shipping_cost', 'order_date', 'shipping_date', 'Payment_Type', 'Days for shipment (scheduled)', 'Days for shipping (real)', 'Late_delivery_risk (boolean)'
]]

# customer table
dim_customer = supply_chain[[
    'Customer Id', 'Customer Fname', 'Customer Lname', 
    'Customer Segment','Customer Street', 'Customer Zipcode', 'Customer City', 'Customer State', 'Customer Country'
]].drop_duplicates()

# product table
dim_product = supply_chain[[
    'Product Card Id', 'Product Name', 'Product Price', 
    'Product Status', 'Product Category Id', 'Department Id'
]].drop_duplicates()

# category table
dim_category = supply_chain[[
    'Category Id', 'Category Name'
]].drop_duplicates()

#department table
dim_department = supply_chain[[
    'Department Id', 'Department Name'
]].drop_duplicates()

#order table 
dim_order = supply_chain[[
    'Order Id', 'Order Customer Id', 'Order Status', 
    'Order City', 'Order Country', 'Market (continent)'
]].drop_duplicates()

#order item table
dim_order_item = supply_chain[[
    'Order Item Id', 'Order Item Product Price', 'Order Item Profit Ratio', 'Order Item Quantity', 
    'order_item_subtotal', 'Order Item Discount', 'Order Item Total'
]].drop_duplicates()

# shipping date table
dim_shipping_date = supply_chain[[
    'shipping_date', 'shipping_date_year', 'shipping_date_month', 'shipping_date_day_name'
]].drop_duplicates()

# order date table
dim_order_date = supply_chain[[
    'order_date', 'order_date_year', 'order_date_month', 'order_date_day_name'
]].drop_duplicates()

# Check if linked ID columns contain the same or overlapping values
linked_columns = [
    ("Order Customer Id", "Customer Id"),
    ("Order Item Cardprod Id", "Product Card Id"),
    ("Product Category Id", "Category Id"),
]

# Verifying overlaps in values for each pair
overlap_results = {
    f"{col1} vs {col2}": supply_chain[col1].isin(supply_chain[col2]).all()
    for col1, col2 in linked_columns
}

# Print results
print(overlap_results)

-- #Exportin CSVs
# Save tables as separate CSV files
fact_table.to_csv("fact_table.csv", index=False)
dim_customer.to_csv("dim_customer.csv", index=False)
dim_product.to_csv("dim_product.csv", index=False)
dim_category.to_csv("dim_category.csv", index=False)
dim_department.to_csv("dim_department.csv", index=False)
dim_order.to_csv("dim_order.csv", index=False)
dim_order_item.to_csv("dim_order_item.csv", index=False)
dim_shipping_date.to_csv("dim_shipping_date.csv", index=False)
dim_order_date.to_csv("dim_order_date.csv", index=False)

```
--- 

## Dax Functions:
``` DAX
Total Profit = SUM(fact_table[Profit])
```
```
Total Sales = SUM(fact_table[Sales])
```
```
Total Sales Volume = SUM(fact_table[Order Item Quantity])
```
```
Average Shipping Cost = AVERAGEX(fact_table, fact_table[shipping cost])
```
```
Average Shipping Time = AVERAGE(fact_table[Shipment day (real)])
```
```
YoY % = 
DIVIDE(
    [_SelectedYearSales] - [_LastYearSales],
    [_LastYearSales],
    0
)
```

## References
- **Kaggle**: [Supply Chain Dataset](https://www.kaggle.com/datasets/shashwatwork/dataco-smart-supply-chain-for-big-data-analysis?select=DataCoSupplyChainDataset.csv)  
