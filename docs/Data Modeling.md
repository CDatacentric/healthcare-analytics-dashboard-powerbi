# Data Modeling

## Purpose

The purpose of this stage was to organize the prepared data into a structured model that supports accurate calculations, efficient filtering, and scalable reporting. A well-designed data model improves report performance, simplifies DAX calculations, and ensures that filters behave consistently across the dashboard.

---

# Overview

After completing the data preparation stage, the cleaned dataset was organized into a Star Schema by separating transactional data from supporting lookup tables. This approach reduced redundancy, simplified relationships, and provided a structure that supports efficient analysis.

The completed model consists of one fact table containing the hospital transactions and multiple dimension tables that provide descriptive information such as diagnoses, doctors, insurance providers, hospital locations, and dates.

---

# Implementation

## Fact Table

The hospital transaction table was used as the central fact table because it records every hospital visit and contains the measurable values used throughout the analysis.

Examples of measures derived from the fact table include:

- Revenue
- Insurance Coverage
- Patient Payments
- Outstanding Treatment Cost
- Length of Stay
- Waiting Time

Keeping transactional records in a single fact table allowed all business calculations to be developed from one consistent source.

---

## Dimension Tables

Supporting lookup tables were created to store descriptive information used for filtering and categorizing the fact table.

Dimension tables included information such as:

- Diagnosis
- Doctor
- Insurance Provider
- Hospital Location
- Date

Separating these attributes from the fact table reduced duplication while making the model easier to maintain and extend.

---

## Relationships

Relationships were manually created between the fact table and each dimension table using their corresponding key columns.

Each relationship was validated to ensure that filters propagated correctly from the dimension tables to the fact table. This ensured that slicers and report filters behaved consistently across all dashboard visualizations.

---

## Date Table

A dedicated Date Table was created to support time-based analysis.

The table was generated using DAX and included additional columns such as:

- Year
- Month Number
- Month Name
- Quarter
- Weekday Number
- Weekday Name

Creating a separate Date Table ensured that all time intelligence calculations were based on a complete calendar rather than relying directly on transaction dates. Month names and weekday names were also sorted by their corresponding numeric values to preserve chronological order within report visuals.

---

## DAX Measures Table

Before creating business KPIs, a dedicated table named **DAX Measures** was created to store every measure developed during the project.

Keeping measures in a separate table prevented calculations from being scattered across the fact and dimension tables, making the model easier to navigate, maintain, and expand as additional measures were introduced.

Although this organization does not affect calculation performance, it significantly improves the readability of the data model.

---

## Model Validation

After the relationships were created, the completed model was reviewed to verify:

- Active relationships.
- Correct relationship direction.
- Matching key columns.
- Proper filter propagation.
- Correct table organization.
- Readable naming conventions.

This validation ensured that the model was ready for DAX development and dashboard construction.

---

# Outcome

The completed Star Schema provided a clean and scalable analytical model capable of supporting dynamic calculations and interactive reporting.

With the relationships established, the Date Table configured, and the DAX Measures table organized, the project was ready for KPI development and dashboard creation.
