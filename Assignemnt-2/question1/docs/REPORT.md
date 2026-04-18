# Q1 Used Cars Analysis Findings

# Part (a) - Missing Values

- Rows with missing **Price** (the target) were dropped.
- Remaining **numeric** columns were filled with the **median** to limit the influence of outliers and skewed distributions.
- **Owner_Type** was filled with the **mode** when missing (most common category).

# Part (b) - Numeric Conversion

- Units removed from **Mileage**, **Engine**, **Power**, and **New_Price** so those fields are plain numbers.

# Part (c) - One-Hot Encoding

- **Fuel_Type** and **Transmission** were converted to dummy columns (`Fuel_Type_*`, `Transmission_*`).

# Part (d) - Car Age Feature

- Added **Car_Age** = current year − **Year** (notebook uses **2026** as the current year).

# Part (e) - Data Manipulations

- Selected and renamed columns (including one-hot columns).
- Filtered to listings with **Price** ≥ 3 lakhs and **Kilometers_Driven** ≤ 80,000 km.
- Created **Price_per_age_year** (price per year of vehicle age).
- Sorted by **Location** and **Price**.
- Grouped by **Location** with summary statistics (e.g. average price, listing count, median **Car_Age**).

### Dataset description (short)

Each row is one listing; **Price** is in **lakhs**. Raw exports may include **Electric** as well as petrol/diesel; one-hot encoding handles all observed fuel categories.
