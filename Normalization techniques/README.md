## Assignment 6 – EVA 6

Requirement

1)We need to make 3 version of Assignment -5 as follows

2)Network with Group Normalization + L1

3)Network with Layer Normalization + L2

4)Network with L1 + L2 + BN

5)Create a model.py file that includes GN/LN/BN and takes an argument to decide which normalization to include, and then import this model file to the notebook. 

6)Create a single notebook file to run all the 3 models above for 25 epochs each

7)Create these graphs:
 * Graph 1: Training Loss for all 3 models together
 * Graph 2: Test/Validation Loss for all 3 models together
 * Graph 3: Training Accuracy for all 3 models together
 * Graph 4: Test/Validation Accuracy for all 3 models together

8)Find 20 misclassified images for each of the 3 models, and show them as a 5x4 image matrix in 3 separately annotated images.
Well documented README file

## This is a function which takes many parameters. type: The user is expected to pass one of the three values**

 - BN : If user pass this then the program must perform Batch Normalization

 - LN : If user pass this then the program must perform Layer Normalization

 - GN : If user pass this then the program must perform Group Normalization


## Group Normalization + L1

**Construct**

The group normalization should not add much parameters to the network, hence should not be computationally expensive than the vanilla 
**Observation**
The group normalization and L1 regularization didn't do a good job on model accuracy.
- The model validation accuracy droped down to 98.67%.
- However the validation accuracy is above train accuracy ( That's good news, which means this network has potential to improve further) 
- Let's observe the misclassified images and see where things went wrong 

## Layer Normalization + L2

The Layer normalization should add more parameters to the network, hence it should be computationally expensive.

![image](https://user-images.githubusercontent.com/65776820/123522258-e13c3a00-d6d9-11eb-9e5d-b0437a905d7b.png)




## Batch Normalization L1 + L2

The Batch normalization and L1/L2 regularization improved the accuracy to 99.15% with same number of parameters

![image](https://user-images.githubusercontent.com/65776820/123522267-ed27fc00-d6d9-11eb-8f71-4dbc88d0a86e.png)


## Train Loss Observation

![image](https://user-images.githubusercontent.com/65776820/123522276-ff099f00-d6d9-11eb-89a3-60fda9a89232.png)


## Test Loss Observation

![image](https://user-images.githubusercontent.com/65776820/123522291-0e88e800-d6da-11eb-92e6-1ab85a6c2125.png)

## Train Accuracy Observation

![image](https://user-images.githubusercontent.com/65776820/123522303-1a74aa00-d6da-11eb-8427-3e4fb74156ed.png)



## Manual Calculation

![image](https://user-images.githubusercontent.com/65776820/123522186-7428a480-d6d9-11eb-8178-d53eb54f6baa.png)




