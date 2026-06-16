# Employee Attrition Prediction — Google Data Analytics Capstone

## Overview
This project builds a machine learning pipeline to predict employee attrition using HR data. Two classification models were trained and compared — Logistic Regression and Random Forest — with the goal of identifying the key drivers of employee turnover and providing actionable business recommendations.

The project was completed as the capstone for the Google Data Analytics Certificate. The final model was containerized with Docker and deployed to an AWS EC2 instance.

## Tools & Technologies
- **Python** (pandas, numpy, scikit-learn, matplotlib) – Data cleaning, modeling, and visualization
- **Jupyter Notebook** – Analysis and documentation
- **Docker** – Model containerization
- **AWS EC2** – Cloud deployment

## Dataset
HR employee dataset containing 14,999 records with the following features:

| Feature | Description |
|---|---|
| `satisfaction_level` | Employee satisfaction score (0–1) |
| `last_evaluation` | Most recent performance evaluation score |
| `num_projects` | Number of projects assigned |
| `avg_monthly_hours` | Average hours worked per month |
| `tenure` | Years spent at the company |
| `work_accident` | Whether the employee had a workplace accident |
| `salary_level` | Salary band (low / medium / high) |
| `attrition` | Target variable — whether the employee left (1) or stayed (0) |

## Project Workflow

### 1. Data Cleaning
- Standardized and renamed columns for consistency
- Removed duplicate rows
- Capped outliers at the 99th percentile
- Encoded salary level ordinally (low=0, medium=1, high=2)

### 2. Modeling
Two models were trained and evaluated on a held-out test set:

| Model | Accuracy | Attrition Precision | Attrition Recall | Attrition F1 |
|---|---|---|---|---|
| Logistic Regression | 78.3% | 42.2% | 84.2% | 56.3% |
| **Random Forest** | **98.4%** | **98.1%** | **92.2%** | **95.1%** |

The Random Forest model significantly outperformed Logistic Regression across all metrics and was selected as the final model.

## Key Findings
**Top drivers of attrition (combined from both models):**
- Satisfaction level
- Tenure
- Number of projects
- Work accidents
- Salary level
- Average monthly hours
- Last evaluation score

## Business Recommendations
Based on the model's top drivers, the following actions are recommended:

1. Run monthly pulse surveys and trigger manager follow-ups for low satisfaction scores, prioritizing teams with repeated low signals
2. Set workload guardrails (monthly hours thresholds) and monitor overtime; rebalance staffing for consistently over-capacity teams
3. Cap concurrent projects per employee and formalize resource planning to prevent chronic overload
4. Add mid-tenure (years 2–4) career paths including mentorship, internal mobility, and milestone-based growth plans
5. Review compensation bands vs. market and address pay compression, targeting high-risk roles and critical teams

## Files
| File | Description |
|---|---|
| `cleaned_google_project.ipynb` | Full analysis and modeling notebook |
| `data/HR_comma_sep.csv` | HR employee dataset |

## Certificate
Google Data Analytics Professional Certificate — Coursera
