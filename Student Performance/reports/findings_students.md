# Question 2 — Student Performance Analysis: Findings

The project compares student performance in **Math, Reading, and Writing** with demographic variables: **gender**, **lunch type**, and **test preparation**. Cleaned dataset: `data/processed/StudentsPerformance_cleaned.csv`.

---

## Data cleaning

- Column names renamed to standard names; score columns normalized to numeric type.
- Missing values filled with group median (by gender, lunch, test prep) and overall median where needed.
- Output: **StudentsPerformance_cleaned.csv** in `data/processed/`.

---

## 1. Summary statistics (numeric columns)

| Statistic | math_score | reading_score | writing_score | total_score | average_score | passed | test_prep_binary | lunch_standard | gender_male |
|-----------|------------|---------------|---------------|-------------|---------------|--------|-------------------|---------------|-------------|
| mean      | 66.0890    | 69.1690       | 68.0540       | 203.312     | 67.7706       | 0.7150 | 0.3580            | 0.6450        | 0.4820      |
| median    | 66.0000    | 70.0000       | 69.0000       | 205.000     | 68.3300       | 1.0000 | 0.0000            | 1.0000        | 0.0000      |
| std       | 15.1631    | 14.6002       | 15.1957       | 42.772      | 14.2573       | 0.4516 | 0.4797            | 0.4788        | 0.4999      |

---

## 2. Correlation matrix (scores and key binaries)

|                  | math_score | reading_score | writing_score | average_score | passed | test_prep_binary |
|------------------|------------|---------------|---------------|---------------|--------|------------------|
| math_score       | 1.0000     | 0.8176        | 0.8026        | 0.9187        | 0.7015 | 0.1777           |
| reading_score    | 0.8176     | 1.0000        | 0.9546        | 0.9703        | 0.7495 | 0.2418           |
| writing_score    | 0.8026     | 0.9546        | 1.0000        | 0.9657        | 0.7550 | 0.3129           |
| average_score    | 0.9187     | 0.9703        | 0.9657        | 1.0000        | 0.7728 | 0.2567           |
| passed           | 0.7015     | 0.7495        | 0.7550        | 0.7728        | 1.0000 | 0.1942           |
| test_prep_binary | 0.1777     | 0.2418        | 0.3129        | 0.2567        | 0.1942 | 1.0000           |

---

## 3. Key relations

- **Correlation (average_score, passed):** 0.7728  
- **Correlation (average_score, test_prep_binary):** 0.2567  

**Interpretation:** Positive correlation with test_prep_binary suggests that completing test preparation is associated with higher average scores. Math, reading, and writing are highly correlated; performance is influenced by gender, test preparation, and lunch type.

---

## Summary

From the analyses and visualizations (V1–V5), **performance is influenced by gender, test prep, and lunch type**, and the three subjects (math, reading, writing) are **highly correlated**. All plots are exported as PNGs in `reports/figures/` (800×600 px, 300 DPI).
