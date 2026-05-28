# Executive Summary: Employee Turnover Prediction

## Business Problem

This course capstone project uses a simulated HR dataset to analyze employee turnover patterns and predict whether an employee left the organization.

## Approach

The analysis cleaned and inspected the dataset, standardized column names, removed duplicate rows, explored turnover patterns, and compared classification models. The target variable was `left`, where `1` indicates an employee left and `0` indicates an employee stayed.

## Key Findings

- Lower satisfaction scores were associated with higher turnover.
- Turnover patterns varied by project count, tenure, salary, and promotion history.
- Employees around 4-6 years of tenure showed notable turnover patterns.
- These findings are associations and should not be interpreted as proof of causation.

## Model Results

| Model | Accuracy | Precision for Leavers | Recall for Leavers | F1 for Leavers |
|---|---:|---:|---:|---:|
| Logistic Regression | 0.83 | 0.49 | 0.21 | 0.29 |
| Decision Tree | 0.98 | 0.96 | 0.93 | 0.94 |
| Random Forest | 0.98 | 0.99 | 0.92 | 0.95 |

## Recommendation

Random Forest is the recommended model because it had the strongest balance of precision, recall, and F1-score for identifying employees who left.

## Next Steps

- Review satisfaction, workload, tenure, salary, and promotion patterns at the group level.
- Validate the model on newer or external data before any real-world use.
- Add richer HR context, such as manager history, compensation changes, team size, engagement comments, and voluntary vs. involuntary turnover.

## Ethical Considerations

The model should not be used to label individual employees as "flight risks," punish employees, or make automated employment decisions. It should support broader retention analysis and HR planning.
