# Exploratory Analysis

## Purpose

The purpose of this stage was to investigate business questions beyond the predefined dashboard requirements. While the dashboard summarized key performance indicators, exploratory analysis provided an opportunity to examine relationships within the data, validate assumptions, and identify additional findings that could support better decision-making.

---

# Overview

After completing the executive dashboard, I revisited the dataset to explore questions that were not directly answered by the report visuals. Rather than creating additional KPIs, this stage focused on understanding why certain patterns appeared in the data and determining whether those observations were supported by evidence.

Some investigations confirmed initial expectations, while others showed that the available data did not support the original assumption.

---

# Implementation

## Revenue Performance by Diagnosis

The first investigation examined how revenue was distributed across diagnosis categories.

The analysis showed that the **Other** diagnosis category generated the highest revenue during the reporting period. Among the predefined diagnosis categories, Fracture, Hypertension, Back Pain, and Menstrual Disorder contributed the largest share of revenue.

This investigation highlighted differences in service demand across diagnosis groups and provided additional context for the financial KPIs displayed on the dashboard.

---

## Revenue Performance by Hospital Location

Revenue was also analyzed across hospital locations.

Sheffield generated the highest revenue during the reporting period, followed by Liverpool and Manchester, while Leeds recorded the lowest revenue.

To better understand these differences, I compared total revenue with hospital bed capacity. Since every location reported the same total bed capacity, capacity alone could not explain the variation in revenue, suggesting that other factors such as patient volume or diagnosis mix were more likely contributors.

---

## Insurance Provider Analysis

Insurance provider performance was reviewed to understand how different insurers contributed to hospital revenue.

The analysis showed that Aviva generated the highest insurance revenue while also covering the largest number of patients. This indicated that patient volume was a stronger contributor to revenue than the insurance provider itself.

---

## Patient Satisfaction Analysis

An additional investigation examined whether patient waiting time or payment method influenced patient satisfaction.

The analysis showed that satisfaction scores remained relatively consistent across the different payment methods despite small differences in average waiting time.

Based on the available data, neither payment method nor waiting time appeared to have a significant impact on patient satisfaction during the reporting period.

---

## Average Length of Stay Investigation

One of the most important findings involved the Average Length of Stay KPI.

The initial dashboard reported an overall average of 1.55 days. Further investigation revealed that the calculation included both inpatient and outpatient visits.

When the calculation was limited to inpatient visits only, the Average Length of Stay increased to 6.27 days.

This investigation demonstrated the importance of understanding how KPIs are constructed before interpreting their results.

---

# Outcome

The exploratory analysis provided additional context beyond the executive dashboard and strengthened the final recommendations presented in the project.

More importantly, it reinforced the importance of validating assumptions before drawing conclusions. Some investigations confirmed expected patterns, while others helped eliminate possible explanations, resulting in a more accurate interpretation of the available data.
