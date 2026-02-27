# Student Performance - PDS Data Science Workflows

Step-by-step data science pipelines: **Q1 - Grip Strength and Frailty Study** (female participants) and **Q2 - Student Performance Analysis** (demographics, test prep, lunch type and subject correlations).

---

## Repository structure

```
Student Performance/
├── data/
│   ├── raw/
│   │   └── frailty_raw.csv
│   └── processed/
│       ├── frailty_processed.csv
│       ├── students_performance_processed.csv
│       └── StudentsPerformance_cleaned.csv
├── reports/
│   ├── figures/                   # Q2 visualizations (V1–V5) PNGs
│   ├── findings.md                # Q1 frailty EDA
│   ├── findings_students.md       # Q2 students EDA
│   └── visualization_report.md    # Q2 figure interpretations
├── 01_frailty_workflow.ipynb      # Q1: three-stage frailty pipeline
├── 02_students_performance_analysis.ipynb
├── 03_student_performance_visualizations.ipynb   # Q2: 5 figures (V1–V5)
├── StudentsPerformance.csv        # Q2 input (place in project root)
├── requirements.txt
└── README.md
```

---

# Question 1 - Grip Strength and Frailty Study (Female Participants)

## Data information

Data includes hand grip strength from a dynamometer and participant characteristic data.

### Variables

| Variable      | Description                                      |
|---------------|--------------------------------------------------|
| **Height**    | Participant height in inches                     |
| **Weight**    | Participant weight in pounds                    |
| **Age**       | Participant age in years                        |
| **Grip Strength** | Hand grip strength in kilograms             |
| **Frailty**   | Qualitative measurement of frailty (Y = frail, N = not frail) |

## Study overview

The study explores the relationship between grip strength and frailty among female participants. Exploratory data analysis (EDA), visualization and predictive modeling are applied to identify frailty determinants.

## Exploratory Data Analysis (EDA)

- Summary statistics: Mean, standard deviation and distribution of all numerical variables were calculated to summarize participant information.
- Correlation analysis: A correlation matrix was calculated to assess correlations between numerical variables.

### Key findings

- Grip strength and frailty: Increased grip strength corresponds to reduced frailty scores.
- Age and grip strength: Female grip strength decreases with age.

## Visualizations

- Correlation heatmap: Displays strength of numeric variable relationships.
- Scatter plot: Age vs. grip strength with frailty status shown by color.
- Box plot: Compares non-frail vs. frail group grip strength; frail participants show weaker grip strength.

## Model evaluation

- Accuracy: 80% on test set, indicating good fit of prediction.
- Confusion matrix: Provides true positives, true negatives, false positives, and false negatives.
- Classification report: Precision, recall, and F1-score for frail and non-frail classes:
  - Frail class precision: 67% (ratio of frail cases correctly predicted)
  - Frail class recall: 100% (ratio of actual frail cases correctly predicted)

## How to run (Q1)

Open **`01_frailty_workflow.ipynb`** and run all the cells.

- Stage 1 - Ingest: Read `data/raw/frailty_raw.csv` into a pandas DataFrame.
- Stage 2 - Process: Unit standardization (Height→m, Weight→kg), BMI, AgeGroup, Frailty_binary, one-hot AgeGroup.
- Stage 3 - Analyze: Summary table (mean/median/std), correlation Grip_kg vs Frailty_binary.
- Output: `data/processed/frailty_processed.csv`, `reports/findings.md`.

---

# Question 2 - Student Performance Analysis

The project compares student performance in Math, Reading and Writing with demographic variables such as gender, lunch type and test preparation.

## Data cleaning

- Renamed column names to standard names and normalized scores to numeric type.
- Filled missing values with group median and overall median.
- Cleaned dataset saved as `data/processed/StudentsPerformance_cleaned.csv`.

## Visualizations

All plots are saved as PNGs (e.g. in `reports/figures/` or Result folder). Each figure: 800×600 px, 300 DPI, with title, labeled axes and legend where ever applicable.

### V1: Gender split for Math vs Reading (boxplots)

From the box plots, the performance of male and female students is shown for mathematics and reading scores. Female students perform slightly higher in reading with a small lead in mathematics scores by male students. There is an overlapping of scores between the two groups which indicates that the performance is not sharply divided. Some scores act as outliers in the performance of these groups.

### V2: Effect of test prep on Math scores (boxplots)

Students who had test preparation scored higher in math. The median of prepared students is higher than that of students who did not get any preparation. Prepared students lack scores in the lowest value range. Students who did not receive preparation have scores spread across a wider range of values.

### V3: Lunch type vs average score (bar chart)

A bar chart shows performance by lunch type. Standard lunch students performance is higher than free/reduced lunch students. This basically suggests that the economic influences may affect student performance. Free or reduced lunch students may receive less support and hence lower scores.Overall, the standard lunch students perform better in academics.

### V4: Math, Reading, Writing correlation (heatmap)

The heatmap shows positive correlations between math, reading and writing. Reading and writing are most strongly correlated. The students who perform well in reading tend to perform well in writing. Math is well correlated with both reading and writing. The heatmap suggests that skills in one subject can help improve performance in others.

### V5: Math vs Reading by test prep (scatter with trend lines)

There is a positive correlation between math and reading scores. Students who received test preparation scored higher in both math and reading and are grouped more closely. Students who did not receive test preparation scored lower in a more scattered pattern. Higher scores are associated with test preparation as indicated by the trend lines. Math and reading scores are closely linked with test preparation making a significant impact.

## Summary (Q2)

From the visualizations, performance is influenced by gender, test preparation and lunch type and the three subjects (math, reading, writing) are highly correlated.

## How to run (Q2)

1. Place `StudentsPerformance.csv` in the project root.
2. Open `03_student_performance_visualizations.ipynb` and run all cells.
3. Ingestion: Load `StudentsPerformance.csv`.
4. Preprocessing: Numeric scores, handle missing values, add `overall_avg`, normalize lunch and test_prep; cleaned data saved to `data/processed/StudentsPerformance_cleaned.csv`.
5. V1–V5: Figures saved under `reports/figures/` (or Result folder depending on notebook configuration).

---

## Assignment alignment checklist

**Q1 — Frailty workflow**  
- Three-stage workflow (ingest → process → analyze) in `01_frailty_workflow.ipynb`.  
- Raw data: `data/raw/frailty_raw.csv`.  
- Unit standardization: `Height_m`, `Weight_kg`.  
- Feature engineering: BMI (2 decimals), AgeGroup (<30, 30–45, 46–60, >60).  
- Encoding: Frailty_binary (Y→1, N→0); one-hot AgeGroup.  
- EDA: Summary table and correlation Grip_kg ↔ Frailty_binary in `reports/findings.md`.

**Q2 — Student performance**  
- Data cleaning → `StudentsPerformance_cleaned.csv`.  
- V1: Gender boxplots (math vs reading).  
- V2: Test prep impact on math (boxplot).  
- V3: Mean overall_avg by lunch type (bar chart).  
- V4: Correlation heatmap (math, reading, writing).  
- V5: Math vs reading scatter with trend lines by test prep.  
- Figures: 800×600 px, 300 DPI; interpretations in `reports/visualization_report.md`.
