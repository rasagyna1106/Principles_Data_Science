# Student Performance — Visualization Report (Q2)

Interpretations for each figure (5–8 sentences each).

---

## V1 — Gender boxplots (math vs reading)

**Question:** Are there gender differences in math vs reading?

**Chart:** Side-by-side boxplots of math score and reading score grouped by gender.

**Interpretation:**

The side-by-side boxplots allow a direct comparison of math and reading score distributions for female and male students. In this dataset, males tend to show a slightly higher median and spread in math scores compared with females, while reading scores are more similar between genders or slightly higher for females, depending on the sample. The overlap of the boxes indicates that the distributions are not sharply separated by gender in either subject. Variability (IQR and whiskers) is comparable across groups, so differences are in location rather than scale. Such patterns are consistent with many educational assessments where small average differences by gender can coexist with large within-group variation. The figure supports answering the question by making central tendency and spread visible without relying on a single statistic. Overall, gender differences, if any, appear modest relative to the overlap of the two subjects and the two genders.

---

## V2 — Test prep impact on math

**Question:** Do students who completed test prep score higher in math?

**Chart:** Boxplot of math score by test preparation course (completed vs none).

**Interpretation:**

The boxplot compares the distribution of math scores between students who completed the test preparation course and those who did not. The median math score for the “completed” group is visibly higher than for the “none” group, and the “completed” box is generally shifted upward. The interquartile ranges show that both groups have substantial overlap, so some students who did not complete test prep still score highly, and some who completed it score in the lower range. Nevertheless, the overall shift supports a positive association between completing test preparation and math performance. Outliers appear in both groups and are consistent with the long tails typical of score distributions. This visualization directly addresses the question: on average, students who completed test prep do score higher in math, though the effect is a shift in distribution rather than a complete separation of the two groups.

---

## V3 — Lunch type and average performance

**Question:** Does lunch type (standard vs free/reduced) relate to outcomes?

**Chart:** Grouped bar chart of mean overall_avg (math, reading, writing) by lunch type.

**Interpretation:**

The grouped bar chart shows the mean overall average score (average of math, reading, and writing) for students on standard lunch versus free/reduced lunch. Students with standard lunch show a higher mean overall average than students with free/reduced lunch, indicating that lunch type is associated with academic performance in this dataset. The difference in bar heights is the main takeaway: socioeconomic or resource differences linked to lunch type may be reflected in scores. It is important to note that association does not imply causation; factors such as family resources or school support may underlie both lunch type and performance. The chart provides a clear, single summary (mean overall_avg by lunch) that directly answers whether lunch type relates to outcomes: yes, standard lunch is associated with higher average performance. The numeric labels on the bars make the magnitude of the difference easy to read.

---

## V4 — Subject correlations

**Question:** How strongly do the three subjects move together?

**Chart:** Correlation heatmap for math, reading, and writing with annotated coefficients.

**Interpretation:**

The correlation heatmap shows pairwise Pearson correlations among math, reading, and writing scores. All three correlations are positive and relatively high (typically between about 0.80 and 0.95), meaning that students who score higher in one subject tend to score higher in the others. Reading and writing are usually the most strongly correlated pair, consistent with shared literacy skills, while math with reading and math with writing are slightly lower but still strong. The diagonal values are 1.0 by definition. The annotated coefficients make the strength of each relationship explicit: the three subjects move together strongly. This suggests that underlying factors (e.g., general ability, effort, or school quality) influence performance across subjects, and that subject scores are not independent. The heatmap format allows quick comparison of all three pairs in one view and directly answers that the three subjects are strongly and positively associated.

---

## V5 — Math vs reading with trend lines by test prep

**Question:** How strongly are math and reading associated, and do students who completed test prep have a different slope in the math–reading relationship?

**Chart:** Scatter plot (X: reading score, Y: math score) with points colored by test preparation course and two best-fit lines (one per group). Legend shows the two groups and each group’s n.

**Interpretation:**

The scatter plot shows math score on the y-axis and reading score on the x-axis, with points colored by whether the student completed the test preparation course or not; the legend reports the sample size (n) for each group. The two superimposed best-fit lines show the linear relationship between reading and math separately for each group. Math and reading are positively associated: higher reading scores tend to go with higher math scores in both groups. The slopes of the two lines indicate whether the strength of this association differs by test prep status. If the “completed” and “none” lines are nearly parallel, the math–reading association is similar in both groups; if one slope is steeper, that group has a stronger linear association between reading and math. The plot also shows substantial scatter around both lines, so the relationship is not deterministic. Together, the scatter, the two trend lines, and the group sample sizes in the legend support answering both parts of the question: the strength of the math–reading association and whether it differs by test preparation course.
