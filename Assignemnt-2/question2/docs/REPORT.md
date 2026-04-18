# Q2 Diabetes Analysis Findings

## Part (a) — Glucose sample vs population

- Population statistics: Population mean Glucose = 120.895; population max = 199.
- Sample statistics: Sample (n = 25, seed = 42) mean Glucose = 116.640; sample max = 183.
- See `figures/Q2a_glucose_kde_compare.png` and `figures/Q2a_glucose_box_compare.png`.

---

## Part (b) — BMI 98th percentile

- Population 98th percentile BMI = 47.526.
- Sample 98th percentile BMI = 40.248.
- See `figures/Q2b_bmi_p98_compare.png`.

---

## Part (c) — Bootstrap on BloodPressure (R = 500, m = 150)

- Population mean / std / 98th = 69.105, 19.356, 99.320.
- Bootstrap average mean / std / 98th = 69.136, 19.186, 98.125 (bootstrap seed `SEED_BOOT = 12345`).
- See `figures/Q2c_bootstrap_bp_stats.png` and `outputs/bootstrap_bp_stats.csv`.

---

## Notes (methods & links)

**Dataset:** [Box — diabetes data](https://app.box.com/s/7qv44umhw0vnzgmoe9krfkfkv5kf2atv) → save as `question2/data/diabetes.csv`.  
**Notebook:** `question2/notebooks/diabetes_assignment.ipynb` — **Restart & Run All** regenerates `figures/` and `outputs/bootstrap_bp_stats.csv`.

**Procedure summary**

| Part | What we did |
|------|-------------|
| **(a)** | `SEED = 42`; simple random sample **n = 25**; compare sample vs population **Glucose** mean and max; bar / KDE / box charts → `figures/`. |
| **(b)** | Sample vs population **98th percentile BMI** (`quantile(0.98)`); bar + KDE charts → `figures/`. |
| **(c)** | **500** bootstrap replicates of **150** draws with replacement from population **BloodPressure** (`numpy.random.default_rng(SEED_BOOT)`); average replicate mean, SD (ddof = 1), and P98 vs population; bars + histogram panel → `figures/`; per-replicate table → `outputs/bootstrap_bp_stats.csv`. |

Additional bar charts for the same analyses: `Q2a_glucose_bar_compare.png`, `Q2b_bmi_p98_bar_compare.png`, `Q2c_bootstrap_bp_bar_compare.png`.
