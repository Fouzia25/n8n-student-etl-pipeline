# n8n Student ETL Pipeline

## Project Overview

This project demonstrates an ETL (Extract, Transform, Load) pipeline built using n8n.

The workflow reads a raw student enrollment CSV file, cleans the student data, removes duplicate records, filters students based on fee payment status, and exports the final cleaned data as a CSV file.

## ETL Workflow

The workflow contains the following steps:

1. Manual Trigger
2. Read File from Disk
3. Extract CSV data
4. Clean and transform data using JavaScript
5. Remove duplicate students using Student_ID
6. Filter students where Fee_Paid is TRUE
7. Convert the data to CSV
8. Write the cleaned CSV file to the output folder

## Input

The input file is:

`input/students_raw.csv`

The raw data contains 50 student records with inconsistent formatting and missing or invalid values.

## Data Cleaning

The JavaScript transformation performs data cleaning such as:

- Trimming whitespace
- Standardizing student names
- Standardizing course values
- Cleaning email values
- Handling missing phone numbers
- Handling invalid values
- Standardizing fee payment values
- Standardizing city values
- Formatting enrollment dates

## Duplicate Removal

Duplicate records are identified using:

`Student_ID`

The n8n Remove Duplicates node is used to remove repeated student records.

## Filtering

The workflow keeps students where:

`Fee_Paid = TRUE`

From the workflow execution:

- Input records: 50
- Records after duplicate check: 50
- Records retained after filtering: 33
- Records filtered out: 17
- Final output records: 33

## Output

The final cleaned file is:

`output/cleaned_students.csv`

## Tools Used

- n8n
- JavaScript
- CSV
- Git
- GitHub
- Visual Studio Code

## Workflow

```text
Manual Trigger
      ↓
Read File
      ↓
Extract CSV
      ↓
JavaScript Cleaning
      ↓
Remove Duplicates
      ↓
Filter Fee_Paid = TRUE
      ↓
Convert to CSV
      ↓
Write File to Disk