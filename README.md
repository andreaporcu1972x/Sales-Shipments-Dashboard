# Sales & Shipments Overview Dashboard

## Project Overview
This project implements a Business Intelligence solution covering the **Order → Shipment → Delivery** lifecycle, starting from raw CSV data and ending with interactive reporting in **Power BI**.

The solution includes the typical phases of a BI environment:
- data ingestion
- data transformation and consolidation
- dimensional modeling
- analytical reporting through dashboards and KPIs

The project is structured as a realistic integration scenario between sales and logistics domains.

---

## Solution Architecture

CSV Files  
↓  
Apache Hop (ETL & Workflow)  
↓  
RAW Layer (SQL Server)  
↓  
STAGING Layer  
↓  
DATA WAREHOUSE (Star Schema)  
↓  
Power BI Dashboard

---

## ETL & Orchestration

**Tool:** Apache Hop

### Implemented features
- Dedicated pipelines for:
  - Customers
  - Orders
  - Order Lines
  - Shipments
  - Products
- Orchestration workflow that:
  - coordinates RAW data ingestion
  - runs audit checks
  - triggers STAGING and DWH loading processes
- Load metadata management:
  - Load Date (`load_dt`)
  - Run ID
  - Ingestion Timestamp
  - Source File
- Support for data reloads and reprocessing

---

## Data Warehouse

### Model
**Star Schema**

### Dimensions
- `DW.DIM_DATE`
- `DW.DIM_CUSTOMER`
- `DW.DIM_PRODUCT`
- `DW.DIM_CARRIER`

### Fact tables
- `DW.FACT_SALES`
- `DW.FACT_SHIPPING`

Facts are modeled independently and linked through conformed dimensions, following dimensional modeling best practices.

---

## Dashboard & KPIs (Power BI)

### Main dashboard
**Sales & Shipments Overview Dashboard**

### Available KPIs
- Total Sales
- Total Orders
- On-Time Delivery Rate (%)
- Outstanding Orders
- Shipments by Carrier
- Delivery Performance Trend (Year-Month)

### Operational tables
Shipment Delivery Status:
- Shipment ID
- Order ID
- Carrier
- Shipment Date
- Expected Delivery Date
- Delivered Date
- Delivery Days
- On-Time Flag
- Delivery Status

Conditional formatting is used to highlight delays and operational issues.

---

## Analytical goals
- Monitor sales performance
- Analyze shipment and delivery efficiency
- Identify delayed or pending orders
- Support operational and control analysis

---

## Technologies
- Apache Hop
- SQL Server
- Power BI
- GitHub
