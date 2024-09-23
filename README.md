# Capstone Project - September 2024 - Professional Certificate in Machine Learning and Artificial Intelligence - Imperial College
Optimising and predicting the time of arrival for time critical deliveries

## NON-TECHNICAL EXPLANATION OF YOUR PROJECT
In the delivery business getting goods to the right place at the agreed time is critical. The aim of this project is to build an optimisation model based on historic data and taking into account all of the factors that can affect the delivery time including but not limited to travel distance, type of products being shipped, transport method and driver charateristics (popularity and age) and of course the weather to help predict delivery times more accuratly. The focus of this exercise was on the travel time and not the time spent after the order was recieved until delivery. (Cooking time in the case of the Zomato food delivery data was not to be taken into account.)

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
With 6 algorthms to compare, each optimisations hyper parameters are considered in turn

### Linear Regression
There is little tuning to be done on the LinerRegression.
Changing fit_intercept=False has a very negative impact on the performance

### GridSeachCV
The nature of gridsearch means that it is the function that identifies the best parameters from those made available.
The chosen paramters to investigate were "alpha" and "Solver" and the best values were alpha of 10, Solver of Saga.

### Bayesian Optimisation - Random Forest
Utilising Random Forest the key parameters changed were n_estimators (10,500) max_depth list(range(1,11)) min_samples_split': (2, 80)

Having these values gave the best output, although reducing the values did worsen the output it wasn't too significant meaning the RandomForest was performing quite well for the given data.

The output from the BayesianSearchCV was max_depth = 11 min_sample_split = 18 n_estimators = 260

### Bayesian Optimisation using SVR
This process was extremly slow. Therefore given the limited time some compromised and assumptions had to be made.
The inital runs were set with a cv as 5 and n_iter as 5. Any higher values were taking far to long (hours) to respond. These runs were executed with the:-
1. 'C': (0.1, 1000),  # Regularization parameter
2. 'epsilon': (0.01, 0.5),  # Epsilon in the epsilon-SVR model
3. 'kernel': ['linear', 'poly', 'rbf', 'sigmoid'],  # Kernel type

The output was then
1. 'C', 837.404616717729
2. 'epsilon', 0.4428244859166225
3. 'kernel', 'poly'

These values were then hard coded to allow maniuplation of CV and n_iter but the performance did not change measurably.

### Bayesian Optimisation using K-Nearest Neighbour

The algorithm ran with the variables sets as shown below. This algoirthm ran quite quickly so no need to reduce the scope of the tuning when running.

1. 'n_neighbors': (1, 30),  # Number of neighbors
2. 'weights': ['uniform', 'distance'],  # Weight function used in prediction
3. 'algorithm': ['auto', 'ball_tree', 'kd_tree', 'brute'],  # Algorithm used to compute the nearest neighbors}

The output showed that:- 

1. algorithm = 'auto'
2. n_neighbours = 13,
3. weights = distance

A cv of 5 abnd n_iter of 50 performed well

### Neural Network

Before tuning started the random.seed was set to 42 to bring some consistency to the results. 

Various values were tried for the Neural network model with respect to the number of nodes including adding more hidden layers and adjusting the number of nodes in each layer. The combination that gave the best performance has 3 hidden layers. The input layer has 64 nodes, the first two hidden layers have 32 nodes and the last hidden layer has 16 nodes. The output layer has 1 node.

Changing the learning rate initialised at 0.001 to smaller or larger values only reduced the performance of the network.

Changing the batch size from 32 to 64 gave some improvement with a Test Loss : 33.3818 and a Test MAE : 4.681

Changing the epoch size from 100 to 200 gave some improvement with a Test Loss : 33.0583 and a Test MAE : 4.641 Other values of epoch seemed to worsen the output although not signficantly. Dropping the epochs below 50 made a large negative difference.

Substituing ReLU with PReLU and LeakyReLU did not improve the result even when changing the alpha value of LeakyReLU.

SGD and RMSProp were tried as optimisers but neither, even with parameter changes could out-perform Adam

## RESULTS

The results are shown in detail in the juypter notebook including graphs of the feature importance.

Results can be split into three categories
1. The performance of each of the optimisations (calculated in the execution and presented at the end of the Jupyter Notebook
2. The relvance of the features including a summary (Summary Graphs after each optimisation and a combined graphs at the end of the Jupyter Notebook)
3. The summary and implications in business language

### Performance of the optimisations

----Optimization Type-------------RMSE
1. Linear Regression-------------7.054342
2. GridSearchCV using Ridge-----7.053524
3. BayesSearch Random Forest--5.408481
4. BayesSearch SVR-------------6.516862
5. BayesSearch KNearest--------6.791588
6. Neural Network---------------5.749636

Therefore, BayesSeachCV with Random Forest and the Neural network performed the best although they actually didn't rank the features equally.

### The relvance of the features in the dataset

The top six features in order of relevance are

1. Distance (to be expected)
2. Road Traffic Density - Jams
3. Delivery Person Age
4. Road Traffic Density = Low
5. Delivery Person Rating
6. Vehicle Condition

In the Jupyter notebook the full break down is shown with the relevant scores.

### Implications for the Business User

The distance being the biggest influencing factor could have been predicted but the delivery persons age and rating proved for more important that other factors.

Weather also was signifcant but sandstorms for example did not appear to influence greatly probably due to very few data items.

There were also items that had almost no impact of the predictability of the times namely the environments the travel was in e.g. metropolitan or rural which was surprising but less surprising was the tyupe of food being transported.

The type of food played very little signficance in any of the optimisation so could probably be dropped from the data set to help increase the performance.

Running the multiple Optimisations and also looking at the average rankings of the results means that there can be confidence in the findings.

However, also note that 


## (OPTIONAL: CONTACT DETAILS)
I can be found on linkedIn at www.linkedin.com/in/antony-cotterill-a8aa453
