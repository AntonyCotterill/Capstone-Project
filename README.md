# Capstone Project - September 2024 - Professional Certificate in Machine Learning and Artificial Intelligence - Imperial College
Optimising and predicting the time of arrival for time critical deliveries

## NON-TECHNICAL EXPLANATION OF YOUR PROJECT
In the delivery business getting goods to the right place at the agreed time is critical. The aim of this project is to build an optimisation model based on historic data and taking into account all of the factors that can affect the delivery time including but not limited to travel distance, type of products being shipped, transport method and driver charateristics (popularity and age) and of course the weather to help predict delivery times more accuratly. The focus of this exercise was on the travel time so this had to be extrapolated from the end to end ordering times.

## DATA
Working for DHL we have a lot of data however it is also confidential. Therefore, the data used is from Kaggle and is a good representation of the type of data we work with with DHL. The data file is called the Zomato Dataset.csv. It can be found in this repository.

The dataset can also be referenced on kaggle following the link: https://www.kaggle.com/datasets/saurabhbadole/zomato-delivery-operations-analytics-dataset

## MODEL 
I am keen to understand how different models can perform for the same data. Therefore I employed a strategy of using 6 differnt optimisations to see how they could perform. After cleaning the data, and removing about 1/3 of the initial 45,000 records due to cleaning, the same data set was then optimised using the following alogorithms.
1. Linear Regresion
2. GridSearch
3. Bayesian Optimisation using Random Forest
4. Bayesian Optimisation using SVR
5. Bayesian Optimisation using K-Nearest Neighbour
6. Neural Network

Each of the alogorithms were tuned and all executed against the same dataset. Performance results were captured against each algorithm and also the features that that drove each optimisation. At the end of the Juypter Notebook the features are ranked as to their respective performance.

## HYPERPARAMETER OPTIMSATION
Description of which hyperparameters you have and how you chose to optimise them. 

## RESULTS
A summary of your results and what you can learn from your model 

## (OPTIONAL: CONTACT DETAILS)
I can be found on linkedIn at www.linkedin.com/in/antony-cotterill-a8aa453
