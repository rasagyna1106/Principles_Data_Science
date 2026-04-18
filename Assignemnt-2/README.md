## PDS Assignment - Question 1 & Question 2 

| Question | Topic | Folder | Notebook (primary code) |
|----------|-------|--------|-------------------------|
| **1** | Used-car listings — missing data, units, one-hot, `Car_Age`, dplyr-style pandas | **`question1/`** | **`question1/notebooks/used_cars_assignment.ipynb`** |
| **2** | Diabetes population — sampling n=25, BMI P98, bootstrap BP | **`question2/`** | **`question2/notebooks/diabetes_assignment.ipynb`** |

- Code for **Question 1** exists **only** under **`question1/`**.
- Code for **Question 2** exists **only** under **`question2/`**.
- Written summaries: **`question1/docs/REPORT.md`** (Q1) and **`question2/docs/REPORT.md`** (Q2).
---

### Official data links

| Question | Box link |
|----------|----------|
| **Q1 — Used cars** | [https://app.box.com/s/jm6pw202asu4xd3uypwtry2rqk691y1i](https://app.box.com/s/jm6pw202asu4xd3uypwtry2rqk691y1i) |
| **Q2 — Diabetes** | [https://app.box.com/s/7qv44umhw0vnzgmoe9krfkfkv5kf2atv](https://app.box.com/s/7qv44umhw0vnzgmoe9krfkfkv5kf2atv) |

Place downloads as **`question1/data/train.csv`** and **`question2/data/diabetes.csv`*.

### Setup 

```bash
pip install -r requirements.txt
```

Open each notebook separately and **Restart & Run All**.

---

### Rubric snapshot

**Question 1:** (a) missing values + justification (b) strip units (c) one-hot Fuel & Transmission (d) new feature e.g. `Car_Age` (e) select/filter/rename/mutate/arrange/groupby+summarize.

**Question 2:** (a) seed, n=25, Glucose mean & max vs population + charts (b) BMI 98th sample vs population + charts (c) 500 bootstrap samples of 150, BP mean/SD/percentile vs population + charts + report.
