## 1. Target

- Fine Tune the Transforms, set rotation to `-10deg to 10deg`
- Use the OneCycleLR Scheduler.

> The 1cycle learning rate policy changes the learning rate after every batch. step should be called after a batch has been used for training.

## 2. Result

- Params: `9,962`
- Best Train Accuracy: `98.12%`
- Best Test Accuracy : `99.43%`

## 3. Analysis

- Now the learning is consistent, the accuracy increases
