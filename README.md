# Neural-Network-Challenge-2
Columbia AI Bootcamp Week 19 Module

## By Sami Chowdhury

### Background

This assignment focused on our abilities in creating a neural network that HR can use to predict whether employees are likely to leave the company, and to predict the department that best fits each employee. This meant with two columns to be predicted, we used a branched neural network. We created the branching neural network model using tensorflow and scikitlearn. The data can be found at [this link](https://static.bc-edx.com/ai/ail-v-1-0/m19/lms/datasets/attrition.csv)

### Repository Structure

```
├── attrition.ipynb
├── README.md
```

### Code Demonstration

To run the code, please run all the cells in the **attrition.ipynb** notebook. Ensure that you have the following libraries installed:

1. *pandas*
2. *tensorflow*
3. *sklearn*
4. *numpy*

### Model Summary

| Layer (type) | Output Shape | Param # | Connected to |
| ------------ | ------------ | ------- | ------------ |
| input_features (InputLayer) | (None, 14) | 0 | - |
| dense_3 (Dense) | (None, 64) | 960 | input_features[0] [0] |
| dense_4 (Dense) | (None, 32) | 2080 | dense_3[0] [0] |
| dense_5 (Dense) | (None, 16) | 528 | dense_4[0] [0] |
| dense_8 (Dense) | (None, 64) | 1,088 | dense_5[0] [0] |
| dense_9 (Dense) | (None, 64) | 1,088 | dense_5[0] [0] |
| department_output (Dense) | (None, 3) | 195 | dense_8[0] [0] |
| attrition_output (Dense) | (None, 2) | 130 | dense_9[0] [0] |

- Total params: 6,069 (23.71 KB)
- Trainable params: 6,069 (23.71 KB)
- Non-trainable params: 0 (0.00 B)
- epochs : 10
- batch size : 32
- validation split : 0.2

### Model Metrics

| Metric | Attrition | Department |
| ------ | --------- | ---------- |
| Accuracy | 0.815217 | 0.649457 |
| Loss | 0.405623 | 0.756928 |

- Total Loss : 1.187806

### Question Responses

Below is the summary of the assignment and its main takeaways.

1. **Is accuracy the best metric to use on this data? Why or why not?**

> Accuracy would still be the best metric to use on this data. This is because we still need to figure out if our model was good at predicting if someone was marked with attrition or not, and which department they were clearly labeled to. Our predicting target variables are all categorical variables, since they are all one-hot encoded. That means we need to know how accurate we are to binary and multi-class classifications. Our data is very strict and rigid, and has specific classifications, meaning accuracy for these binary and multi-class classifications are justified for this dataset.

2. **What activation functions did you choose for your output layers, and why?**

> For the output layers, I used two different activation functions. For the department layer, I used softmax, since it has 3 possible values between [**Human Resources, Research & Development, and Sales**]. Since it isn't a binary output, it needed to use softmax to be able to account for more categories. For the attrition layer, I used sigmoid since it only had 2 possible values between [**Yes and No**]. This was a binary output, so I only needed to account for values between 0 and 1 with sigmoid.

3. **Can you name a few ways that this model might be improved?**

> There are a few ways to improve the model. One way is to add more hidden layers for the output and input. This would make the deep learning neural network larger and more compute heavy. Another way to improve the model would be to decrease the batch size when fitting and compiling the model. This signficantly increases compute time but will improve accuracy. Lastly, we could use more epochs to improve the loss of the model across more epochs and time. 