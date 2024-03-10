# Deep Learning Challenge
_Module 21 Report_

## Overview of the Analysis

This analysis reviews the accuracy in predicting the success of crowdfunding through the nonprofit organization Aophabet Soup.  A large dataset was provided to run through neural network and machine learning with different parameters to determine if this method could assist in predicting success accurately given the makeup of the dataset.

The dataset is comprised of 34,299 rows of data and included the following categories:

- APPLICATION_TYPE
- AFFILIATION
- CLASSIFICATION
- USE_CASE
- ORGANIZATION
- STATUS
- INCOME_AMT
- SPECIAL_CONSIDERATIONS
- ASK_AMT
- IS_SUCCESSFUL

Three test models were run sequentially with minor changes made in an effort to improve accuracy.  All tests were run with "IS_SUCCESSFUL" as the target, and with the EIN and NAME columns removed as they were not impactful to the results.  The variable adjustments are noted in the Results section.

##Results

###Neural Network Machine Learning Model 1:

The first test was run with the following data modifications and ML settings: 

- Application type data was minimized to only classify types with 500 or more entries
  - Those with less were classified as "other"
  - This brought the Application type count down from 17 to 9
 
- Classification data was minimized to only classify those with 1000 or more entries
  - Those with less were classified as "other"
  - This brought the Classification count down from 71 to 6
  
- Deep neural network settings of: 
  - 2 hidden layers (1st with 8 nodes, 2nd with 5 nodes)
  - Training with 75%, Test with 25%
  - 100 epochs

**loss: .5530 - accuracy: 0.7263 - 490ms/epoch - 2ms/step**  (Does not meet the goal of minimum 75% accuracy)

###Neural Network Machine Learning Model 2:

The second test was run with the following data modifications and ML settings: 

- Application type data was minimized to only classify types with 500 or more entries
  - Those with less were classified as "other"
  - This brought the Application type count down from 17 to 9
- Classification data was minimized to only classify those with 1000 or more entries
  - Those with less were classified as "other"
  - This brought the Classification count down from 71 to 6
- Deep neural network settings of: 
  - 3 hidden layers (1st with 16 nodes, 2nd with 8 nodes, 3rd with 8 nodes)
  - Training with 75%, Test with 25%
  - 50 epochs

**loss: .5518 - accuracy: 0.7259 - 488ms/epoch - 2ms/step**  (Does not meet the goal of minimum 75% accuracy) 

###Neural Network Machine Learning Model 3:

The third test was run with the following data modifications and ML settings: 

- Application type data was minimized to only classify types with 500 or more entries
  - Those with less were classified as "other"
  - This brought the Application type count down from 17 to 9
- Classification data was minimized to only classify those with 1000 or more entries
  - Those with less were classified as "other"
  - This brought the Classification count down from 71 to 6
- Ask Amount data was binned into the following categories, minimizing the individual count of 8747 count to the 9 groups:
  - 0-5k         25398
  - 10k-50k       2398
  - 100k-500k     2304
  - 50k-100k      1423
  - 1M-10M        1165
  - 500k-1M        650
  - 5k-10k         549
  - 10M-100M       311
  - 100M+          101
- Deep neural network settings of: 
  - 3 hidden layers (1st with 16 nodes, 2nd with 8 nodes, 3rd with 8 nodes)
  - Training with 75%, Test with 25%
  - 100 epochs

**loss: .5509 - accuracy: 0.7264 - 523ms/epoch - 2ms/step**  (Does not meet the goal of minimum 75% accuracy) 

##Summary

All three tests came back very similarly with 72.63%, 72.59%, 72.64% accuracy. With some additional organization and purposeful encoding into numerical values (to avoid having to encode text to numerical values which is not always efficient or effective), it is possible that this method may be helpful in the future.  However, as it stands with this dataset and organization, even after binning and encoding text objects, I do not have a lot of confidence in accurately predicting success.
