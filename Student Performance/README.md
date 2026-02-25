# PDS — Data Science Workflows (Ingest → Process → Analyze)

Step-by-step data science pipelines: **Frailty & Grip Strength** (assignment) and **Students Performance** (GitHub-ready analysis).

## Repository structure

```
PDS/
├── data/
│   ├── raw/
│   │   └── frailty_raw.csv
│   └── processed/
│       ├── frailty_processed.csv
│       └── students_performance_processed.csv
├── reports/
│   ├── figures/                 # Q2 visualizations (V1–V5)
│   ├── findings.md              # Frailty EDA
│   ├── findings_students.md     # Students performance EDA
│   └── visualization_report.md # Q2 figure interpretations
├── 01_frailty_workflow.ipynb    # Same workflow, Jupyter notebook
├── 02_students_performance_analysis.ipynb  # Same, Jupyter notebook
├── 03_student_performance_visualizations.ipynb  # Q2: same as above, Jupyter notebook
├── StudentsPerformance.csv     # Input for students analysis
├── requirements.txt
└── README.md
```

## Setup

```bash
pip install -r requirements.txt
```

## Run

**Frailty workflow (10 female participants, grip strength vs frailty):**

- **Jupyter notebook:** Open `01_frailty_workflow.ipynb` and run all cells (ingest → process → analyze). Report is written to `reports/findings.md`.

- **Stage 1 — Ingest:** Load `data/raw/frailty_raw.csv` into a pandas DataFrame.
- **Stage 2 — Process:** Unit standardization (Height→m, Weight→kg), BMI, AgeGroup, Frailty_binary, one-hot AgeGroup.
- **Stage 3 — Analyze:** Summary stats (mean/median/std), correlation Grip_kg vs Frailty_binary → `reports/findings.md`.

**Students performance (step-by-step analysis for GitHub):**

- **Jupyter notebook:** Open `02_students_performance_analysis.ipynb` and run all cells (ingest → process → analyze). Report → `reports/findings_students.md`.

- **Stage 1 — Ingest:** Load `StudentsPerformance.csv`.
- **Stage 2 — Process:** Total/average score, GradeBand (A–F), passed (binary), test_prep_binary, lunch_standard, one-hot GradeBand.
- **Stage 3 — Analyze:** Summary table, correlation matrix, relation average_score ↔ passed and test_prep → `reports/findings_students.md`.

**Q2 — Student performance visualizations (5 figures + report):**

- **Jupyter notebook:** Open `03_student_performance_visualizations.ipynb` and run all cells (ingestion → preprocessing → V1–V5 → report note). Figures display inline and are saved to `reports/figures/`.

- **Ingestion:** Load `StudentsPerformance.csv`.
- **Preprocessing:** Numeric scores, drop missing, add `overall_avg`, normalize lunch/test_prep.
- **V1:** Gender boxplots (math vs reading). **V2:** Test prep impact on math (boxplot). **V3:** Mean overall_avg by lunch (bar). **V4:** Correlation heatmap (math, reading, writing). **V5:** Math vs reading scatter with trend lines by test prep (legend with n).
- Figures: 800×600 px, 300 DPI, in `reports/figures/`. Interpretations (5–8 sentences each) in `reports/visualization_report.md`.
