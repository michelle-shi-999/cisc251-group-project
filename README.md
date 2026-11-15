# Ames Housing Price Prediction
**Project Status: Completed | Kaggle Submission Score: 0.13392 (Top 44%)**

---

## Project Overview
This project focuses on predicting residential home prices in Ames, Iowa, using a dataset containing 79 explanatory variables. Our goal was to move beyond basic regression by implementing a professional machine learning pipeline, sophisticated feature engineering, and hyperparameter optimization.

### Team Members
* Mustafa Al-Youzbaki
* Gabriel Burrows
* Queenie Li
* Michelle Shi

---

## Key Technical Phases

### 1. Data Cleaning & Outlier Strategy
We performed deep exploratory data analysis (EDA) to identify properties that did not follow market trends. We removed houses with more than 4,500 square feet of living space as they acted as extreme outliers. Additionally, we applied a **log-transformation** to the target sale price to normalize the data and ensure the model was penalized based on percentage error rather than absolute dollar amounts.

### 2. Advanced Feature Engineering
Rather than relying solely on raw data, we engineered several domain-specific features to capture the true value of a home:
* **TotalSF:** Combined basement, first floor, and second floor square footage into a single "Total Space" metric.
* **Total Bathrooms:** Aggregated full and half baths from both the basement and upper floors.
* **Property Amenities:** Created simplified boolean indicators for the presence of pools, garages, and fireplaces.
* **Neighborhood Imputation:** Filled missing "Lot Frontage" values using the median of the specific neighborhood rather than a global average.

### 3. Machine Learning Pipeline
We built a robust Scikit-Learn pipeline to automate the preprocessing of data. This included:
* **Numerical Data:** Median imputation and Standard Scaling.
* **Categorical Data:** Constant imputation and One-Hot Encoding for over 40 categorical variables.
* **Model Selection:** We compared **Ridge Regression**, **Gradient Boosting**, and **K-Nearest Neighbors**.

---

## Final Model & Performance
The final selected model was a **Tuned Ridge Regression**. By using `GridSearchCV`, we identified the optimal regularization strength ($\alpha \approx 14.4$) to balance the bias-variance trade-off.



| Metric | Result |
| :--- | :--- |
| **Cross-Validated RMSE** | 0.1147 |
| **Kaggle RMSLE** | 0.13392 |
| **Global Rank** | 2345 / 5428 |

### Diagnostic Analysis
Our residual plots showed that errors were randomly distributed around zero, confirming that our log-transformation successfully corrected for heteroscedasticity (the tendency for errors to grow larger as house prices increase).



---

## Tools Used
* **Python:** Core programming language.
* **Pandas & NumPy:** Data manipulation and numerical operations.
* **Scikit-Learn:** Pipeline construction, scaling, and machine learning algorithms.
* **Matplotlib & Seaborn:** Statistical visualizations and diagnostic plotting.

---

## How to Run
1. Clone the repository.
2. Ensure you have `train.csv` and `test.csv` in the root folder.
3. Install dependencies:
- pip install pandas numpy seaborn matplotlib scikit-learn
4. Run the Jupyter Notebook: Deliverable_3_Final.ipynb
