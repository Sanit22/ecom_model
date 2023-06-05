# Ecommerce Shoppers Behaviour Understanding

The project can be found in the file "Ecom.ipynb".

# Problem overview
This project aims to predict whether a customer will make a purchase or not based on an ecommerce dataset.
Assume that you are working in a consultancy company and one of your client is running an e-commerce company. They are interested in understanding the customer behavior regarding the shopping. They have already collected the users’ session data for a year. Each row belongs to a different user. The “Made_purchase” is an indicator that whether the user has made a purchase or not during that year. Your client is also interested in predicting that column using other attributes of the users. The client also informs you that the data is collected by non-experts. So, it might have some percentage of error in some columns.

# Dataset Description
There are 21 attributes and their descriptions are given below.

### Files
* train.csv - the training set
* test.csv - the test set

### Columns
The first six columns represent the different pages in the e-commerce website visited by a user from other sites.

* HomePage: Number of times visited this page
* HomePage_Duration: Total number of duration spent on this page.
* LandingPage: Number of times visited this page
* LandingPage_Duration: Total number of duration spent on this page.
* ProductDesriptionPage Number of times visited this page
* ProductDescriptionPage_Duration: Total number of duration spent on this page.
* GoogleMetric-Bounce Rate: Whenever a user comes to any one web-page of the website and he/she does not go to any other page and exits from the website from the same page, then this activity done by the user is called Bounce. And the percentage of the total number of times the user visiting our website and bounce it, is called Bounce Rate
* GoogleMetric-Exit Rate: The bounce rate is calculated based on the user exiting a website after visiting one page. But some users exit from the second, third, fourth, or any other page of our website, then those visitors’ data help determine the exit rate. The percentage of the total number of times the user to our website who do not exit from the first page (Landing Page) but exit after exploring other website pages is called the Exit Rate.
* GoogleMetric-Page Value: Page Value is the average value for a page that a user visited before landing on the goal page or completing an Ecommerce transaction.
* SeasonalPurchase: It is a weight indicator to track the seasonal purchase. If a user makes a purchase during any seasonal time (Mother’s Day, Diwali, Valentine's Day), we will assign based on internal heuristic.
* Month_ SeasonalPurchase: Month of the special day considered for seasonal purchase.

The other attributes like, OS, Search Engine, Zone, Type of Traffic, Customer Type, Gender, Cookies Setting, Education, Marital Status and Weekend Purchase are self-explanatory variables

# Problem Solving Approach

## Data Analysis
Before diving into the predictive modeling process, an exploratory data analysis was performed to gain insights into the dataset. The following steps were undertaken:

* Examined the distribution of features and labels.
* Identified outliers using a box plot and correlation using a correlation matrix.
* Investigated missing values or anomalies in the data.

## Data Preprocessing
The following preprocessing steps were applied:

### Duplicate Rows Handling:

* Approach 1: Marked all duplicates as true to ensure wrongly marked false instances were correctly marked true.
* Approach 2: Marked all duplicates as false, to ensure wrongly marked true instances were correctly marked false.
* Evaluated the impact of each approach on model performance.

### Imputing and scaling:

* Applied K-Nearest Neighbors (KNN) imputer for numerical columns and SimpleImputer for categorical columns to fill missing values.
* Scaled numerical columns using StandardScaler.
* Performed One-Hot Encoding to convert categorical variables into numerical representations.

## Model Building

Various classification algorithms were explored to build predictive models, including logistic regression, decision trees, random forests, Bagging classifier, AdaBoost, and XGBoost. The following steps were followed:

* Trained each model using the preprocessed data.
* Evaluated the performance of each model using appropriate metrics (e.g., precision, recall, F1 score, and accuracy).
* The best performing algorithms from the previous step were identified and further optimized through hyperparameter tuning.

## Model Evaluation
Based on the evaluation results on the test set, the best performing model was selected. The model's performance was assessed using a classification report. The following metrics were analyzed:

* Precision: The ability of the model to correctly predict positive instances.
* Recall: The ability of the model to identify all positive instances.
* F1 Score: The harmonic mean of precision and recall, providing a balanced measure.
* Accuracy: The overall correctness of the model's predictions.

The model with the best scores was chosen to make the final predictions.

## Results
The score achieved on this model was 0.645.

