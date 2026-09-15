# Telco Customer Churn Prediction
## Project Overview
The project involves the use of machine learning in order to predict customer churn; in this case, churn refers to a customer stopping use of the company. The primary aim is to identify the customers who are more likely to churn and to investigate the factors that are related to customer churn.
The project follows an end-to-end machine learning workflow, including data cleaning, exploratory data analysis, data preprocessin## Dataset
The dataset contains information about telecommunications customers, including:
- Customer demographics
- Services subscribed to
- Contract information
- Payment methods
- Monthly charges
- Total charges
- Customer tenure
- Churn status
`Churn` is the variable in question and it shows if a customer has left the company.
- `No` → Customer did not churn
- `Yes` → Customer churned
## Exploratory Data Analysis
A number of analyses were carried out in order to gain a better understanding of the relationship between customer characteristics and churn.
Key observations included:
Customers who had been with the company for a shorter time were more likely to leave.
- The rate of customers who had month-to-month contracts was higher.
Customers who had their accounts churned usually had higher monthly charges.
– The churn rates were different for various types of internet service.
- The churn rates varied as well according to the method of payment.
The correlation analysis revealed a strong relationship between tenure and TotalCharges.
## Data Cleaning
The dataset was cleaned and prepared for analysis before the models were trained.
The values in the `TotalCharges` column, which were stored as strings, were converted into numeric values and the `customerID` column was deleted since it does not contain any useful predictive information.
The target variable was encoded as:
- `No` → `0`
- `Yes` → `1`
## Data Preprocessing
The data was divided into training and testing sets in an 80/20 ratio, with stratified sampling employed in order to maintain the churn distribution. The categorical features were encoded by using One-Hot Encoding and the numerical features were standardized by means of `StandardScaler`.
A ColumnTransformer was employed in order to carry out the suitable preprocessing steps on each type of feature.
## Machine Learning Models
Four classification models were trained and evaluated:
1. Logistic Regression
2. Decision Tree
3. Random Forest
4. Gradient Boosting
Each model was implemented with the use of a Scikit-learn Pipeline which combined the preprocessing and the model training.
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
0.734 | 0.499 | 0.505 | 0.502 | 0.663
Logistic Regression obtained an ROC-AUC score of 0.845, which indicates that it had the greatest overall capacity to distinguish between the two classes, while CustGradient Boosting achieved the highest values for Accuracy, Precision, and F1-score among the models that were evaluated.
## ROC Curve
The ROC curves were employed in order to compare the classification performance of the various models at different probability thresholds.
Logistic Regression had the highest ROC-AUC score, which was 0.845.
## Confusion Matrix
The classification results of the Gradient Boosting model were analysed using a confusion matrix.
The model's correct predictions as well as those which are false positives and false negatives are shown in the confusion matrix.
## Feature Importance
An analysis of the Logistic Regression coefficients was carried out in order to find the features most strongly linked with customer churn.
The most influential features included:
- `tenure`
- `Contract`
- `TotalCharges`
- `InternetService`
- `PhoneService`
- `TechSupport`
- `PaperlessBilling`
- `OnlineSecurity`
In general, customers who had been with the company for a shorter time and those on month-to-month contracts were more likely to churn.
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
The project shows a complete The project shows  machine learning workflow for customer churn prediction, including data cleaning, exploratory data analysis, feature preprocessing, model training, model comparison, ROC analysis, and churn probability prediction.

Of the models examined, Logistic Regression obtained the highest ROC-AUC at 0.845, whereas Gradient Boosting achieved the greatest Accuracy, Precision, and F1-score.
