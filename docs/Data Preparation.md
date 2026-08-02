# Data Preparation

## Purpose

The purpose of this stage was to prepare the hospital datasets for analysis by combining six monthly CSV files into a single, reliable dataset suitable for data modeling and reporting. Every transformation was performed in Power Query to create a repeatable workflow that can be refreshed whenever new data becomes available.

---

# Overview

The source data consisted of six monthly CSV files containing hospital operational information. Before any analysis could begin, the data required standardization to ensure consistency across all files.

Power BI's Folder connector was used to import the monthly files into a single query. This approach eliminated the need to manually import each file individually and allowed future monthly datasets to be incorporated through a simple refresh, provided the files maintained the same structure.

For the Folder connector to combine files successfully, two conditions had to be satisfied:

- Every file contained the same column names.
- Every file contained the same number of columns.

Maintaining a consistent file structure ensured that future data could be appended automatically without requiring additional transformation work.

---

# Implementation

The following preparation tasks were completed in Power Query before building the data model.

## Data Import

- Imported six monthly CSV files using the Folder connector.
- Combined the files into a single dataset.
- Verified that every file followed the same structure before transformation.

---

## Data Cleaning

Several cleaning operations were performed to improve data quality and consistency.

These included:

- Validating and correcting data types.
- Standardizing text values.
- Removing unnecessary spaces using the **TRIM** function.
- Removing non-printable characters using the **CLEAN** function.
- Correcting regional date formats using **Change Type with Locale**.
- Renaming queries where necessary to improve readability.
- Removing unnecessary columns.
- Creating calculated columns required for later analysis.

---

## Data Transformation

Additional transformations were performed to prepare the dataset for reporting.

These included:

- Appending monthly datasets into a single table.
- Merging lookup tables using matching key columns.
- Extracting date components where required.
- Creating conditional columns.
- Selecting only the columns required for analysis.
- Organizing queries to support a clean analytical model.

---

## Data Validation

After the transformation process was complete, the dataset was reviewed to confirm its readiness for modeling.

Validation included:

- Checking for incorrect data types.
- Reviewing null values.
- Verifying lookup relationships.
- Confirming calculated columns.
- Reviewing column profiling information.
- Ensuring the combined dataset matched the expected structure.

---

## Performance Optimization

During development, I noticed that Power Query created multiple **Changed Type** steps as transformations were applied.

Rather than leaving several separate type conversion steps in the Applied Steps pane, I removed the intermediate **Changed Type** steps and applied a single final type conversion after completing the transformations.

This simplified the query, reduced unnecessary transformation steps, and helped maintain a cleaner and more efficient Power Query workflow.

---

# Outcome

By completing the preparation stage in Power Query, the project produced a clean, standardized, and repeatable dataset ready for data modeling.

Because every transformation was recorded as part of the query, future monthly files can be added to the source folder and incorporated into the dashboard through a refresh without repeating the entire cleaning process manually.

This prepared the project for the next stage: building the data model and defining relationships between the fact and dimension tables.
