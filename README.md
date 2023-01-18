# How to build CNN Architecture: Step-By-Step

## STEP 1

### Target
- create Datasets and Data Loaders
-  build a working  architecture skeleton under 10K parameters
- use Batch Normalization for better accuracy and model efficiency
- setting training and testing loop
- evaluating model accuracy

### Results
1. Parameters: 9968
2. Train Accuracy: 99.61%
3. Test Accuracy: 99.26%

### Analysis
-  Training accuracy gradually increased with epochs
-  Test accuracy was better and similar to train accuracy in first few epochs
-  During last epochs training accuracy increased but test accuracy remained approximately constant which created gap between train and test accuracy
-  This suggests overfitting
