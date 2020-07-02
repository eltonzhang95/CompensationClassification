# Kaggle Data Science Community Compensation Classification
The purpose this project is to analyze and predict the compensation of the data science community from Kaggle yearly servey.
### Dataset
The dataset being analyzed is the "2019 Kaggle ML & DS Survey". The survey contains 34 multiple choice questions, and is answered by 19,717 participants globally. 
### Pre-processing
The survey contains both numerical and categorical entries, where numerical entries can be either ordinal or non-ordinal. Therefore, encoding needs to be done in order to implement regression models. In this project, One-Hot encoding is utilized. In detail, the following steps are performed:
1. Remove all 'Other_Text' indicator columns.
2. Introduce a new feature 'country_income_ranking'.
3. Remove participants who answer less than 24 questions.
4. One-hot encoding categorical data.
### Feature Engineering
Too many features add training complexity to ML models. Therefore, feature engineering and selection is required. In order to filter out the most important features, questions that over 95% of the participants gives the same answer is eliminated since they do not contribute a lot. Then, chi-square contengency test is performed between each remaining feature and the target, which is compensation. Last but not least, correlation between the remaining features are checked. If any two features with P-value greater than 0.5, the less importnat feature is removed. After all the feature selection processes, 11 features remain.
### Model Tuning
In this project, logistic regression is being put on to test. The optimal hyper-parameters are aquired thru grid-search with cross-validation. The  result shows that logistic regression is not the best ML method to implement to such kind of dataset.  
  
To further improve the accuracy, ensemble based ML method like random forest or XGBoost can be better choices since most of the categorical data becomes binary after encoding. Also, different encoding methods might improve the performance as well, but still might not be desirable.
