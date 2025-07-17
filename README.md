# WideWorldImporters ETL Project

This project implements an ETL solution for WideWorldImporters using SSIS, creating a staging database and a data warehouse (DWH) with transformed data.

## Project Overview

The solution consists of two main components:
1. **WideWorldImporters_Staging**: SSIS package to load Excel files into a staging database
2. **WideWorldImporters_DWH**: SSIS package to transform and load data from staging to the data warehouse

## Key Features

- Daily scheduled data loads
- Data transformations including:
  - Table joins (Orders and OrderLines)
  - Data conversions
  - Calculated columns
  - Data filtering
- Proper dimensional modeling with fact and dimension tables
- View creation for analytics
- Primary key and index implementation

## Implementation Details

### Staging Database
- Created packages for each source Excel file
- Scheduled to run daily

### Data Warehouse
- Implemented fact and dimension tables (prefixed with Fact_ and Dim_)
- Created calculated columns:
  - PostalPostalCode_4 in Customers table
  - [Other calculated columns you added]
- Applied data filters:
  - Excluded LastEditedBy = 20
  - Excluded PostalAddressLine2 values starting with 'Z'
  - Removed specific columns from various tables
- Created vw_Supplier_count view

## Repository Contents

- `screenshots/`: Evidence of implementation
- `scripts/`: SQL scripts including view definition
- `solutions/`: SSIS solution files
- `docs/`: Additional documentation

## Setup Instructions

1. Clone this repository
2. Open SSIS solutions in SQL Server Data Tools
3. Deploy packages to your SQL Server Integration Services catalog
4. Schedule jobs in SQL Server Agent as specified in the project requirements
