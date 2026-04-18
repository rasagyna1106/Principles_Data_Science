# Q1 Used Cars Analysis Findings

## Part (a) — Missing Values

- Rows with missing **Price** (the target) were dropped.
- Remaining **numeric** columns were filled with the **median** to limit the influence of outliers and skewed distributions.
- **Owner_Type** was filled with the **mode** when missing (most common category).

## Part (b) — Numeric Conversion

- Units removed from **Mileage**, **Engine**, **Power**, and **New_Price** so those fields are plain numbers.

## Part (c) — One-Hot Encoding

- **Fuel_Type** and **Transmission** were converted to dummy columns (`Fuel_Type_*`, `Transmission_*`).

## Part (d) — Car Age Feature

- Added **Car_Age** = current year − **Year** (notebook uses **2026** as the current year).

## Part (e) — Data Manipulations

- Selected and renamed columns (including one-hot columns).
- Filtered to listings with **Price** ≥ 3 lakhs and **Kilometers_Driven** ≤ 80,000 km.
- Created **Price_per_age_year** (price per year of vehicle age).
- Sorted by **Location** and **Price**.
- Grouped by **Location** with summary statistics (e.g. average price, listing count, median **Car_Age**).

---

## Notes (methods & artifacts)

**Course data:** [Box — used cars](https://app.box.com/s/jm6pw202asu4xd3uypwtry2rqk691y1i) → `question1/data/train.csv`.  
**Notebook:** `question1/notebooks/used_cars_assignment.ipynb`.  
**Cleaned table (after Run All):** `question1/outputs/train_cleaned.csv`.

### Alignment with assignment rubric

| Part | Requirement |
|------|-------------|
| **(a)** | Audit missing values; drop or impute with justification (median numerics, mode **Owner_Type**, drop missing **Price**). |
| **(b)** | Strip units from mileage, engine, power, new price. |
| **(c)** | One-hot **Fuel_Type** and **Transmission**. |
| **(d)** | New feature **Car_Age**. |
| **(e)** | Demonstrate **select**, **filter**, **rename**, **mutate**, **arrange**, **group_by** + **summarize** (pandas equivalents). |

### Dataset description (short)

Each row is one listing; **Price** is in **lakhs**. Raw exports may include **Electric** as well as petrol/diesel; one-hot encoding handles all observed fuel categories.
