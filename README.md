# MNIST Project

This is my Neural Networks course project.  
I chose the Handwritten Digit Recognition problem using the MNIST dataset.

The idea of the project is to build a neural network that can recognize handwritten digits from 0 to 9.  
Each image in the dataset contains one digit, and the model tries to predict the correct number.

## Dataset

I used the MNIST dataset because it is simple, clear, and suitable for practicing neural networks.

The dataset contains grayscale images of handwritten digits.  
Each image has a size of 28 x 28 pixels.

I loaded the dataset using torchvision.datasets.MNIST.

Dataset link:  
https://pytorch.org/vision/stable/generated/torchvision.datasets.MNIST.html

## Data Preprocessing

Before training the model, I prepared the data.

I converted the images to tensors using ToTensor.  
This also scaled the pixel values from 0 to 1, which helps the model train better.

The dataset does not contain missing values, so I did not need to handle missing data.

There were no categorical input features, so encoding was not needed.

The training data was split into training and validation sets.  
The test set was used only for final evaluation.

Dataset sizes:

- Training set: 48000 images
- Validation set: 12000 images
- Testing set: 10000 images

## Model

I used a Multilayer Perceptron model.

The input layer has 784 features because each image is 28 x 28 pixels.

28 x 28 = 784

The output layer has 10 neurons because the model predicts one digit from 0 to 9.

I used Cross Entropy Loss because this is a multi-class classification problem.  
I also used Adam optimizer to update the model weights during training.

## Experiments

I made two experiments to compare different settings.

In the first experiment, I used ReLU activation, 128 hidden neurons, and a learning rate of 0.001.

In the second experiment, I used Tanh activation, 64 hidden neurons, and a learning rate of 0.01.

| Experiment | Activation | Hidden Neurons | Learning Rate | Test Loss | Test Accuracy |
|---|---|---:|---:|---:|---:|
| Experiment 1 | ReLU | 128 | 0.001 | 0.0738 | 97.78% |
| Experiment 2 | Tanh | 64 | 0.01 | 0.1403 | 95.93% |

## Results

Experiment 1 gave the best result.

It achieved a test accuracy of 97.78% and a test loss of 0.0738.

Experiment 2 also gave a good result, but it was lower than Experiment 1.  
It achieved a test accuracy of 95.93% and a test loss of 0.1403.

From the results, I found that ReLU with 128 hidden neurons and learning rate 0.001 performed better.

## Visualizations

I plotted the training and validation loss curves.  
I also plotted the training and validation accuracy curves.

The loss curves show that the loss decreased during training.  
This means that the model was learning.

The accuracy curves show that the accuracy increased during training.  
This means that the model performance improved over the epochs.

The training and validation curves were close to each other, so there was no strong overfitting.

## Regularization

I used Dropout in the model.

Dropout helps reduce overfitting by randomly turning off some neurons during training.  
This helps the model generalize better on new data.

## How to Run

Open the notebook file:

MNIST Project.ipynb

Then run the blocks in order.

The notebook is divided into 5 parts:

1. Import libraries, load the dataset, and prepare the data
2. Build the MLP model
3. Define the training and evaluation functions
4. Run the experiments and show the results table
5. Show the visualization curves

The MNIST dataset will be downloaded automatically when the notebook runs.
## Conclusion

In this project, I built an MLP model to classify handwritten digits using the MNIST dataset.

I trained the model, evaluated it, and compared two experiments.

The best result was from Experiment 1 because it had the highest accuracy and the lowest test loss.
