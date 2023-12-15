# Metabolic Syndrome Prediction

## Task

My task here was to predict metabolic syndrome based on common risk factors. 

## Permutation Importance

I started by plotting permutation importance. 

![](https://github.com/Gondram/Metabolic-Syndrome-Prediction/blob/main/importances.jpg?raw=true)

I looked closer at Triglycerides and WaistCirc.

![](https://github.com/Gondram/Metabolic-Syndrome-Prediction/blob/main/violin1.jpg?raw=true)

As you can see in both cases the mean with metabolic syndrome present was much higher.

## Feature Engineering

I chose to use two methods of feature engineering. Firt I used Principal Component Analysis (PCA) to reduce the number of features. Then I used a forward selection wrapper to narrow down the features to ten.

## Neural Networks

I started by manually creating a sequential neural network model. I manually adjusted several iterations, most often attacking variance to increase the model accuracy. 

I then utilized the Keras tuner to create a model to compare.

## Models
I created several models.
- Starting KNN: I used a KNN model before any modification
- KNN w/ PCA: This is with the PCA transform applied
- KNN w/ Filter: This is where I applied a Forward selection wrapper
- Manual Neural Network
- Keras Tuned Neural Network

## Model Evaluation Metrics
Starting KNN:
~~~
                precision    recall  f1-score  

  weighted avg       0.76      0.77      0.76           

    accuracy 0.77     
~~~
~~~
 KNN w/ PCA:

                precision    recall  f1-score   
  weighted avg       0.79      0.79      0.879

    accuracy 0.79 
~~~
KNN w/ Filter:

                 precision    recall  f1-score
  weighted avg       0.83      0.82      0.82    

    accuracy  0.83 

Manual Neural Network:

                precision    recall  f1-score

  weighted avg       0.79      0.73      0.76          

    accuracy  0.84 

Keras Tuned Neural Network:

                precision    recall  f1-score

  weighted avg       0.76      0.69      0.82      

    accuracy  0.82 
    
## Recommendation

The 2 best models were the Manual Neural Network and the KNN w/ Filter. 

Based on the model accuracy and precision I recommend using the Manual Neural Network model. The KNN w/ Filter model had a similar accuracy and higher precision, but had a much higher instance of false negatives. Given the medical nature of this task I am prioritizing avoiding false negatives. 

##### I recommend the Manual Neural Network for production and/or further tweaking.
