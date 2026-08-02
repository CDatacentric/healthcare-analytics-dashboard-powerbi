# Data Dictionary

## Purpose

The Data Dictionary provides a reference for every table and column used throughout the Healthcare Analytics Dashboard project. It describes the purpose of each field, its role within the data model, and how the information supports analysis and reporting.

---

# Dataset Overview

The project follows a **Star Schema** consisting of one central fact table, multiple supporting dimension tables, and two model-supporting tables created specifically for reporting.

## Fact Table

- Hospital Visits

## Dimension Tables

- Patients
- Doctors
- Departments
- Procedures

## Supporting Tables

- Date Table
- DAX Measures

---

# Fact Table

## Hospital Visits

The Hospital Visits table is the central fact table of the model. Each row represents a single patient visit and contains the measurable values used throughout the dashboard.

| Column | Description |
|---------|-------------|
| VisitID | Unique identifier for each hospital visit. |
| VisitDate | Date the patient visited the hospital. |
| PatientID | References the patient associated with the visit. |
| DoctorID | References the attending doctor. |
| DepartmentID | References the department where treatment was provided. |
| ProcedureID | References the medical procedure performed during the visit. |
| AdmissionType | Indicates the patient's admission category (for example, Emergency or Elective). |
| VisitType | Indicates whether the visit was Inpatient or Outpatient. |
| DiagnosisCategory | Diagnosis assigned during the visit. |
| LengthOfStayDays | Number of days the patient remained admitted. |
| WaitTimeMinutes | Patient waiting time before treatment. |
| TreatmentCost | Total treatment cost before insurance and patient payment. |
| InsuranceCoverage | Amount covered by the patient's insurance provider. |
| AmountPaid | Amount paid directly by the patient. |
| PatientSatisfactionScore | Patient satisfaction rating recorded after treatment. |
| Outcome | Final treatment outcome for the visit. |
| PaymentStatus | Indicates whether payment has been completed or remains outstanding. |
| Revenue | Calculated column created during data preparation representing the total revenue generated from each hospital visit. |

---

# Dimension Table

## Patients

The Patients table stores demographic information used to analyze patient characteristics and support report filtering.

| Column | Description |
|---------|-------------|
| PatientID | Unique identifier for each patient. |
| FirstName | Patient's first name. |
| LastName | Patient's last name. |
| DateOfBirth | Patient's date of birth. |
| Gender | Patient gender. |
| City | Patient's city of residence. |
| BloodGroup | Patient blood group. |
| InsuranceProvider | Patient's insurance provider. |

---

# Dimension Table

## Doctors

The Doctors table stores information about healthcare professionals responsible for patient treatment.

| Column | Description |
|---------|-------------|
| DoctorID | Unique identifier for each doctor. |
| DoctorName | Doctor's full name. |
| DepartmentID | References the department where the doctor works. |
| Specialty | Doctor's area of medical specialization. |
| Grade | Professional grade or designation. |
| YearsExperience | Total years of professional experience. |

---

# Dimension Table

## Departments

The Departments table stores information about each hospital department.

| Column | Description |
|---------|-------------|
| DepartmentID | Unique identifier for each department. |
| DepartmentName | Name of the hospital department. |
| Floor | Hospital floor where the department is located. |
| BedCapacity | Number of beds allocated to the department. |
| StaffCount | Total staff assigned to the department. |

---

# Dimension Table

## Procedures

The Procedures table stores information about the medical procedures performed within the hospital.

| Column | Description |
|---------|-------------|
| ProcedureID | Unique identifier for each procedure. |
| ProcedureName | Name of the medical procedure. |
| DepartmentID | References the department responsible for the procedure. |
| StandardCost | Standard cost assigned to the procedure. |

---

# Supporting Table

## Date Table

The Date Table was created using DAX to support time-based analysis and reporting. Rather than relying directly on the VisitDate field from the fact table, the Date Table provides a complete calendar that enables consistent filtering and chronological reporting.

| Column | Description |
|---------|-------------|
| Date | Calendar date used throughout the model. |
| Year | Calendar year. |
| Month Number | Numeric representation of the month (1–12). |
| Month Name | Full month name used in report visuals. |
| Quarter | Calendar quarter (Q1–Q4). |
| Weekday Number | Numeric representation of the day of the week. |
| Weekday Name | Full weekday name used in report visuals. |

---

# Supporting Table

## DAX Measures

The DAX Measures table was created to store every business measure developed throughout the project. Rather than distributing measures across the fact and dimension tables, a dedicated table was used to keep the data model organized, improve readability, and simplify future maintenance.

The following measures were developed for this project.

| Measure | Business Purpose |
|----------|------------------|
| Total Revenue | Calculates the total revenue generated from all hospital visits. |
| Total Patients | Counts the total number of unique patients treated during the reporting period. |
| Total Visits | Counts the total number of hospital visits recorded in the dataset. |
| Total Treatment Cost | Calculates the total cost of all treatments provided. |
| Total Insurance Coverage | Calculates the total amount covered by insurance providers. |
| Total Amount Paid | Calculates the total amount paid directly by patients. |
| Average Revenue Per Patient | Calculates the average revenue generated per unique patient. |
| Average Wait Time | Calculates the average patient waiting time before treatment. |
| Average Length of Stay | Calculates the average duration of inpatient stays. |
| Average Patient Satisfaction Score | Calculates the average patient satisfaction rating. |
| Insurance Coverage % | Calculates the percentage of treatment costs covered by insurance providers. |
| Patient Payment % | Calculates the percentage of treatment costs paid directly by patients. |
| Revenue Collection % | Measures the percentage of treatment revenue successfully collected. |
| Outstanding Treatment Cost | Calculates the remaining treatment cost that has not yet been recovered. |
| Repeat Visit Rate | Calculates the percentage of patients with more than one hospital visit during the reporting period. |
| Today's Date | Returns the current date used for report display and refresh reference. |

These measures form the analytical foundation of the executive dashboard and automatically respond to report filters, slicers, and user interactions.

---

# Relationships

The Power BI data model uses the following primary relationships between the fact table and supporting tables.

| Fact Table Column | Related Table | Related Column |
|-------------------|---------------|----------------|
| PatientID | Patients | PatientID |
| DoctorID | Doctors | DoctorID |
| DepartmentID | Departments | DepartmentID |
| ProcedureID | Procedures | ProcedureID |
| VisitDate | Date Table | Date |

These relationships allow dimension tables to filter the Hospital Visits fact table while supporting accurate calculations and interactive reporting throughout the dashboard.

---

# Notes

- The data model follows a Star Schema design.
- The Hospital Visits table is the only fact table in the model.
- All remaining imported tables function as dimension tables.
- Revenue is the only calculated column created during data preparation.
- Business KPIs were created as DAX measures and stored separately within the DAX Measures table.
- The Date Table was generated using DAX to support time-based analysis and ensure chronological reporting.
