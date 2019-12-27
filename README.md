# Predicting-online-shoppers-intention

Considering a website's metrics measured by Google Analytics, the user's browsing session parameters and demographics, we developed a machine learning model to predict whether the user in question will generate revenue for the website.

Team : Akankshi Mody, Apoorv Mehrotra, Grant Zhong, Jacob Padden and Sachin Balakrishnan from The University of Texas at Austin

### Problem statement
In this group project, the five of us worked on a binary classification problem - Given a user and a website, the objective was to classify him/her as revenue generating or not. Over the past decade, we have been witnessing the exponential growth in the volume of online purchasing. Retailers can be benefited in a great deal if they get to know upfront the potential value that a customer brings. This can help to formulate and optimize marketing strategies, customer specific promotion deals etc. 

### Approach
Machine learning models used: Logistic Regression, Lasso, Ridge, Decision Trees, kNN, Random Forest. 
Most of the classification problems have a class imbalance issue built-in, and ours was also no different. The dependent variable was skewed with only 15% of the observations as positive (Revenue generating). Due to this, our first set of models hardly were able to get the positive predictions correctly. To tackle, we tried data resampling methods - Under and over sampling with SMOTE and ROSE libraries and observed significant improvement in performance. We used the Area under ROC curve and standard F1 score to evaluate the performance of our models. 

Logistic regression outperformed the other models with an overall accuracy of 0.88 and f1 score of 0.82.

Results are documented in 'Online Shopper's intention.pptx' file.
