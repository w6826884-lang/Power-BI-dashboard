# 🩺 Cancer Screening & Treatment Analytics Dashboard

A multi-page Power BI report analyzing cancer screening coverage, patient pipeline, diagnosis timelines, treatment outcomes, and healthcare access across Indian states and districts.

---

## 📊 Report Overview

| Property | Detail |
|---|---|
| **File** | `Assignment1.pbix` |
| **Tool** | Microsoft Power BI Desktop |
| **Pages** | 3 |
| **Data Source** | `Sheet1` (tabular dataset with state/district-level health metrics) |
| **Theme** | CY24SU10 (Power BI built-in) |
| **Custom Visuals** | 3 active (Bullet Chart, Strip Plot, Waffle Chart) + 3 bundled |

---

## 📁 Report Pages

### Page 1 — Screening Coverage

Focuses on how well each state and district is meeting its cancer screening targets.

| Visual | Type | Fields Used |
|---|---|---|
| Screening Coverage vs Target | **Bullet Chart** *(OKVIZ)* | `Screening_Coverage_percent`, `State`, `Target` |
| District-level Coverage Distribution | **Strip Plot** *(Nova Silva)* | `State`, `Avg(Screening_Coverage_percent)`, `District` |
| Population Reached by Screening Program | **Waffle Chart** | `Screen%`, `Column1` |

---

### Page 2 — Cancer Pipeline & Diagnosis

Tracks the patient journey from eligibility through treatment completion, and examines stage detection and wait times.

| Visual | Type | Fields Used |
|---|---|---|
| Patient Funnel | **Funnel Chart** | `Eligible_for_Screening`, `Screened_People`, `Suspected_Cases`, `Confirmed_Cancer`, `Treatment_Started`, `Treatment_Completed` |
| Early vs Late Stage Detection by State | **Column Chart** | `Early_Stage_Pct`, `Late_Stage_Pct`, `State` |
| Diagnosis & Treatment Wait Times | **Clustered Bar Chart** | `State`, `Avg_Diagnosis_Time_Days`, `Avg_Treatment_Wait_Days` |

---

### Page 3 — Outcomes & Access

Examines survival rates, socioeconomic risk, insurance coverage, and treatment costs.

| Visual | Type | Fields Used |
|---|---|---|
| One-Year Survival Rate by State | **Clustered Bar Chart** | `State`, `One_Year_Survival_Rate_percent` |
| Survival Rate vs Early Detection (by District) | **Scatter Chart** | `One_Year_Survival_Rate_percent`, `District_Early_Pct`, `State`, `District` |
| Risk, Insurance & Treatment Cost Matrix | **Pivot Table** | `State`, `Risk_Index`, `Insurance_Coverage_percent`, `Avg_Treatment_Cost_INR` |
| Screening Coverage by District Type | **Clustered Bar Chart** | `District_Type`, `State`, `Screening_Coverage_percent` |

---

## 🧩 Custom Visuals

| Visual | Publisher | Used In |
|---|---|---|
| [Bullet Chart by OKVIZ](https://okviz.com/bullet-chart/) | OKVIZ | Page 1 |
| [Strip Plot by Nova Silva](https://novsilva.com.br) | Nova Silva | Page 1 |
| [Waffle Chart](https://appsource.microsoft.com/en-us/product/power-bi-visuals/wa104381049) | Community | Page 1 |
| Power KPI Matrix 3.1.1 | Microsoft | Bundled |
| Box and Whisker by MAQ Software | MAQ Software | Bundled |
| Dumbbell Chart by MAQ Software | MAQ Software | Bundled |

> **Note:** Bundled visuals are included in the `.pbix` but are not actively placed on any report page.

---

## 🗂️ Data Fields Reference

| Field | Description |
|---|---|
| `State` | Indian state name |
| `District` | District within a state |
| `District_Type` | Classification of district (e.g., urban/rural) |
| `Eligible_for_Screening` | Total population eligible for cancer screening |
| `Screened_People` | Number of people screened |
| `Suspected_Cases` | Cases flagged as suspected cancer |
| `Confirmed_Cancer` | Confirmed cancer diagnoses |
| `Treatment_Started` | Patients who began treatment |
| `Treatment_Completed` | Patients who completed treatment |
| `Screening_Coverage_percent` | % of eligible population screened |
| `Target` | Screening coverage target |
| `Screen%` | Alternate screening percentage metric |
| `Early_Stage_Pct` | % of cancers detected at early stage |
| `Late_Stage_Pct` | % of cancers detected at late stage |
| `District_Early_Pct` | District-level early-stage detection rate |
| `Avg_Diagnosis_Time_Days` | Average days from screening to diagnosis |
| `Avg_Treatment_Wait_Days` | Average days from diagnosis to treatment start |
| `One_Year_Survival_Rate_percent` | 1-year post-treatment survival rate |
| `Risk_Index` | Composite health risk index for the area |
| `Insurance_Coverage_percent` | % of population with health insurance |
| `Avg_Treatment_Cost_INR` | Average cancer treatment cost (₹) |

---

## 🚀 Getting Started

### Prerequisites

- [Power BI Desktop](https://powerbi.microsoft.com/desktop/) (free) — any version from **2024** onwards is recommended for full theme and custom visual compatibility.

### Opening the Report

1. Clone or download this repository.
2. Open **Power BI Desktop**.
3. Go to **File → Open report** and select `Assignment1.pbix`.
4. If prompted about custom visuals, click **Enable** to allow them to render.

### Refreshing Data

The report uses a static embedded data model. To connect your own data:

1. Go to **Home → Transform data** to open Power Query.
2. Replace the `Sheet1` source with your own file or database connection.
3. Ensure your source contains the same column names listed in the [Data Fields Reference](#-data-fields-reference) above, or remap the fields in each visual.

---

## 📌 Notes

- Currency values (`Avg_Treatment_Cost_INR`) are in **Indian Rupees (₹)**.
- The report theme is Power BI's built-in **CY24SU10** — no external theme file is required.
- All custom visuals are **embedded within the `.pbix`** file; no separate installation is needed when opening the report.

---

## 📄 License

This project is submitted as an academic assignment. Please do not redistribute or repurpose the data or report without permission.
