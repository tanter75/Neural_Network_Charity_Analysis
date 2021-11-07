# Neural Network Charity Analysis

## Overview of the analysis: 
###
The purpose of this analysis is to utilize machine learning and neural networks to create a binary classifier that is capable of predicting whether charity applicants will be successful if funded by Alphabet Soup.  This analysis will use a CSV file containing over 34,000 organizations that have previously received funding.

## Results of Analysis:
###
For this analysis the target output used was 'IS_SUCCESSFUL'.  In order to clean up the data set, in the initial approach the 'EIN' and 'NAME' column were dropped.  In the first optimized attempt the 'STATUS' column was also dropped.  Attempt #2 also dropped 'USE_CASE'.  
For data preprocessing, the following variables were included as features in the model: 'APPLICATION_TYPE', 'AFFILIATION', 'CLASSIFICATION', 'USE_CASE', 'ORGANIZATION', 'STATUS', 'INCOME_AMT', 'SPECIAL_CONSIDERATIONS', 'ASK_AMT', unless otherwise indicated.  It was determined that 'EIN' and 'NAME' were neither a target nor a feature and therefore the column was dropped.

The initial model dropped two columns: 'EIN' and 'NAME', used 70 epochs and yielded the following results:
![image](https://user-images.githubusercontent.com/86161212/140663732-a8de098f-22c0-49cb-ab6a-82bb08633fc3.png)

The first optimized model dropped 3 columns, used 40 epochs and yielded the following results:
![image](https://user-images.githubusercontent.com/86161212/140663599-dfd7250e-29ac-4140-a392-09312ddb44c0.png)

The second optimized model dropped 4 columns: 'EIN', 'STATUS', 'USE_CASE' and 'NAME', used 100 epochs and yielded the following results:
![image](https://user-images.githubusercontent.com/86161212/140663634-9b7806cc-6894-4b5e-9ec8-e8c641cee3c3.png)

The third and final optimized model dropped two columns: 'EIN' and 'NAME', used 50epochs and increased the number of neurons in hidden_layer2 to 40.  Here are the results:
![image](https://user-images.githubusercontent.com/86161212/140663843-fdcd38aa-e8fc-43ae-8c93-5acc80ea986d.png)

![image](https://user-images.githubusercontent.com/86161212/140664192-cff3b061-ab84-437d-b55a-edbfcedc8299.png)

For hidden layer 1 & 2 the number of neurons used was based on the sequential model output shape and bears in mind that the second hidden layer (80) should have at least twice the number of neurons as the first hidden layer (30).

## Summary of Analysis:
###
In both the initial machine learning model and the three subsequent optimized attempts, the predictive accuracy of the models did not exceed 75%.  In order to increase the accuracy of the predictive model there are several recommendations.  First would be to complete a deeper analysis of the dataset itself to determine which factors are truly impactful of the 'IS_SUCCESSFUL' output and perhaps expanding the dataset.  The second recommendation would be to try to use a different machine learning model.  As increasing and decreasing features, epochs, and neurons did not make a significant impact on the output accuracy, a different machine learning model may be more impactful.  As the desired output is categorical: 'IS_SUCCESSFUL': Yes or No, supervised machine learning using the ensemble random forest model may yield more accurate predictions.
