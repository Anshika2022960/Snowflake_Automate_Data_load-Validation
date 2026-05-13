# Snowflake Automated Data Load & Validation

## Project Overview

This project demonstrates how to automate data loading and validation in Snowflake using a single stored procedure.

The workflow loads CSV files from a Snowflake stage into a temporary staging table, validates the data, and then inserts only clean data into the final target table. If validation fails, the records are not inserted and the failure details are captured in an audit log table.

This project is useful for real-world data engineering scenarios where raw files must be checked before loading into production tables.
## Tools and Technologies Used
- Snowflake
- SQL
- Stored Procedure
- Internal Stage
- COPY INTO
- Temporary Table
- Audit Logging
- CSV File

---


## Project Objective

The objective of this project is to build a simple but production-style Snowflake workflow that can:

Load a CSV file from a Snowflake stage.
Store raw data temporarily before final insertion.
Validate data for missing values.
Validate duplicate customer IDs.
Insert clean data into the target table.
Skip invalid data from final insertion.
Store success and failure details in an audit log table.
Return a final status message after execution.

## Key Learning from This Project.

This project helped me understand how to build a Snowflake-based data validation workflow using SQL and stored procedures.

Key concepts covered:

Snowflake stage
File format
COPY INTO command
Temporary table
Stored procedure
Dynamic SQL
Null validation
Duplicate validation
Conditional data loading
Audit logging
Error handling

## Real-World Use Case

In real-world data pipelines, raw files often come from external systems such as CRM, ERP, applications, or cloud storage. These files may contain missing values, duplicate records, or incorrect data.

Instead of directly loading raw data into production tables, this project uses a temporary staging table and validation logic. This ensures that only clean and trusted data reaches the final table.

## Architecture

```text
Source CSV File
      |
      v
Snowflake Internal Stage
      |
      v
Temporary / Staging Table
      |
      v
Stored Procedure Validation
      |
      |-- Validation Passed --> Target Table
      |
      |-- Validation Failed --> Audit Log Table
      |
      v
Success / Failure Message



