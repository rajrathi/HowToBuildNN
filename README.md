# How to build CNN Architecture: Step-By-Step

## STEP 1

[Code](HowToBuildCNN_step1.ipynb)

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

[Code](HowToBuildCNN_step2.ipynb)

### Target
- for avoiding overfitting, added dropout = 0.05 before every layer except last layer
- introduced GAP in the last layer instead of convolution
- removed maxpooling and one layer to test the models with lower number of parameters

### Results
1. Parameters: 9,376
2. Train Accuracy: 98.94%
3. Test Accuracy: 99.21%

### Analysis
- train accuracy is less than test accuracy throughout all epochs, which suggests dropout is effective in avoiding overfitting
- train accuracy is lower than usual accuracy, which shows that it can be improved further to increase test accuracy
- train accuracy is lower than last step, as there are lower number of parameters
- thus we can add one more layer that is increase the number of parameters


## STEP 3

[Code](HowToBuildCNN_step3.ipynb)

### Target
- for increasing train accuracy, introduce one more layer i.e., increase number of parameters
- increasing train accuracy should increase test accuracy as well

### Results
1. Parameters: 9,968
2. Train Accuracy: 98.94%
3. Test Accuracy: 99.30%

### Analysis
- Even after adding more number of parameters, there is quite negligible improvement in the test accuracy 
- The model is performing similar to the previous model with less paramters, as there is no improvement in train accuracy
- This suggest that dropout of 0.05 is heavily regulating the model, therefore we need to decrease it 

## STEP 4

[Code](HowToBuildCNN_step4.ipynb)

### Target
- decrease the dropout rate (0.025, 0.02, 0.01) to avoid underfitting

### Results
1. Parameters: 9,968
2. Train Accuracy: 99.25%
3. Test Accuracy: 99.27%

### Analysis
- the dropout = 0.01, got the desired results and it helped to avoid underfitting
- but the model is not crossing the mark of 99.3 
- We can rotations and vertical and horizontal shift in images as we saw it in some images

## STEP 5

[Code](HowToBuildCNN_step5.ipynb)

### Target
- add rotations (7 degrees) to images
- add vertical and horizontal shift (5% of height and width)

### Results
1. Parameters: 9,968
2. Train Accuracy: 98.89%
3. Test Accuracy: 99.30%

### Analysis
- training become difficult as the train accuracy dropped
- no significant change in test accuracy
- model not learning faster therefore test accuracy is not crossing 99.30 mark, therefore LR should be increased
- no consistency in test accuracy, therefor LR scheduler should be used

## STEP 6

[Code](HowToBuildCNN_step6.ipynb)

### Target
- add LR scheduler for the consistency of accuracy
- increased LR from 0.01 to 0.3 to maked model learn faster
- added StepLR with steps=4 and making LR 1/10th of previous LR after every 4 steps
- 
### Results
1. Parameters: 9,968
2. Train Accuracy: 99.17%
3. Test Accuracy: 99.46%

### Analysis
- got desired results of test accuracy above 99.4% for multiple epochs
- test accuracy gets consistent in few last epochs ranging from 99.44 to 99.46
- can be improved further with better LR scheduler