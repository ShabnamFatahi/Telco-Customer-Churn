# Telco Customer Churn Prediction
## Project Overview
This project focuses on predicting customer churn using machine learning techniques. Customer churn refers to cus
tomers who discontinue their services. The goal of this project is to identify customers who are likely to churn
and understand the factors associated with customer churn.
The project covers the complete machine learning workflow, including data cleaning, exploratory data analysis, pr
eprocessing, model training, model comparison, evaluation, and churn probability prediction.
## Dataset
The dataset contains information about telecommunications customers, including:
- Customer demographics
- Services subscribed to
- Contract information
- Payment methods
- Monthly charges
- Total charges
- Customer tenure
- Churn status
The target variable is `Churn`, which indicates whether a customer left the company.
- `No` → Customer did not churn
- `Yes` → Customer churned
## Exploratory Data Analysis
Several analyses were performed to understand the relationships between customer characteristics and churn. Key o
bservations included:
- Customers with shorter tenure were more likely to churn.
- Month-to-month contract customers showed a higher churn rate.
- Monthly charges were generally higher among churned customers.
- Churn rates varied across different internet service types.
- Payment method was also associated with differences in churn rates.
- Correlation analysis showed a strong relationship between `tenure` and `TotalCharges`.
## Data Cleaning
The dataset required several preprocessing steps before modeling. The `TotalCharges` column contained blank value
s stored as strings. These values were converted to numeric values, and the missing values were replaced with 0.
The `customerID` column was removed because it does not provide useful predictive information.
The target variable was encoded as:
- `No` → `0`
- `Yes` → `1`
## Data Preprocessing
The data was divided into training and testing sets using an 80/20 split. Stratified sampling was used to preserv
e the churn distribution in both datasets.
Categorical features were encoded using One-Hot Encoding, while numerical features were standardized using `Stand
ardScaler`. A `ColumnTransformer` was used to apply the appropriate preprocessing steps to each feature type.
## Machine Learning Models
Four classification models were trained and evaluated:
1. Logistic Regression
2. Decision Tree
3. Random Forest
4. Gradient Boosting
Each model was implemented using a Scikit-learn Pipeline that combined preprocessing and model training.
## Model Evaluation
The models were evaluated using:
- Accuracy
- Precision
- Recall
- F1-score
- ROC-AUC
### Model Performance
| Model | Accuracy | Precision | Recall | F1-score | ROC-AUC |
|---|---:|---:|---:|---:|---:|
| Logistic Regression | 0.796 | 0.643 | 0.524 | 0.577 | 0.845 |
| Gradient Boosting | 0.800 | 0.655 | 0.519 | 0.579 | 0.841 |
| Random Forest | 0.797 | 0.647 | 0.519 | 0.576 | 0.818 |
| Decision Tree | 0.734 | 0.499 | 0.505 | 0.502 | 0.663 |
Logistic Regression achieved the highest ROC-AUC score of 0.845, indicating the strongest overall ability to dist
inguish between churn and non-churn customers.
Gradient Boosting achieved the highest Accuracy, Precision, and F1-score among the evaluated models.
## ROC Curve
ROC curves were used to compare the classification performance of the models across different probability thresho
lds.
Logistic Regression achieved the highest ROC-AUC score of 0.845.
## Confusion Matrix
A confusion matrix was used to examine the classification results of the Gradient Boosting model. The model corre
ctly identified both churn and non-churn customers, while also showing some false positive and false negative pre
dictions.
## Feature Importance
Logistic Regression coefficients were analyzed to identify the features most strongly associated with customer ch
urn.
The most influential features included:
- `tenure`
- `Contract`
- `TotalCharges`
- `InternetService`
- `PhoneService`
- `TechSupport`
- `PaperlessBilling`
- `OnlineSecurity`
In general, shorter customer tenure and month-to-month contracts were associated with a higher likelihood of chur
n.
## Churn Probability Prediction
The Gradient Boosting model was also used to generate churn probabilities for customers in the test set. This all
ows customers to be ranked according to their predicted likelihood of leaving the company.
Such predictions can be useful for identifying high-risk customers and supporting customer retention strategies.
## Key Findings
The analysis suggests that customer churn is strongly associated with customer tenure and contract type. Customer
s with shorter relationships with the company and month-to-month contracts showed a higher likelihood of churn.
Machine learning models can therefore be used not only to classify churn, but also to estimate individual custome
r churn risk.
## Technologies Used
- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- Jupyter Notebook
## Project Structure
```text
Telco-Customer-Churn/
├── TelcoCustomerChurn.ipynb
├── README.md
└── data/
└── WA_Fn-UseC_-Telco-Customer-Churn.csv
```
## Conclusion
This project demonstrates an end-to-end machine learning workflow for customer churn prediction. The analysis inc
luded data cleaning, exploratory data analysis, feature preprocessing, model training, model comparison, ROC anal
ysis, and churn probability prediction.
Among the evaluated models, Logistic Regression achieved the highest ROC-AUC of 0.845, while Gradient Boosting ac
hieved the highest Accuracy, Precision, and F1-score.