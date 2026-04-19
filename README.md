# DataVizClassProject

A data visualization class project (CS3751) that analyses student quiz performance across three quizzes. The dataset contains per-student attempt records—start time, completion time, total grade, and per-question marks—for Quiz 1, Quiz 2, and Quiz 3.

---

## Repository Structure

```
DataVizClassProject/
├── Task 1/          # Task 1 notebooks and description
├── Task 2/          # Task 2 notebooks and description
└── README.md
```

---

## Dataset

All notebooks read from a shared CSV dataset stored under `dataset/marks/`:

| File | Description |
|------|-------------|
| `dataset/marks/quiz1/quiz1_marks.csv` | Student attempt records for Quiz 1 |
| `dataset/marks/quiz2/quiz2_marks.csv` | Student attempt records for Quiz 2 |
| `dataset/marks/quiz3/quiz3_marks.csv` | Student attempt records for Quiz 3 |

Each CSV contains columns such as `Student Code`, `State`, `Started on`, `Completed`, `Time taken`, `Grade/10.00`, and per-question scores (`Q. 1 /2.00` … `Q. 5 /2.00`).

---

## Task 1 – Answer Five Given Hypotheses

> **Goal:** Investigate five pre-defined hypotheses about student quiz performance using data visualizations.

### Files

| File | Hypothesis | Key Libraries | Visualizations |
|------|------------|---------------|----------------|
| `Task 1/t1` | Plain-text task description | — | — |
| `Task 1/2.ipynb` | **Hypothesis 2 – Some questions are consistently harder than others.** Analyses question-level success rates across quizzes, keeping only each student's first attempt to reduce learning-effect bias. | NumPy, Pandas, Matplotlib | Bar charts of average marks per question; difficulty comparison across quizzes |
| `Task 1/hypothesis 3.ipynb` | **Hypothesis 3 – Performance trends differ across multiple attempts between high and low performers.** Classifies students as High (avg ≥ 7), Medium, or Low (avg < 5) performers and tracks score progression over repeated attempts. | Pandas, Matplotlib | Line plots of average performance trend per attempt; bar charts of consistency (standard deviation); box plots of score distribution by performer type |
| `Task 1/Task_01_Hypothesis_04.ipynb` | **Hypothesis 4 – More difficult questions take longer to answer, but higher-performing students answer them faster than lower-performing students.** Uses four complementary visualizations and non-parametric statistical tests (Kruskal-Wallis, Mann-Whitney U) to confirm the hypothesis. **Verdict: Accepted.** | Pandas, NumPy, Matplotlib, Seaborn, SciPy | Grouped box-plot (time per difficulty × performance tier); bar chart with 95% confidence intervals; violin plot; scatter plot with per-tier regression lines |
| `Task 1/5.ipynb` | **Hypothesis 5 – There is a relationship between the time a student spends on a quiz and their final grade.** Examines whether faster or slower students score higher, and also explores hourly and yearly patterns in quiz attempts. | Pandas, NumPy, Matplotlib, Seaborn, statsmodels | Scatter plots (time vs. grade per quiz); bar charts of average grade by time range; box plots and violin plots of time distribution per grade; bar chart of quiz attempts by hour of day |

---

## Task 2 – Propose and Verify Five New Hypotheses

> **Goal:** Formulate five original hypotheses about the dataset and verify each with appropriate visualizations.

### Files

| File | Hypothesis | Key Libraries | Visualizations |
|------|------------|---------------|----------------|
| `Task 2/t2` | Plain-text task description | — | — |
| `Task 2/hyp3.ipynb` | **Hypothesis 3 – Score improvements decrease after several attempts (learning plateaus over time).** Tracks average grade changes across successive quiz attempts to determine whether gains flatten out. | Pandas, Matplotlib | Line/trend plots of average score vs. attempt number |
| `Task 2/4.ipynb` | **Hypothesis 4 – Students who fail the first question (Q1) are statistically more likely to have a lower success rate on subsequent questions (Q2–Q5) compared to those who get Q1 correct.** Uses only each student's first attempt per quiz. | Pandas, NumPy, Matplotlib | Bar charts comparing subsequent-question success rates between Q1-pass and Q1-fail groups |
| `Task 2/Task_02_Hypothesis_05.ipynb` | **Hypothesis 5 – Students who score on hard questions achieve disproportionately higher overall grades than students who only score on easy questions, even when easy-question performance is held constant.** Classifies students as *Easy Only*, *Hard Only*, or *Scores on Both* and compares their overall grades. **Verdict: Accepted.** | Pandas, NumPy, Matplotlib, Seaborn, SciPy | Bar chart of mean grade by performance profile with 95% CI; box plot of grade distribution by profile; additional statistical comparisons using Kruskal-Wallis, Mann-Whitney U, and Spearman correlation |

---

## Technologies Used

- **Python 3** (Google Colab environment)
- **Pandas** – data loading, cleaning, and manipulation
- **NumPy** – numerical operations
- **Matplotlib** – core plotting library
- **Seaborn** – statistical data visualization
- **SciPy** (`stats`, `kruskal`, `mannwhitneyu`, `spearmanr`) – hypothesis testing
- **statsmodels** – OLS regression modelling
