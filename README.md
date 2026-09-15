# Telco Customer Churn Prediction
## Project Overview
The aim of this project is to use machine learning methods to predict customer churn, churn referring to customers who
The aim of this project is to find customers who are likely to stop using their services.
and understand the reasons linked to customers leaving.
The project covers the complete machine learning workflow, including data cleaning, exploratory data analysis, pr
The processing, the training of the models, the comparison of the models, the evaluation and the prediction of churn probability.
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
The variable in question is `Churn`, and it shows whether or not a customer has left the company.
- `No` → Customer did not churn
- `Yes` → Customer churned
## Exploratory Data Analysis
A number of analyses were carried out in order to understand the relationships between customer characteristics and churn. Key observations included:
Customers who had been with the company for a shorter time were more likely to cancel their accounts.
Customers with month-to-month contracts had a greater churn rate.
- Customers who churned usually had higher monthly charges.
- The churn rates were different for various types of internet service.
The method of payment was also linked to differences in churn rates.
- The correlation analysis revealed a strong relationship between tenure and TotalCharges.
## Data Cleaning
Before modelling, the dataset needed a number of preprocessing steps, and the `TotalCharges` column had blank values.
They are stored in the form of strings; the values were transformed into numeric values and the missing values were substituted with zero.
The column named customerID was deleted since it does not contain any useful predictive information.
The target variable was encoded as:
- `No` → `0`
- `Yes` → `1`
## Data Preprocessing
The data was split into training and testing sets in an 80/20 ratio, and stratified sampling was employed to preserve
Look at the churn distribution in both datasets.
Categorical features were encoded using One-Hot Encoding, while numerical features were standardized using `Stand
We used a ColumnTransformer to carry out the suitable preprocessing steps for each type of feature.
## Machine Learning Models
Four classification models were trained and evaluated:
1. Logistic Regression
2. Decision Tree
3. Random Forest
4. Gradient Boosting
Each model was implemented with the use of a Scikit-learn Pipeline which combined the preprocessing and the model training.
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
0.734  |  0.499  |  0.505  |  0.502  |  0.663  |
Logistic Regression obtained an ROC-AUC score of 0.845, which shows that it had the greatest overall ability to dist
Distinguish between churning and non-churning customers.
Gradient Boosting was the model that obtained the highest values for Accuracy, Precision, and F1-score.
## ROC Curve
ROC curves were used to compare the classification performance of the models across different probability thresholds.
Logistic Regression had the highest ROC-AUC score, which was 0.845.
## Confusion Matrix
A confusion matrix was applied in order to examine the classification results of the Gradient Boosting model. The model correctly identified both churn and non-churn customers, while also showing some false positive and false negative pre
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
The Gradient Boosting model was employed as well in order to calculate the churn probabilities for the customers in the test set. That's all.
Allows customers to be ranked based on the likelihood that they have been predicted to leave the company.
They can be of use in identifying high-risk customers and in helping to develop customer retention strategies.
## Key Findings
The analysis indicates that there is a strong association between customer churn and both the length of customer tenure and the type of contract. Customer
Those with shorter associations with the company and those on month-to-month contracts were more likely to churn.
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
This project provides a complete machine learning workflow for predicting customer churn. The analysis included data cleaning, exploratory data analysis, feature preprocessing, model training, model comparison, ROC anal
Analysis and the prediction of churn probability.
Of the models examined, Logistic Regression obtained the highest ROC-AUC value of 0.845, whereas Gradient Boosting did so as well.
Achieved the highest values for Accuracy, Precision, and F1-score.
