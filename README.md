# Alphabet Soup Charity Success Analysis

## Overview

This analysis uses a deep neural network model to predict which charity organizations will best use funds for their proposed projects.

## Results

### Data Preprocessing

![Final Table](images/table.PNG)

The  target variable is the column **IS_SUCCESS**. It is a binary variable, true or false, indicates if the charity successfully used the money granted to it.

The remaining 8 variables in the above table are features for the neural network model.

Three columns, EIN, STATUS, and SPECIAL_CONSIDERATIONS were dropped during preprocessing.
    - EIN was a unique record identifier and provides no information.
    - STATUS and SPECIAL_CONSIDERATIONS were heavily skewed to one categorical variable and provide no useful information. 

![STATUS and SPECIAL_CONSIDERATIONS](images/no_info_columns.PNG)

### Compiling, Training, and Evaluating the Model

The neural network was constructed as follows:

    - Neurons: Used the 2 to 3 times neuron per feature general rule for each which gives 640 neurons
    - Layers: Applied two neuron layers to search for primary and secondary features in the data
    - Activation Functions:
        - Hidden Layers: Used Relu activiation function. Simple and works in most scenarios.
        - Output Layer: Goal of the model is to output a binary value, therefore Sigmoid was selected

Using the neural network structure listed above, and bucketing the charity names,  final model achieved about 78% accuracy.

## Summary

To reach an accuracy of 78%, the name of the charity must be provided otherwise the accuracy falls to 73%. 

Given that a charities history is needed for the model to achieved 78% accrucay, this implies that the model would bias new unknown charities making a request for money as they would have no history in the model.

A logistic regression should be considered to replaced the neural network modeld, thus reducing the time needed to fit.
