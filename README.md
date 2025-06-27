🎓 Predicting Student Satisfaction with ChatGPT

This project uses machine learning to predict students' satisfaction with ChatGPT based on behavioral, perceptual, and demographic data collected through a global higher education survey.

📌 Overview

ChatGPT has rapidly become a tool of interest in academic environments. This project investigates:

- How students interact with ChatGPT
- What factors drive their satisfaction
- Whether we can predict satisfaction using ML

Using a dataset of **23,000+ responses**, we build and compare **regression** and **classification** models, validating performance using cross-validation.

🔍 Dataset

- **Source**: ChatGPT in Higher Education – Global Student Survey (Open Dataset)
- **Size**: ~23,000 records
- **Features**: 
  - Demographics (e.g., country, field of study)
  - Usage behavior (e.g., frequency, purpose)
  - Perceived learning impact
- **Targets**:
  - `satisfaction_score` (regression target; normalized)
  - `satisfaction_level` (classification target: Low, Medium, High)

🛠️ Tech Stack

- Python (Pandas, NumPy)
- Scikit-learn
- Seaborn, Matplotlib (for EDA & visualizations)
- Jupyter Notebook

⚙️ Machine Learning Models

| Task           | Model                    |
|----------------|---------------------------|
| Regression     | Linear Regression, Random Forest Regressor |
| Classification | Logistic Regression, Random Forest Classifier |

All models are wrapped in scikit-learn pipelines including:
- Mean imputation (`SimpleImputer`)
- Min-max scaling
- 5-fold cross-validation (`KFold` and `StratifiedKFold`)

📈 Results Summary

🔹 Regression

| Model                  | MAE        | R² Score   | CV MAE     | CV R²     |
|------------------------|------------|------------|------------|-----------|
| Linear Regression      | 3.56e-16   | 1.000      | 3.43e-16   | 1.000     |
| Random Forest Regressor| 0.00032    | 0.9996     | 0.00045    | 0.9993    |

🔹 Classification

| Model                  | Accuracy   | Macro F1   | CV Accuracy| CV F1     |
|------------------------|------------|------------|------------|-----------|
| Logistic Regression    | 1.000      | 1.000      | 0.998      | 0.997     |
| Random Forest Classifier| 0.970     | 0.950      | 0.976      | 0.956     |

🔍 Feature Importance (Top Factors)

- Use of ChatGPT for assignments (Q18a)
- Perceived improvement in learning (Q26e)
- Country
- Field of Study
- Frequency of use (Q35c)
