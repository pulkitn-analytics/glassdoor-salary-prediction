# 📊 Glassdoor Salary Analysis and Prediction

A data analysis and machine learning project exploring salary patterns in Glassdoor job listings and building regression models to estimate job salary midpoints.

## 📌 Project Overview

The objective of this project is to analyse Glassdoor job listings, identify patterns associated with salary estimates, and compare regression models for predicting the average salary midpoint of a job listing.

The project covers data cleaning, exploratory data analysis (EDA), feature engineering, hypothesis testing, preprocessing, model training, and evaluation. The findings describe salary estimates in the available listings and should not be interpreted as verified salaries actually paid to employees.

## 🎯 Objectives

- Analyse salary distributions and identify patterns in job listings.
- Explore salary estimates across job titles, seniority levels, locations, and company characteristics.
- Clean and transform raw data for analysis and modelling.
- Engineer features from job titles, company information, and skills mentioned in job descriptions.
- Use hypothesis testing to examine differences in mean salary estimates across groups.
- Train and compare regression models using appropriate evaluation metrics.

## 🗂️ Dataset

The project uses Glassdoor job-listing data containing information such as:

- Job titles and salary estimates
- Company ratings and company size
- Locations and industry details
- Company founding years
- Job descriptions and other employer attributes

The target variable, `avg_salary`, is calculated as the midpoint of the minimum and maximum values extracted from the listed salary range.

**Note:** The target represents an estimated salary midpoint derived from the listing, not a verified employee salary.

## 🛠️ Tools and Technologies

- **Python** — core programming language
- **Pandas and NumPy** — data manipulation and numerical operations
- **Matplotlib and Seaborn** — data visualization
- **Scikit-learn** — preprocessing, regression models, and evaluation
- **Jupyter Notebook / Google Colab** — development and analysis
- **Git and GitHub** — version control and project hosting

## 🔍 Project Workflow

### 1. Data Cleaning and Wrangling

- Inspected the dataset structure, data types, missing values, and duplicates.
- Processed salary ranges and calculated salary midpoint estimates.
- Excluded salary entries outside the scope of the analysis.
- Extracted seniority and location information.
- Derived company age from the founding year.
- Created binary indicators for selected skills mentioned in job descriptions.
- Removed columns not required for the analysis or modelling.

### 2. Exploratory Data Analysis (EDA)

Explored the data using descriptive statistics and visualizations, including:

- Salary distribution and spread
- Salary estimates across seniority levels
- Salary estimates across company-size categories
- Relationships among numerical variables
- Correlations and potential patterns in the dataset

The visualizations help identify patterns and guide further analysis; they do not establish causation.

### 3. Hypothesis Testing

ANOVA tests are used to examine whether mean salary estimates differ across:

- Seniority categories
- Company-size categories

The conclusions are based on the calculated p-values at a 5% significance level. A statistically significant result indicates evidence of a difference in at least one group mean, but does not establish a causal relationship.

### 4. Feature Engineering and Preprocessing

- Created candidate predictors from job and company attributes.
- Excluded the target and salary components used to calculate it from the input features.
- Handled missing categorical and numerical values.
- Applied one-hot encoding to categorical variables.
- Standardized input features using `StandardScaler`, fitted on the training data only.
- Split the data into training and testing sets for model evaluation.

### 5. Model Building

The project compares the following regression approaches:

- **Linear Regression** — a baseline model for estimating relationships between input features and salary.
- **Gradient Boosting Regressor** — an ensemble model that builds trees sequentially to improve predictions.
- **Random Forest Regressor** — an ensemble model that combines predictions from multiple decision trees.
- **Tuned Random Forest Regressor** — a Random Forest model with hyperparameters selected through cross-validation.

### 6. Model Evaluation

Models are evaluated using the following metrics:

| Metric | Purpose | Preferred result |
|---|---|---|
| MAE | Average absolute prediction error | Lower |
| RMSE | Penalizes larger prediction errors more heavily | Lower |
| R² | Measures the proportion of target variation explained by the model | Higher |

The final model should be selected after comparing the test-set results. Hyperparameter tuning does not guarantee better performance, and the best model should not be assumed in advance.

## 📈 Results and Findings

The notebook contains the analysis, visualizations, statistical tests, and model evaluation workflow.

The final model and its performance should be reported using the actual results produced when the notebook is executed. No model is declared the winner in this README without verified evaluation results.

## 📁 Repository Structure

```text
glassdoor-salary-prediction/
│
├── AB_capstone06_glassdoor_salary_pred.ipynb
├── glassdoor_jobs.csv
└── README.md
```

- `AB_capstone06_glassdoor_salary_pred.ipynb` — notebook containing the analysis, feature engineering, hypothesis testing, and regression modelling.
- `glassdoor_jobs.csv` — dataset used for the project, subject to applicable redistribution permissions.
- `README.md` — project documentation and instructions.

## 🚀 How to Run the Project

1. Clone or download this repository.
2. Open the notebook in Google Colab or Jupyter Notebook.
3. Upload `glassdoor_jobs.csv` if it is not available in the notebook environment.
4. Confirm that the dataset path in the notebook matches its actual location.
5. Run the notebook cells in order.
6. Review the visualizations, ANOVA p-values, model-comparison table, and final prediction output.

### Install Dependencies

If running locally, install the main libraries using:

```bash
pip install pandas numpy matplotlib seaborn scikit-learn jupyter
```

## ⚠️ Limitations

- Salary estimates are derived from listed salary ranges and may not represent actual compensation.
- The dataset may contain outdated listings, incomplete information, and other sources of bias.
- Feature relationships and statistical associations do not establish causation.
- Model performance depends on the dataset, preprocessing choices, and evaluation procedure.
- Results on a held-out test set do not guarantee similar performance on future job listings.
- Further validation on newer and independent data would help assess generalizability.

## 🔮 Future Improvements

- Validate the selected model on newer job listings.
- Explore more robust methods for processing salary ranges and missing data.
- Investigate text-based features from job descriptions.
- Assess feature importance using appropriate model-based or permutation methods.
- Compare performance across relevant job and location groups.
- Improve model selection and document the verified evaluation results.

## 👤 Author

**Pulkit Narang**

- **GitHub:** [pulkitn-analytics](https://github.com/pulkitn-analytics)

---

*This project was developed as part of a data science learning portfolio to practise data cleaning, exploratory analysis, statistical testing, feature engineering, and regression modelling.*
