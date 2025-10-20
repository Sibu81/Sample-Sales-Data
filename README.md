# Sample-Sales-Data
About Dataset Sample Sales Data, Order Info, Sales, Customer, Shipping, etc., Used for Segmentation, Customer Analytics, Clustering and More. Inspired for retail analytics. This was originally used for Pentaho DI Kettle, But I found the set could be useful for Sales Simulation training.

# Sales Data ETL & Analysis

## Overview
This project demonstrates a complete **ETL pipeline** using Python and MySQL.  
It loads a raw sales dataset, cleans and transforms the data, and stores it in a MySQL database.  
Finally, it performs SQL queries to extract meaningful insights.

---

## Tech Stack
- Python (pandas, sqlalchemy)
- MySQL
- Jupyter Notebook / VS Code (for development)

---

## Dataset
- CSV file: `sales_data_sample.csv`
- Columns: 25 (including Order info, Customer info, Product info, Sales, etc.)

---

## Features
1. **Data Cleaning**
   - Handle missing values (`STATE`, `TERRITORY`, `ADDRESSLINE2`, `POSTALCODE`)
   - Convert `ORDERDATE` to datetime
   - Remove duplicates
2. **Derived Columns**
   - `TotalSales = QUANTITYORDERED * PRICEEACH`
   - `Year` and `Month` from `ORDERDATE`
3. **ETL**
   - Push cleaned data directly into MySQL table `sales_data`
4. **SQL Queries**
   - Top 10 products by sales
   - Revenue by country
   - Monthly sales trend

---

## Usage
1. Update MySQL credentials in `sales_etl_mysql.py`:
   ```python
   engine = create_engine("mysql+pymysql://username:password@localhost:3306/sales_db")
