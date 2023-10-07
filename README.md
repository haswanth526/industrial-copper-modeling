
## **Approach**

1) Data Understanding: - Recognise the different categories of variables (continuous, categorical), as well as their distributions. 'Material_Reference' contains some useless values, the first of which should be changed to null and starts with the value '00000'. Reference columns should be treated as categorical variables. The INDEX might not be helpful.

2) Data Preprocessing: Use the mean, median, and mode to handle missing numbers.
  - Handle outliers by using the Sklearn library's IQR or Isolation Forest.
  To handle high skewness in continuous variables, identify any skewness in the dataset and treat it with the appropriate data transformations, such as the log transformation (which is best suited to transform the target variable-train, predict, and then reverse transform it back to original scale, e.g., dollars), boxcox transformation, or other techniques.
  - Depending on the nature of the categorical variables, encode them using the appropriate approaches, such as one-hot encoding, label encoding.

**3) EDA:**
 - Try using Seaborn's boxplot, distplot, and violinplot to visualise outliers and skewness (both before and after treating skewness).

**4) Feature Engineering:** - Create new features, if necessary, by combining or altering current features to provide data visualisations that are more useful. and using SNS HEATMAP to remove strongly linked columns.

**5) Model Development and Assessment:**

- Divide the dataset into testing/validation and training sets.

- Use appropriate assessment metrics, such as accuracy, precision, recall, F1 score, and AUC curve, to train and assess various classification models, such as ExtraTreesClassifier, XGBClassifier, or Logistic Regression.

- To select the model with the highest performance, optimise model hyperparameters using methods like grid search and cross-validation.

- Interpret the model's output and evaluate its effectiveness in light of the specified problem statement.

- Same steps for Regression modelling.(note: dataset contains more noise
and linearity between independent variables so itll perform well only with
tree based models)

**6) Model GUI:** 

- Using streamlit module, create interactive page with
    - (1) task input( Regression or Classification) and
    - (2) create an input field where you can enter each column value except
‘Selling_Price’ for regression model and except ‘Status’ for classification
model.

    - (3) perform the same feature engineering, scaling factors, log/any
transformation steps which you used for training ml model and predict this new
data from streamlit and display the output.

