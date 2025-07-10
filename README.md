# Transaction Data Analysis Pipeline

A comprehensive PySpark-based data pipeline for analyzing transaction data across multiple channels (web, mobile, in-store) using Azure Databricks and Delta Lake.

# Project Overview

This project implements a complete data processing pipeline that:
- Loads transaction and product data from Azure Data Lake Storage Gen2
- Performs comprehensive data quality checks and validation
- Conducts business intelligence analysis across multiple dimensions
- Stores results in optimized Delta tables for efficient querying
- Monitors data quality with advanced outlier detection

# Data Sources

### Synthetic Data Generation
The project uses **synthetic data generated with Python's Faker library** to simulate realistic e-commerce transaction scenarios:

- **`transactions.csv`**: Generated transaction records with customer IDs, product IDs, order dates, quantities, prices, channels, and marketing campaigns
- **`products.csv`**: Generated product catalog with product names, categories, prices, and descriptions

### Data Schema

**Transactions Table:**
- `transaction_id`: Unique transaction identifier
- `customer_id`: Customer identifier
- `product_id`: Product identifier
- `channel`: Sales channel (web, mobile, in-store)
- `order_date`: Transaction date
- `quantity`: Items purchased
- `unit_price`: Price per unit
- `campaign_applied`: Marketing campaign identifier

**Products Table:**
- `product_id`: Product identifier
- `product_name`: Product name
- `category`: Product category
- `price`: Product price
- `description`: Product description

## 🔧 Features Implemented

### 1. Data Loading & Integration
- **ADLS Gen2 Integration**: Secure connection using SAS tokens
- **Multi-source Loading**: Combines transaction and product data
- **Schema Validation**: Ensures data integrity with expected column validation

### 2. Data Quality Management
- **Missing Value Detection**: Comprehensive null value analysis
- **Outlier Detection**: 
  - Z-score method (3 standard deviations)
- **Schema Validation**: Automated column presence verification

### 3. Data Analysis
- **Customer Analysis**: Average order value per customer
- **Product Performance**: Top 10 most popular products
- **Category Analysis**: Sales performance by product category
- **Marketing Impact**: Campaign effectiveness measurement
- **Channel Analysis**: Multi-channel sales comparison (web, mobile, in-store)

### 4. Data Storage & Optimization
- **Delta Lake Tables**: ACID-compliant data storage
- **Storage Optimization**: Automatic table optimization using `OPTIMIZE` command
- **Version Control**: Table history tracking with `DESCRIBE HISTORY`
- **Managed Tables**: Simplified table management in Databricks



**Note**: This project uses synthetic data generated with Python's Faker library to simulate e-commerce scenarios.
