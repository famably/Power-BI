# Snowflake + Power BI

## ✨ Goal

`1. Load data from MongoDB to Snowflake.`

`2. Import Snowflake data to Power BI.`

`3. Build and visualize a dashboard.`

## 🔗  Step-by-Step Guide

### 1. Snowflake Setup

✅ Create an account at https://www.snowflake.com/

✅ In the Snowflake dashboard:
- Navigate to Admin > Warehouses → click “+ Warehouse” to create a compute warehouse.
- Navigate to Data > Databases → click “+ Database” to create a logical database.

### 2. MongoDB Preparation

✅ Obtain your MongoDB connection URL
- (e.g. mongodb+srv://user:pass@cluster.mongodb.net/db_name)

✅ Whitelist Fivetran’s IP addresses in your MongoDB Atlas cluster under Network Access.

### 3. Fivetran Integration

Use Fivetran to load MongoDB → Snowflake.

✅ Go to https://fivetran.com and create an account.

✅ Set up:
- Source: MongoDB
- Destination: Snowflake
- Sync Frequency: Choose how often data should be updated

✅ Schema mapping:
- Automatically handled by Fivetran
- Supports evolving MongoDB schema

🔍 Note: Fivetran loads documents into Snowflake with nested structures placed inside a single DATA column (variant type).

### 4. Power BI + Snowflake

✅ Install Power BI Desktop (from powerbi.microsoft.com)

✅ Install the Snowflake ODBC driver (from Snowflake documentation)

✅ In Power BI:
- Connect to Snowflake via Get Data > Snowflake
- Enter account URL, warehouse, and database details

✅ After importing:
- Parse the DATA column to extract fields into separate columns (e.g., via Power Query)
- Transform/clean unnecessary data
- Establish relationships between logical tables if needed
- Build dashboards to visualize key business metrics