# Credit_Risk_Analysis

## Overview of the analysis: 
##### Explain the purpose of this analysis.
* Using the credit card credit dataset from LendingClub, a peer-to-peer lending services company, we will deploy various Machine Learning algorithms to predict credit risk and evaluate the performance of those models.
  * We will oversample the data using the (1) RandomOverSampler and (2) SMOTE algorithms, and (3) undersample the data using the ClusterCentroids algorithm. 
  * We will use a combinatorial approach of (4) over- and under sampling using the SMOTEENN algorithm. 
  * We will use two new machine learning models that reduce bias, (5) BalancedRandomForestClassifier and (6) EasyEnsembleClassifier

## Results: 
##### Using bulleted lists, describe the balanced accuracy scores and the precision and recall scores of all six machine learning models. Use screenshots of your outputs to support your results.
[!Classification Reports] https://github.com/BBBrian1124/Credit_Risk_Analysis/blob/main/Challenge/Classification_Reports.png
* The image shows the balanced accuracy scores (bas), precision scores (pre) and recall scores (rec) of the 6 models mentioned above 
* Recall the definitions of each score:
  * Balance Accuracy Score = the % of predictions our model got right
  * Precision = is a measure of how reliable a positive classification is (i.e. if the model predicted the risk to be high or low, how likely is that prediction to be       correct)
  * Recall = is a measure of how well the model detected all of the “true/actual” outcome (i.e. did the model predict all of the high credit risk / low credit risks?)
* When looking at credit card risks, we should be more concerned with precision, so that the applications are correctly classified. We would not want a high risk applicant to be classified as low risk, as that may lead to monetary losses if the applicant is unable to repay their credit card bills. Similarly, we wouldn't want to classify a low risk applicant as high risk, as this may lead to lossed opportunities/revenues (i.e. from fees) if the applicant is likely to be paying their bills, and generating revenue.
* The accuracy of the model is important for the same reasons as precision.
* The sensitivity is still a valuable metric for a similar reason. If the credit card applicant poses low risk, we want to ensure that we are correctly predicting and identifying those applications, a low sensitivity would mean that we are missing out on predicting/identifying those applications, and thus potential revenues. The inverse would be true, where if sensitivity is high, we are identifying these low risk applications which increase the chances of maximizing profits. For the high risks, we want to ensure we are capture all high risk applicants as well, so that they can be turned away or charged higher interest rates to reduce/offset the risk of lending. A low sensitivity would mean that this is not happening, and a high sensitivity would mean that we are capable of predicting/identifying these applications and thus will be able to reject their application or adjust their lending rate accordingly. 
* A look at all the models show that all models have a high precision score for identifying low risk applications, but a poor precision score for identifying high risk applications 
* Sensitivity and accuracy for the sampling models are fairly low to mediocre 
* The Balanced Random Forest Classifier and Easy Ensemble AdaBoost Classifier perform better in terms of sensitivity and accuracy, with the latter being the best in these metrics


## Summary: 
##### Summarize the results of the machine learning models, and include a recommendation on the model to use, if any. If you do not recommend any of the models, justify your reasoning.
* With the above in mind, we should reject all of the models. They all have a low precision score for high risk applications, meaning they will not be able to predict/correctly classify high risk applications, which as explained above, leads to a risk of monetary loses. Despite all of the models having a high precision score in predicting/identifying low risk applications, and thus able to identify profitable applicants, the sensitivity for most of those models are low to mediocre, meaning we won't be able to predict/identify all of these low risk applications, and thus we may not be able to obtain enough revenues from these applications (since we cannot capture all of them) to offset the risks of the low precision scores for the high risk classifications.  
* If a model must be used, the Easy Ensemble AdaBoost Classifier can be used since it scores the highest in all metrics but the precision score for high risk applications, which remains poor. This means that it is able to accurately identify all low risk applications which will help with maximizing profits, however, the risk is that it is not precise at predicting high risk applications, so we run the risk of approving high risk applications. Further analysis can be done to see if this would be a valid strategy/model to use (i.e. if the profits will exceed potential losses from wrongly identifying/predicting high risk applications).

## Appendix
[Repository Link] https://github.com/BBBrian1124/Credit_Risk_Analysis
