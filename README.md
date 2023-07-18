# EMNIST

## Project Goal:
This project aims to build a neural network model to solve the EMNIST classification problem.
As deep neural networks are widely used in various domains, such as computer vision, natural
language processing and medical image analysis, how to create a proper neural network to
implement the specific task has become very important.

## Dataset Introduction:
In the project, we use the EMNIST1 (Extended MNIST) dataset, which is a set of handwritten
character digits derived from the NIST Special Database 19 and converted to a 28x28 pixel
image format and dataset structure that directly matches the MNIST dataset.
Due to the EMNIST dataset includes 6 different splits, we select “Balanced” dataset, which
had addressed the balance issues in the “ByClass” and “ByMerge” datasets. It is derived from
the “ByMerge” dataset to reduce mis-classification errors due to capital and lower-case letters
and also has an equal number of samples per class. The “Balanced” dataset information is as
follows:
- Train: 112,800
- Test: 18,800
- Total: 131,600
- Classes: 47 (balanced)

If we visualize the EMNIST images, they look like as follows: https://www.kaggle.com/datasets/crawford/emnist

## Project Introduction:
Write the python code to build various neural networks and compare the performance of
different network models.
In this project, you need implement two types of neural networks, one is the multilayer
perceptron (MLP) networks with at least three hidden layers (i.e., neural networks with only
fully-connected layers); the other is the Convolutional Neural Networks (CNNs) with at least
two convolutional layers.

For each network model, you need consider to multiple parameters to obtain the best
performance. You can use various techniques (you have learnt) to overcome overfitting,
underfitting, unstable gradient, etc. You need to utilize and explore the following techniques
to train your neural network models:
1) Adaptive Learning Rate (e.g., learning rate schedulers) (explore at least two learning
rate scheduling methods)
2) Activation function (ReLU, Leaky ReLU, ELU, etc.) (explore at least three activation
functions)
3) Optimizers (SGD, ADAM, RMSprop, ASGD, AdaGrad, etc.) (exlore at least three
optimizers)
4) Batch Normalization (explore two options: with Batch normalization, without Batch
normalization)
5) L1 & L2 regularization (explore three options: without L1&L2 regularization, with L1
regularization, with L2 regularization)
6) Dropout (explore two options: with or without Dropout)

Note: Below is one strategy you can try to effectively explore the combinations of the above techniques:
- Initially, establish a baseline model configuration utilizing your existing knowledge of deep learning. For
instance, you might select ReLU, ADAM, Batch Normalization, L2 Regularization, and Dropout, etc., as the
initial setup of your model.
- Following this, investigate each optimization technique separately, while preserving the most effective
settings from previous explorations. For exmaple,
  - Explore learning rate scheduling methods and identify the most suitable one; Incorporate
this method into your model
  - Explore activation functions and select the most appropriate one; Use this activation
function in your model
  - Explore various optimizers and choose the optimal one for your model
  - Continue this process to explore additional techniques
- Upon completing these explorations, your resulting model should demonstrate superior performance
compared to the initial baseline configuration.

This is one possible strategy, of course, you can use other feasible strategies, as long as you can demonstrate your ability
to evaluate and investigate various techniques in order to determine the most appropriate deep learning model for a
specific task. The assessment of this critical skill is one of the key goals of this assignment.
During your training MLP and CNNs, you also need to decide the below hyperparameters that
are most suitable for your MLP and CNN models, for example,
- Number of Hidden layers
- Number of hidden neurons for each hidden layer
- …

When building the neural networks, you can use any libraries (pandas, NumPy, matplotlib …)
and frameworks (PyTorch, Tensorflow, …). However, your code must include the following
steps:
1. Indicate the imported packages/libraries
2. Load the dataset (you can import PyTorch dataset library to download the dataset)
3. Split data into a training dataset and a testing dataset (e.g., using DataLoader in
PyTorch)
4. Understand the dataset and visualize the dataset:
a. Print-out the number of training/testing samples in the dataset.
b. Plot some figures to visualize some samples as above figures (we will provide
the mapping .txt file for “Balanced” dataset, if you can implement mapping
from the index to the classes by yourself, you can ignore the .txt file).
5. For the two models - MLP and CNNs, please complete the below steps respectively on
the training dataset
a. For the techniques/hyperparameters you choose to explore, you can use cross
validation to find the most suitable combination (of those
techniques/hyperparameters) under the evaluation metric of accuracy.
b. After you obtain the best version of the model (i.e., the model with the best
techniques/hyperparameters combination), please:
1. Plot the loss function graph respect to the iteration/epoch
2. Plot the accuracy graph respect to the iteration/epoch
3. You can use either CPU or GPU to train your model and please print
the training time

6. After you obtained the best version of MLP and CNNs, please test both models on the
testing dataset
a. Compare the performance of MLP and CNNs
1. Load your model and print the prediction of the top six samples in testing
dataset, compare them with the true labels, which will be similar to the
below (example from Fashionmnist).
2. Plot the confusion matrix of two models – MLP and CNNs
3. Summarize the performance of two models using accuracy, please also
report the precision, recall and F1 score of MLP and CNNs
