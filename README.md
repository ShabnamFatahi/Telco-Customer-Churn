# Telco Customer Churn Prediction

## Project Overview

This project uses machine learning to predict customer churn. In this context, churn refers to a customer stopping their use of the company's services.

The main goal is to identify customers who are more likely to churn and explore the factors associated with customer churn.

The project follows an end-to-end machine learning workflow, including data cleaning, exploratory data analysis, data preprocessing, model training, model evaluation, and churn probability prediction.

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

`Churn` is the target variable and indicates whether a customer has left the company.

- `No` → Customer did not churn
- `Yes` → Customer churned

## Exploratory Data Analysis

Several analyses were carried out to better understand the relationship between customer characteristics and churn.

Key observations included:

- Customers who had been with the company for a shorter period were more likely to churn.
- Customers with month-to-month contracts had higher churn rates.
- Customers who churned generally had higher monthly charges.
- Churn rates differed across different types of internet service.
- Churn rates also varied depending on the payment method.
- The correlation analysis showed a strong relationship between tenure and `TotalCharges`.

## Data Cleaning

The dataset was cleaned and prepared for analysis before training the models.

The values in the `TotalCharges` column, which were initially stored as strings, were converted to numeric values.

The `customerID` column was removed because it does not provide useful predictive information.

The target variable was encoded as:

- `No` → `0`
- `Yes` → `1`

## Data Preprocessing

The data was divided into training and testing sets using an 80/20 split, with stratified sampling to maintain the original churn distribution.

Categorical features were encoded using One-Hot Encoding, while numerical features were standardized using `StandardScaler`.

A `ColumnTransformer` was used to apply the appropriate preprocessing steps to each type of feature.

## Machine Learning Models

Four classification models were trained and evaluated:

1. Logistic Regression
2. Decision Tree
3. Random Forest
4. Gradient Boosting

Each model was implemented using a Scikit-learn Pipeline that combined the preprocessing steps with model training.

## Model Evaluation

The models were evaluated using the following metrics:

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

Logistic Regression achieved the highest ROC-AUC score of 0.845, indicating the strongest overall ability to distinguish between customers who churned and those who did not.

Gradient Boosting achieved the highest Accuracy, Precision, and F1-score among the evaluated models.

## ROC Curve

The ROC curves were used to compare the classification performance of the different models across various probability thresholds.

Logistic Regression achieved the highest ROC-AUC score, with a value of 0.845.

## Confusion Matrix

The classification results of the Gradient Boosting model were further analyzed using a confusion matrix.

The confusion matrix shows the model's correct predictions as well as its false positive and false negative predictions.

## Feature Importance

The coefficients of the Logistic Regression model were analyzed to identify the features most strongly associated with customer churn.

The most influential features included:

- `tenure`
- `Contract`
- `TotalCharges`
- `InternetService`
- `PhoneService`
- `TechSupport`
- `PaperlessBilling`
- `OnlineSecurity`

In general, customers who had been with the company for a shorter period and those on month-to-month contracts were more likely to churn.

## Churn Probability Prediction

The Gradient Boosting model was used to calculate churn probabilities for customers in the test set.

These probabilities allow customers to be ranked according to their predicted likelihood of leaving the company. This can be useful for identifying high-risk customers and supporting customer retention strategies.

## Key Findings

The analysis indicates that customer churn is strongly related to both customer tenure and contract type.

Customers who had shorter relationships with the company and those on month-to-month contracts were more likely to churn.

The models can be used not only to classify churn, but also to estimate the individual churn risk of customers.

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

This project demonstrates a complete machine learning workflow for customer churn prediction, covering data cleaning, exploratory data analysis, feature preprocessing, model training, model comparison, ROC analysis, and churn probability prediction.

Among the evaluated models, Logistic Regression achieved the highest ROC-AUC score of 0.845, while Gradient Boosting achieved the highest Accuracy, Precision, and F1-score.
