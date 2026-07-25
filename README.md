# 📊 Student Performance Prediction — Linear Regression

A complete **Machine Learning** project that predicts student exam scores using **Linear Regression** (Simple & Multiple), built as part of a university AI & Data Analysis assignment.

---

## 📁 Dataset

**File:** `student_habits_performance.csv`
**Records:** 1,000 students
**Columns:** 16 (15 features + 1 target)

| Column | Type | Description |
|---|---|---|
| `student_id` | ID | Unique identifier (dropped before training) |
| `age` | Numeric | Student age |
| `gender` | Categorical | Male / Female |
| `study_hours_per_day` | Numeric | Daily study hours |
| `social_media_hours` | Numeric | Daily social media usage |
| `netflix_hours` | Numeric | Daily Netflix/streaming hours |
| `part_time_job` | Categorical | Yes / No |
| `attendance_percentage` | Numeric | Class attendance % |
| `sleep_hours` | Numeric | Daily sleep hours |
| `diet_quality` | Categorical | Poor / Fair / Good |
| `exercise_frequency` | Numeric | Exercise days per week |
| `parental_education_level` | Categorical | High School / Bachelor / Master / PhD |
| `internet_quality` | Categorical | Poor / Average / Good |
| `mental_health_rating` | Numeric | Rating 1–10 |
| `extracurricular_participation` | Categorical | Yes / No |
| `exam_score` | Numeric | **Target variable** (0–100) |

---

## 🎯 Task

Predict `exam_score` using all remaining numeric and encoded categorical features.

---

## 📌 Project Workflow

1. **Import Libraries** — pandas, numpy, matplotlib, seaborn, sklearn, joblib
2. **Load Dataset** — shape, info, describe, missing values, duplicates
3. **Exploratory Data Analysis (EDA)**
   - Exam score distribution (histogram + box plot)
   - Scatter plots — 6 numeric features vs exam score (with trend lines & correlation)
   - Bar charts — 6 categorical features vs average exam score
   - Correlation heatmap
4. **Data Cleaning & Preprocessing**
   - Drop `student_id`
   - Fill missing `parental_education_level` with mode
   - Label Encoding for all 6 categorical columns
5. **Simple Linear Regression (SLR)** — `study_hours_per_day` → `exam_score`
6. **Multiple Linear Regression (MLR)** — all 14 features → `exam_score`
7. **Model Comparison** — SLR vs MLR (table + bar charts)
8. **Prediction Results** — first 20 actual vs predicted + custom student prediction
9. **Save & Load Model** — `joblib.dump()` + `joblib.load()`
10. **Summary & Business Insights**

---

## 📈 Visualizations Used

- Histogram + Box Plot (exam score distribution)
- Scatter Plots with Trend Lines (6 features vs exam score)
- Bar Charts (categorical features vs avg exam score)
- Correlation Heatmap
- Actual vs Predicted Scatter Plot
- Feature Importance Bar Chart (|coefficients|)
- Residuals vs Predicted Plot
- Residuals Distribution Histogram
- SLR vs MLR Comparison Charts

---

## 📊 Model Results

| Metric | Simple LR (study_hours only) | Multiple LR (all features) |
|---|---|---|
| MAE | 7.3746 | **4.2415** |
| MSE | 83.2919 | **28.4094** |
| RMSE | 9.1264 | **5.3300** |
| **R² Score** | 0.7001 | **0.8977** |

**MLR achieved 89.77% accuracy** — significantly better than SLR.

---

## 🔑 Key Insights

1. `study_hours_per_day` is the **strongest predictor** of exam score (highest correlation)
2. `attendance_percentage` also strongly influences exam performance
3. `mental_health_rating` has a positive impact on scores
4. `social_media_hours` and `netflix_hours` **negatively** impact exam performance
5. Students with good `diet_quality` and `internet_quality` score consistently higher
6. MLR outperforms SLR by capturing the combined effect of all 14 features

---

## 💾 Saved Models

| File | Description |
|---|---|
| `slr_student_model.joblib` | Simple Linear Regression (study_hours → exam_score) |
| `mlr_student_model.joblib` | Multiple Linear Regression (all features → exam_score) |

---

## 📂 Project Structure

```
Student_Performance_Prediction/
│
├── Student_Performance_Prediction.ipynb   ← Main Jupyter Notebook
├── student_habits_performance.csv         ← Dataset
├── slr_student_model.joblib               ← Saved SLR model (generated on run)
├── mlr_student_model.joblib               ← Saved MLR model (generated on run)
└── README.md                              ← This file
```

---

## ▶️ How to Run

1. Place `Student_Performance_Prediction.ipynb` and `student_habits_performance.csv` in the **same folder**
2. Install required libraries:
   ```bash
   pip install pandas numpy matplotlib seaborn scikit-learn joblib
   ```
3. Open the notebook in Jupyter and run **Cell → Run All**

---

## 🛠 Technologies Used

- Python 3.10
- Jupyter Notebook
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- Joblib
