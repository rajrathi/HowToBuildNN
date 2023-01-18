# How to build CNN Architecture: Step-By-Step

## STEP 1

### Target
- create Datasets and Data Loaders
-  build a working  architecture skeleton under 10K parameters
- use Batch Normalization for better accuracy and model efficiency
- setting training and testing loop
- evaluating model accuracy

### Results
1. Parameters: 9,968
2. Train Accuracy: 99.61%
3. Test Accuracy: 99.26%

### Analysis
- train accuracy gradually increased with epochs
- test accuracy was better and similar to train accuracy in first few epochs
-  during last epochs train accuracy increased but test accuracy remained approximately constant which created gap between train and test accuracy
-  this suggests overfitting 

## STEP 2

### Target
- for avoiding overfitting, added dropout = 0.05 before every layer except last layer
- introduced GAP in the last layer instead of convolution
- removed maxpooling and one layer to test the models with lower number of parameters

### Results
1. Parameters: 9,376
2. Train Accuracy: 98.95%
3. Test Accuracy: 99.31%

### Analysis
- train accuracy is less than test accuracy throughout all epochs, which suggests dropout is effective in avoiding overfitting
- train accuracy is lower than usual accuracy, which shows that it can be improved further to increase test accuracy
- train accuracy is lower than last step, as there are lower number of parameters
- thus we can add one more layer that is increae the number of parameters
