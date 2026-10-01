# Student Performance Analysis

A data analytics project exploring the academic performance of 395 secondary school students. This project uses Python to clean, analyze, and visualize student data to uncover patterns between attendance, study habits, and final grades.

---

## Project Overview

The goal of this project is to analyze student academic performance and identify the key factors that influence final grades. Using a real-world dataset of 395 students, we explore how variables like **attendance, study time, past failures, and parental education** relate to academic outcomes.

This project demonstrates a complete data analytics workflow — from raw data to actionable insights.

---

## Objectives

- Clean and preprocess raw student data
- Explore performance trends across three assessment periods (G1, G2, G3)
- Visualize distributions and relationships using charts
- Statistically test whether attendance level affects final grades
- Generate insights and recommendations for educators

---

##  Dataset

- **Source:** [UCI Machine Learning Repository — Student Performance Data Set](https://archive.ics.uci.edu/ml/datasets/Student+Performance)
- **File:** `student_data.csv`
- **Rows:** 395 students
- **Columns:** 33 features
- **Schools:** 2 (GP: Gabriel Pereira, MS: Mousinho da Silveira)

### Key Features

| Column | Description |
|---|---|
| `school` | Student's school (GP / MS) |
| `sex` | Gender (F / M) |
| `age` | Age (15–22) |
| `studytime` | Weekly study time (1–4 scale) |
| `failures` | Number of past class failures |
| `absences` | Number of school absences |
| `Medu` / `Fedu` | Mother's / Father's education level (0–4) |
| `higher` | Wants to take higher education (yes/no) |
| `internet` | Internet access at home (yes/no) |
| `G1` | First period grade (0–20) |
| `G2` | Second period grade (0–20) |
| `G3` | Final grade (0–20) — **target variable** |

---

##  Tools & Technologies

- **Language:** Python 3.x
- **Libraries:**
  - `pandas` — data loading and manipulation
  - `numpy` — numerical operations
  - `matplotlib` — basic visualizations
  - `seaborn` — statistical charts
  - `scipy` — statistical tests (correlation, ANOVA)

---

##  Project Workflow

### 1. Data Cleaning & Preprocessing
- Checked for missing values and duplicates
- Created derived columns:
  - `pass` → Pass/Fail based on G3 ≥ 10
  - `attendance_band` → High / Medium / Low attendance
  - `grade_change_G1_G3` & `grade_change_G2_G3` → Improvement tracking
- Encoded binary categorical variables for correlation analysis
- Saved cleaned dataset as `student_data_cleaned.csv`

### 2. Exploratory Data Analysis (EDA)
- Summary statistics (`describe()`) for grades and absences
- Average grade trend across G1 → G2 → G3
- Pass/fail distribution
- Group comparisons by gender, school, study time, and failures

### 3. Data Visualization
- **Bar charts:** Average grade by study time, failures, attendance band
- **Histograms:** Distribution of G3 and absences
- **Pie charts:** Pass/Fail ratio, gender distribution
- **Box plots:** Grade spread by attendance group
- **Heatmap:** Correlation matrix across key variables
- **Scatter plot:** Absences vs final grade with trend line

### 4. Statistical Analysis
- **Pearson Correlation:** Absences vs G3
- **One-way ANOVA:** Comparing grades across attendance bands
- **Correlation Heatmap:** Identifying strongest predictors of G3

### 5. Insights & Recommendations
Derived actionable findings from analysis (see below).

---

##  Key Insights

1. **Performance declines slightly over time** — Average grades drop from 10.9 (G1) to 10.4 (G3).
2. **G2 is a strong predictor of G3** — Students who perform well in the second period tend to perform well in the final.
3. **Past failures hurt performance** — Students with more failures have significantly lower final grades.
4. **Study time matters** — Students in higher study-time categories achieve better average grades.
5. **Attendance correlates with grades** — More absences are associated with lower final scores (moderate negative correlation).
6. **Attendance groups differ significantly** — ANOVA test confirms a statistically significant difference in G3 across attendance bands.
7. **Most students pass** — Approximately 67% of students scored G3 ≥ 10.

---

##  Recommendations

- **Early warning system:** Flag students with >15 absences for academic support.
- **Use G1 & G2 as predictors:** Intervene before final exams, not after.
- **Tutoring for repeaters:** Target students with prior failures.
- **Promote structured study habits:** Encourage 2–4+ hours of weekly study.
- **Parental engagement:** Involve guardians in supporting low-performing students.

---

##  Project Structure
student-performance-analysis/
│
├── student_data.csv # Raw dataset
├── student_data_cleaned.csv # Cleaned dataset
├── student_performance.ipynb # Main analysis notebook
├── README.md # This file
├── requirements.txt # Python dependencies
│
└── images/
├── grade_trend.png
├── pass_fail_pie.png
├── histogram_G3.png
├── bar_studytime.png
├── bar_attendance.png
├── correlation_heatmap.png
└── scatter_absences_G3.png

##  How to Run

1. **Clone the repository**
   ```bash
   git clone https://github.com/your-username/student-performance-analysis.git
   cd student-performance-analysis
Install dependencies

bash
pip install -r requirements.txt
Open the notebook

bash
jupyter notebook student_performance.ipynb
Run all cells and explore the outputs.

"Sample Visualizations
Chart	What it shows
https://images/grade_trend.png	Average grade across G1, G2, G3
https://images/pass_fail_pie.png	Pass vs Fail distribution
https://images/correlation_heatmap.png	Correlation between key variables
https://images/scatter_absences_G3.png	Attendance impact on final grades
 Limitations
Dataset is limited to two Portuguese schools — results may not generalize globally.

Attendance is measured as absences, not actual attendance percentage.

Correlation does not prove causation.

G3 = 0 may represent either failure or withdrawal in some cases.
 Future Improvements
Build a predictive model (linear regression / decision tree) to forecast G3 from early features.

Add Power BI / Tableau dashboards for interactive exploration.

Perform post-hoc Tukey test to identify which attendance groups differ.

Extend analysis with clustering to segment student profiles.

 References
Cortez, P., & Silva, A. (2008). Using Data Mining to Predict Secondary School Student Performance.


