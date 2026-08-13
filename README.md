# Bank-Marketing-Subscription-Prediction-Model

**Project Overview**
*This project aimed to develop a machine learning model capable of predicting whether a customer would subscribe to a term deposit product offered by a bank. The dataset used for this project contains customer demographic information, campaign-related variables, and historical marketing interaction records collected from previous direct marketing campaigns.*

The primary objective was to help the bank identify customers who are more likely to subscribe to a term deposit, thereby enabling more targeted marketing efforts, reducing campaign costs, and improving conversion rates.

Since the target variable (y) consists of two classes (yes and no), the problem was treated as a binary classification task.

# Data Understanding and Exploration

The first phase of the project involved understanding the structure, quality, and characteristics of the dataset.

**Key activities performed included:**

1. Loading and inspecting the dataset.
2. Examining data types and dataset dimensions.
3. Checking for missing values.
4. Identifying the presence of "unknown" values.
5. Understanding the distribution of numerical and categorical features.
6. Analyzing the target variable distribution.
7. Performing correlation analysis among numerical variables.

**Exploratory Data Analysis (EDA) was conducted to gain insights into customer behavior and understand the factors that may influence deposit subscription decisions.**

*Visualizations such as:*

a. Count plots
b. Histograms
c. Boxplots
d. Correlation heatmaps

were used to identify patterns, trends, and potential outliers within the data.

# Data Preprocessing

Several preprocessing steps were performed to prepare the dataset for machine learning.

a. Handling Missing and Unknown Values
b. The dataset contained categorical entries labeled as "unknown", representing unavailable customer information.

# Actions taken:
a. Quantified the frequency of unknown values.
b. Assessed their impact on model performance.
c. Retained and encoded them as valid categories where appropriate.
d. Encoding Categorical Variables

## Machine learning algorithms require numerical inputs.

## Categorical variables were transformed into numerical representations using:

One-Hot Encoding - This enabled the models to process customer attributes such as:
i. Job
ii. Marital Status
iii. Education
iv. Contact Method
v. Month
vi. and other categorical variables.

Feature Scaling - Feature scaling was applied where necessary, especially for algorithms sensitive to feature magnitude such as Logistic Regression.

Standardization was used to ensure numerical features contributed equally to model training.

Handling Class Imbalance - One of the major challenges encountered during the project was class imbalance.

The target variable distribution was approximately:

- No: 88%
- Yes: 12%

Such imbalance can lead to biased models that predominantly predict the majority class.

To address this challenge, class weights were applied to:

- Logistic Regression
- Decision Tree
- Random Forest

## To penalize misclassification of the minority class, SMOTE (Synthetic Minority Oversampling Technique) was implemented with XGBoost to generate synthetic samples of the minority class and improve class representation within the training data. This approach helped improve the model's ability to identify potential subscribers.

## Model Development

*Multiple classification algorithms were trained and compared to identify the best-performing model.*

The models evaluated included:

1. Logistic Regression - Used as a baseline model because of its simplicity and interpretability.

2. Decision Tree Classifier - Implemented to capture nonlinear relationships and provide decision-making transparency.

3. Random Forest Classifier - An ensemble learning method used to improve predictive performance and reduce overfitting.

4. XGBoost Classifier with SMOTE - A boosting-based ensemble model combined with SMOTE to address class imbalance.

This model was designed to maximize predictive performance while effectively capturing complex patterns in customer behavior.

## Model Evaluation

Several evaluation metrics were used to assess model performance. Since the dataset was imbalanced, accuracy alone was insufficient. The following metrics were considered:
i. Accuracy - Measures overall prediction correctness.
ii. Precision - Measures the proportion of positive predictions that were correct.
iii. Recall - Measures the model's ability to identify actual subscribers.
iv. F1-Score - Provides a balance between precision and recall.
v. ROC-AUC Score - Measures the model's ability to distinguish between customers likely and unlikely to subscribe.
vi. Confusion Matrix was used to analyze:
- True Positives
- True Negatives
- False Positives
- False Negatives

In order to understand prediction errors, model comparison was performed using these metrics to select the best-performing algorithm.

# Hyperparameter Tuning - 
After identifying the best-performing model, hyperparameter tuning was conducted to improve performance further.

# Grid Search Cross Validation (GridSearchCV) or Randomized Search Cross Validation (RandomizedSearchCV) was used to identify optimal parameter combinations.

# Parameters tuned included:
- Number of estimators
- Learning rate
- Maximum tree depth
- Subsampling ratios
- Feature sampling ratios

*The tuned model demonstrated improved predictive capability and generalization performance.*

# Error analysis was carried out to understand the model's misclassifications.

The following were examined:
- False Positives
- False Negatives
- Misclassified observations

This analysis helped identify patterns among incorrectly predicted customers and provided additional insight into areas where model performance could be improved.

Special attention was given to false negatives, as these represent customers who were likely to subscribe but were incorrectly classified as non-subscribers.

*Feature Importance Analysis was conducted on the final model to identify variables with the highest predictive influence. This analysis highlighted customer and campaign-related factors that significantly affect subscription outcomes. The findings provide valuable business insights and help stakeholders understand the primary drivers of customer conversion.*

Model Deployment and Persistence

The trained model can be loaded and used to predict the likelihood of subscription for new customers.

# Business Use Cases

The developed model provides several practical applications for the bank.

# Targeted Marketing Campaigns - 
Identify customers with a high likelihood of subscribing and focus marketing resources on these segments.

# Cost Reduction - 
Reduce unnecessary marketing expenses by avoiding low-probability prospects.

# Improved Customer Conversion - 
Increase campaign success rates through data-driven customer targeting.

# Customer Segmentation - 
Gain a better understanding of customer behavior and preferences.

# Decision Support - 
Provide marketing teams with predictive insights that support strategic planning and campaign optimization.

# Revenue Growth - Improve term deposit subscription rates and enhance overall business profitability.

# Conclusion
This project successfully developed and evaluated multiple machine learning models to predict customer subscription behavior. Through extensive exploratory data analysis, preprocessing, class imbalance handling, model comparison, hyperparameter tuning, and error analysis, an optimized predictive model was obtained.

The final model can assist the bank in making more informed marketing decisions, improving campaign effectiveness, and increasing the likelihood of customer conversion while reducing operational costs.
