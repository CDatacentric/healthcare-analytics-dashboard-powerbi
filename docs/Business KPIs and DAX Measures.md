# Business KPIs and DAX Measures

## Purpose

The purpose of this stage was to transform the prepared data into meaningful business metrics that support operational monitoring and management decision-making.

Rather than relying on static calculations, DAX measures were developed to produce dynamic results that respond automatically to filters, slicers, and user interactions throughout the dashboard.

To maintain a clean and organized data model, all measures were stored in a dedicated **DAX Measures** table instead of being distributed across the fact and dimension tables.

---

# Overview

The measures developed during this project were grouped according to the business questions they were intended to answer.

The KPIs fall into three categories:

- Financial Performance
- Patient Activity
- Operational Performance

This organization simplified dashboard development while making it easier to maintain and expand the model as new measures were introduced.

---

# Implementation

## Financial Performance

### Total Revenue

**DAX Formula**

```DAX
Total Revenue = SUM(Hospital Data[Revenue])
```

**Returns**

Calculates the total revenue generated during the selected reporting period.

**Business Purpose**

Provides management with an overall view of hospital revenue and serves as one of the primary financial KPIs displayed on the dashboard.

---

### Average Revenue per Patient

**DAX Formula**

```DAX
Average Revenue per Patient =
DIVIDE([Total Revenue],[Total Patients])
```

**Returns**

Calculates the average revenue generated per unique patient.

**Business Purpose**

Helps evaluate the average financial contribution of each patient during the reporting period.

---

### Total Insurance Coverage

**DAX Formula**

```DAX
Total Insurance Coverage =
SUM(Hospital Data[Insurance Coverage])
```

**Returns**

Calculates the total amount covered by insurance providers.

**Business Purpose**

Measures the financial contribution made by insurance companies.

---

### Revenue Collection Percentage

**Returns**

Calculates the percentage of total revenue successfully collected.

**Business Purpose**

Helps evaluate revenue collection efficiency.

---

### Outstanding Treatment Cost

**Returns**

Calculates the remaining treatment costs yet to be recovered.

**Business Purpose**

Supports monitoring of outstanding balances.

---

# Patient Activity

### Total Patients

**DAX Formula**

```DAX
Total Patients =
DISTINCTCOUNT(Hospital Data[Patient ID])
```

**Returns**

Counts the total number of unique patients.

**Business Purpose**

Measures the number of individual patients served during the reporting period.

---

### Total Hospital Visits

**DAX Formula**

```DAX
Total Visits =
COUNTROWS(Hospital Data)
```

**Returns**

Counts every recorded hospital visit.

**Business Purpose**

Measures total hospital activity and supports repeat visit analysis.

---

### Repeat Visit Rate

**Returns**

Calculates the percentage of patients who visited the hospital more than once.

**Business Purpose**

Helps evaluate patient retention and recurring service utilization.

---

# Operational Performance

### Average Waiting Time

**DAX Formula**

```DAX
Average Waiting Time =
AVERAGE(Hospital Data[Waiting Time])
```

**Returns**

Calculates the average patient waiting time.

**Business Purpose**

Monitors operational efficiency and patient flow.

---

### Average Length of Stay

**DAX Formula**

```DAX
Average Length of Stay =
AVERAGE(Hospital Data[Length of Stay])
```

**Returns**

Calculates the average duration of patient stays.

**Business Purpose**

Measures hospital resource utilization and operational efficiency.

---

### Average Patient Satisfaction

**DAX Formula**

```DAX
Average Satisfaction =
AVERAGE(Hospital Data[Satisfaction Score])
```

**Returns**

Calculates the average patient satisfaction score.

**Business Purpose**

Monitors patient experience across the reporting period.

---

# Dashboard Integration

The measures developed during this stage became the analytical foundation of the executive dashboard.

Each KPI was connected to report visuals, cards, charts, and slicers, allowing management to interact with the data and monitor hospital performance across different dimensions such as diagnosis, location, insurance provider, and reporting period.

---

# Outcome

By developing dynamic DAX measures, the project transformed transactional hospital data into business-focused KPIs capable of supporting interactive reporting and informed decision-making.

Organizing every measure within a dedicated **DAX Measures** table also improved the readability and maintainability of the data model, making future enhancements easier to implement.
