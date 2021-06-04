## 1. Target**

- Making the model lighter

- Get the Setup Right

- Get a pretty decent accuracy

- Make sure the data loaders are working

- Setup the basic training loop

- Create a Baseline Model

- 15 Epochs

## 2. Result**

- Params: 13,808

- Best Train Accuracy: 99.22%

- Best Test Accuracy : 99.35%

## 3. Analysis**

- The model is not overfitting, but we need to reduce the number of params, since our target is 10K Params

- The model is underfitting since we have added BatchNorm and Dropout to the model, since we know they are beneficial for this network

- We should add data augmentation to possibly improve the model
