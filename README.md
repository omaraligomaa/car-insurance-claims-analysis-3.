# Car Insurance Claims Analysis

Exploratory data analysis and preprocessing of car insurance customer records, focusing on how demographic and driving-related attributes relate to the dataset's binary `OUTCOME` label.

**Python · Pandas · NumPy · Matplotlib · Seaborn · Scikit-learn**

## Project Overview

This project examines **10,000 records and 19 columns**. The notebook explores differences in the binary outcome across age, gender, income, driving experience, and marital status. It also covers missing-value treatment, outlier handling, categorical encoding, train/test splitting, and feature scaling.

**Scope:** Exploratory data analysis and preprocessing. The notebook does **not** train or evaluate a prediction model, so no accuracy or performance claims are made.

## Business & Analysis Questions

- How does the mean binary outcome vary across age groups?
- What differences are observed by gender and income?
- How does driving experience relate to the outcome?
- What patterns appear across marital-status groups?
- How is the dataset prepared for potential machine learning?

## Exploratory Data Analysis

The five figures below are extracted from the notebook's saved outputs. The bar charts show the **mean binary `OUTCOME`** within each group, not the number of claims. They show associations, not causal effects.

### Age vs. Outcome

![Mean outcome by age group](images/01-age-vs-outcome.png)

*Mean outcome across the notebook's age categories.*

### Gender vs. Outcome

![Mean outcome by gender](images/02-gender-vs-outcome.png)

*Mean outcome by gender.*

### Income vs. Outcome

![Mean outcome by income group](images/03-income-vs-outcome.png)

*Mean outcome across income categories.*

### Driving Experience vs. Outcome

![Mean outcome by driving experience](images/04-driving-experience-vs-outcome.png)

*Mean outcome across driving-experience groups.*

### Marital Status vs. Outcome

![Mean outcome by marital status](images/05-marital-status-vs-outcome.png)

*Mean outcome by the `MARRIED` indicator.*

> **Image status:** The image files will display after the corresponding PNGs are uploaded to the `images/` folder.

## Data Preparation Workflow

1. **Inspect data:** Explore dataset shape, column types, descriptive statistics, and missing values.
2. **Handle missing values:** Impute `CREDIT_SCORE` and `ANNUAL_MILEAGE` using their medians.
3. **Treat outliers:** Detect outliers with `datasist` and replace flagged numerical values with medians, as implemented in the notebook.
4. **Prepare features:** Separate the target `OUTCOME` from predictors.
5. **Encode categories:** Apply `pd.get_dummies(..., drop_first=True)`.
6. **Split data:** Create training and test subsets.
7. **Scale features:** Fit `StandardScaler` on the training set and transform both subsets.

**Methodology note:** This README describes the notebook as written, without changing the original analysis. Imputation and outlier treatment occur before splitting, which should be revisited before a leakage-safe predictive experiment.

## Dataset

| Attribute | Value |
| --- | --- |
| Records | 10,000 |
| Columns | 19 |
| Target | `OUTCOME` (0/1) |
| Missing `CREDIT_SCORE` | 982 |
| Missing `ANNUAL_MILEAGE` | 957 |

Example features: `AGE`, `GENDER`, `INCOME`, `DRIVING_EXPERIENCE`, `MARRIED`, `SPEEDING_VIOLATIONS`, `DUIS`, and `PAST_ACCIDENTS`.

## Project Structure

```text
car-insurance-claims-analysis/
├── README.md
├── data/
│   └── Car_Insurance_Claim.csv
├── images/
│   ├── 01-age-vs-outcome.png
│   ├── 02-gender-vs-outcome.png
│   ├── 03-income-vs-outcome.png
│   ├── 04-driving-experience-vs-outcome.png
│   └── 05-marital-status-vs-outcome.png
└── notebooks/
    └── car_insurance.ipynb
```

## Tools & Technologies

- **Python, Pandas, NumPy:** Data inspection and preparation
- **Seaborn, Matplotlib:** Exploratory visualization
- **datasist:** Outlier detection
- **Scikit-learn:** Data splitting and scaling
- **Jupyter Notebook:** Interactive analysis

## Reproducibility Notes

The notebook loads its CSV from the original Google Colab path `/content/Car_Insurance_Claim.csv` and installs `datasist` in a cell. To run it in a different environment, update the dataset path. The visualizations and observations above reflect saved notebook outputs; the analysis has not been independently rerun.

## Author

**Omar Ali**  
Data Engineering · Analytics Engineering

[LinkedIn](https://www.linkedin.com/in/eng-omargomaa) · [GitHub](https://github.com/omaraligomaa)
