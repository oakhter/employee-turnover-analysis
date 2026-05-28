# Employee Turnover Prediction - Salifort Motors

## Project Overview

Course capstone project using a simulated HR dataset.

This project analyzes employee survey and workplace data to understand patterns associated with turnover and predict whether an employee is likely to leave. It is intended as a supporting portfolio project that demonstrates an end-to-end analytics and machine learning workflow, from business framing through model evaluation and recommendations.

## Business Problem

Employee turnover can create operational disruption, hiring costs, and knowledge loss. The goal of this analysis is to identify employee characteristics associated with turnover and compare classification models that predict whether an employee left the organization.

The target variable is `left`:

- `0` = employee stayed
- `1` = employee left

## Dataset

The dataset is the HR Capstone dataset from the Google Advanced Data Analytics capstone project. It contains simulated employee survey and workplace variables, including satisfaction score, last evaluation score, project count, average monthly hours, tenure, work accident history, promotion history, department, salary, and turnover status.

## Tools Used

- Python
- pandas and numpy
- matplotlib and seaborn
- scikit-learn
- statsmodels
- XGBoost
- Jupyter Notebook

## Workflow

1. Framed the turnover prediction problem as a binary classification task.
2. Loaded and inspected the HR dataset.
3. Standardized column names for readability.
4. Checked for missing values, duplicates, and outliers.
5. Removed duplicate rows before modeling.
6. Explored turnover patterns across satisfaction, workload, project count, tenure, salary, and department.
7. Built and evaluated Logistic Regression, Decision Tree, Random Forest, and a supplemental XGBoost model.
8. Compared model performance using accuracy, precision, recall, and F1-score.
9. Translated findings into business recommendations and ethical considerations.

## Key EDA Findings

- Lower satisfaction scores were associated with higher turnover.
- Turnover varied by project count, suggesting workload balance may be relevant.
- Employees around 4-6 years of tenure showed notable turnover patterns.
- Salary and promotion history appeared related to turnover patterns.
- Department-level differences existed, but the analysis should be treated as descriptive rather than causal.

## Model Results

| Model | Accuracy | Precision for Leavers | Recall for Leavers | F1 for Leavers |
|---|---:|---:|---:|---:|
| Logistic Regression | 0.83 | 0.49 | 0.21 | 0.29 |
| Decision Tree | 0.98 | 0.96 | 0.93 | 0.94 |
| Random Forest | 0.98 | 0.99 | 0.92 | 0.95 |

Logistic regression had decent accuracy, but weak recall for employees who left. This matters because the business goal is to identify likely leavers, not just predict the majority class.

Decision tree and random forest performed much better on the leaver class. The random forest model had the strongest balance of precision, recall, and F1-score for identifying employees who left.

## Recommended Model

Random Forest is the recommended model from this analysis. It produced high precision for employees who left while maintaining strong recall and F1-score. Accuracy alone is not enough for this problem because a model can perform well overall while missing many employees in the minority class.

## Business Recommendations

- Monitor broader employee groups with low satisfaction scores.
- Review workload balance for employees with unusually high or low project counts.
- Investigate turnover risk patterns around 4-6 years of tenure.
- Review salary and promotion patterns for signs of retention issues.
- Use the model as decision support for HR planning, not as an automated decision-making system.

## Limitations and Ethics

The model should not be used to label individual employees as "flight risks," punish employees, or make automated employment decisions. It should be used to identify broader retention patterns and support HR decision-making.

Important limitations:

- The dataset is simulated and course-provided.
- The model identifies associations, not causation.
- Potentially useful features are missing, such as manager history, compensation changes, engagement comments, team size, and voluntary vs. involuntary turnover.
- Any model would need validation before real-world use.

## Repository Structure

```text
salifort-turnover-prediction/
├── README.md
├── notebooks/
│   └── salifort_turnover_prediction.ipynb
├── data/
│   ├── HR_capstone_dataset.csv
│   └── README.md
├── reports/
│   └── executive_summary.md
├── visuals/
│   └── README.md
├── requirements.txt
└── .gitignore
```

## How to Run

1. Create and activate a Python virtual environment.
2. Install dependencies:

```bash
pip install -r requirements.txt
```

3. Open the notebook:

```bash
jupyter notebook notebooks/salifort_turnover_prediction.ipynb
```

4. Run the notebook cells from top to bottom.
