# Predicting Online Shopper Intention

This project was completed as part of the Predictive Modeling Course during the MSBA Program at UT Austin.<br>
Team members: Akankshi Mody, Apoorv Mehrotra, Grant Zhong, Jacob Padden and Sachin Balakrishnan

## Introduction
Protection of personal data is an extremely hot topic nowadays. Whether we like it or not, our personal data is out there and is being exploited in an unlimited number of ways. Each and every one of our digital footprints grows by the day, and our behavior is being predicted like never before. Gone are the days where we are embarrassed about our internet search history, or even the days where we worried about privacy of highly sensitive information. We’re all aware of the very public personal data privacy class action lawsuits involving Facebook and Cambridge Analytica, but this is just the tip of the iceberg. With more and more stigma generated surrounding the exploit of personal user data, our team sought an alternative approach to predict online user activity, specifically within eCommerce.

Considering a website's metrics measured by Google Analytics, the user's browsing session parameters and demographics, we developed a machine learning model to predict whether the user in question will generate revenue for the website. Over the past decade, we have been witnessing the exponential growth in the volume of online purchasing. Retailers can be benefited greatly if they get to know upfront the potential value that a customer brings. This can help to formulate and optimize marketing strategies, customer specific promotion deals etc.

## Data
The [dataset](https://archive.ics.uci.edu/ml/datasets/Online+Shoppers+Purchasing+Intention+Dataset) consists of feature vectors belonging to 12,330 web sessions.<br>
A session is a set of hits triggered by a user. A hit is a user interaction (pageview, screenview, event, transaction) that sends data to Google Analytics server. A user can generate >1 sessions in a day, hence number of users<=number of sessions<br>
The dataset was formed so that each session would belong to a different user in a 1-year period to avoid any tendency to a specific campaign, special day, user profile, or period.<br>

The dataset consists of 10 numerical and 8 categorical attributes.
1. The 'Revenue' attribute is our dependent variable.
2. "Administrative", "Administrative Duration", "Informational", "Informational Duration", "Product Related" and "Product Related Duration" represent the number of different types of pages visited by the visitor in that session and total time spent in each of these page categories. The values of these features are derived from the URL information of the pages visited by the user and updated in real time when a user takes an action, e.g. moving from one page to another.
3. The "Bounce Rate", "Exit Rate" and "Page Value" features represent the metrics measured by "Google Analytics" for each page in the e-commerce site.
4. The value of "Bounce Rate" feature for a web page refers to the percentage of visitors who enter the site from that page and then leave ("bounce") without triggering any other requests to the analytics server during that session.
5. The value of "Exit Rate" feature for a specific web page is calculated as for all pageviews to the page, the percentage that were the last in the session.
6. The "Page Value" feature represents the average value for a web page that a user visited before completing an e-commerce transaction.
7. The "Special Day" feature indicates the closeness of the site visiting time to a specific special day (e.g. Mother’s Day, Valentine's Day) in which the sessions are more likely to be finalized with transaction. The value of this attribute is determined by considering the dynamics of e-commerce such as the duration between the order date and delivery date. For example, for Valentina’s day, this value takes a nonzero value between February 2 and February 12, zero before and after this date unless it is close to another special day, and its maximum value of 1 on February 8.
8. The dataset also includes operating system, browser, region, traffic type, visitor type as returning or new visitor, a Boolean value indicating whether the date of the visit is weekend, and month of the year.

## Goal of the Project
Engineer predictive models for a binary classification problem - given a user and a website, classify him/her as revenue generating or not. Compare metrics such as sensitivity, accuracy and area under the curve to identify the best classification model.

## Tools Used
Technology: R-Studio, R Markdown

Machine learning models: Logistic Regression, Lasso, Ridge, Decision Trees, kNN, Random Forest. 

## Approach
Our classification problems had a class imbalance problem for our dependent variable.<br>
The dependent variable was skewed with only 15% of the observations as positive (meaning that the customer generated revenue). Due to this, our first set of models were barely performing better than the baseline. To tackle this issue, we experimented with various data resampling methods - undersampling and oversampling with [SMOTE](https://www.rdocumentation.org/packages/DMwR/versions/0.4.1/topics/SMOTE) and [ROSE](https://www.rdocumentation.org/packages/ROSE/versions/0.0-3/topics/ROSE) libraries - to observe significant improvement in the performance of our models. <br>
The primary metrics we used to compare and evaluate the performance of our models were the area under ROC curve and standard F1 score.

## Results
The logistic regression model outperformed the other models with an overall accuracy of 0.88, AUC of 0.84 and f1 score of 0.82.<br>
The detailed results are shown in our [presentation](https://github.com/akankshimody/Predicting-online-shoppers-intention/blob/master/Predictive%20Modeling%20Group%20Project.pdf)
