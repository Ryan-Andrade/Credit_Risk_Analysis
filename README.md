# Credit_Risk_Analysis
## Overview
 The purpose of this analysis was to review the performance of different machine learning predictive algorithms on an unbalanced credit card dataset to classify the loans as risky or not.

## Results
In our results the target variable "loan_status" has been encoded so that low_risk is equal to 1 and high_risk is equal to 0. The trade-off between precision and sensitivity in this analysis is as follows: precision is the model's ability to identify low risk loans, sensitivity is a measure of how many people who are actually a low risk of defaulting on their loans and were correctly identified. In this model it is more important to have precision because we will be able to fulfill more loans by identifying low risk individuals and  will be able to absorb the cost of the few high risk loans that are not detected.

1. RandomOverSampler:
   1. Accuracy Score: 0.5001461646398503
   2. Classification Report: https://postimg.cc/yJcNP9DZ
   3. In this model we have a low F1 score which means that there is a high imbalance between sensitivity and precision. From our classification table we can see that there is a high recall score for low risk individuals it means that this model is too aggressive in identifying high risk loans to the point where no loans will be issued.
2. SMOTE Oversampling
   1. Accuracy Score: 0.659763161185155
   2. Classification Report: https://postimg.cc/Lg5b3txk
   3. In this model you can see that we have a weak low risk F1 score and a strong F1 score for high risk loans. While this model seems to have increased its effectiveness in identifying high risk loans we still face the problem of not approving the greater amount of low risk loans.
3. RandomUnderSampler
   1. Accuracy Score: 0.5602305407107595
   2. Classification Report: https://postimg.cc/Z0Y0pwSk
   3.  this model is similar to the one above and that the F1 score is high four high risk loans and low for low risk loans. Comparatively the model above performed better identifying high risk loans and we are still facing the same issue as mentioned.
4. SMOTE_EEN
   1. Accuracy Score: 0.6570097666922913
   2. Classification Report: https://postimg.cc/vcRjCNHk
   3. This model falls in line with the prior two without much enhancement.
5. BalancedRandomForest:
   1. Accuracy Score: 0.9318062360492364
   2. Classification Report: https://postimg.cc/grBR0C6t
   3. This model further increases accuracy for predicting high risk loans. However it's still suffer from a lack of ability in identifying low risk loans.
6. EasyEnsembleClassifier:
   1. Accuracy Score: 0.9318062360492364
   2. Classification Report: https://postimg.cc/4nzk4gMs
   3. Here we have found our strongest performing model, although the precision remains low .09 this is the highest of all models in predicting low risk loans also the high accuracy of predicting high risk loans remains strong at 0.94.

# Summary
 My recommendation based on our analysis would be to use the easy ensemble classifier machine learning algorithm on loan applications that are issued above a certain high dollar amount because defaults on these high dollar loans are more costly to the company and require a stricter classification metrics in order to be approved.