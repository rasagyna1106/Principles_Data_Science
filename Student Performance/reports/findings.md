# Question 1 - Grip Strength and Frailty Study: Findings

**Female participants.** Data include hand grip strength (dynamometer) and participant characteristics. Variables: Height (in), Weight (lb), Age (years), Grip Strength (kg), Frailty (Y = frail, N = not frail).

---

## Summary statistics (numeric columns)

| Statistic | Height | Weight | Age | Grip(kg) | Height(m) | Weight(kg) | BMI | Frailty_binary |
|-----------|--------|--------|-----|---------|----------|-----------|-----|----------------|
| mean      | 68.6   | 131.9  | 32.5| 26.0    | 1.7424   | 59.8288   | 19.682 | 0.4   |
| median    | 68.45  | 136.0  | 29.5| 27.0    | 1.7386   | 61.6886   | 19.185 | 0.0   |
| std       | 1.6707 | 14.2318| 12.8604| 4.5216| 0.0424   | 6.4554    | 1.781  | 0.5164|

---

## Correlation: Grip strength vs Frailty

- Correlation (Grip_kg, Frailty_binary): -0.4759

Interpretation: Negative correlation indicates that higher grip strength is associated with lower frailty (Frailty_binary 0) and lower grip strength with higher frailty (1). Increased grip strength corresponds to reduced frailty scores.

---

## Key findings

- Grip strength and frailty: Increased grip strength corresponds to reduced frailty scores.
- Age and grip strength: Female grip strength decreases with age.

---

## EDA outputs

- Summary statistics (mean, standard deviation, distribution) of all numerical variables were calculated to summarize participant information.
- Correlation analysis was used to assess relationships between numerical variables.
- Visualizations: correlation heatmap (numeric variable relationships), scatter plot (age vs. grip strength, colored by frailty), box plot (non-frail vs. frail grip strength).
- Model evaluation (when run): 80% accuracy on test set; confusion matrix; classification report (e.g. frail class precision 67%, recall 100%).


