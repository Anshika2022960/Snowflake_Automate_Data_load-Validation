# Snowflake Automated Data Load & Validation

## Project Overview

This project demonstrates how to automate data loading and validation in Snowflake using a single stored procedure.

The workflow loads CSV files from a Snowflake stage into a temporary staging table, validates the data, and then inserts only clean data into the final target table. If validation fails, the records are not inserted and the failure details are captured in an audit log table.

This project is useful for real-world data engineering scenarios where raw files must be checked before loading into production tables.

---

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

## Tools and Technologies Used
- Snowflake
- SQL
- Stored Procedure
- Internal Stage
- COPY INTO
- Temporary Table
- Audit Logging
- CSV File
