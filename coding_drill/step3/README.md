
## 1. Target

- Reduce the number of parameters
- Add Transformations
- By close examination of the dataset we see that `-7deg to 7deg` rotations should work for us

## 2. Result

- Params: `9,707`
- Best Train Accuracy: `98.85%`
- Best Test Accuracy : `99.32%`

## 3. Analysis

- We added transformations/augmentation to compensate the removal of params, now we need to train the remaining neurons harder
- The model is still overfitting.
