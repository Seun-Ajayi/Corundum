# Report: Predict Bike Sharing Demand with AutoGluon Solution
#### OLUWASEUN AJAYI

## Initial Training
### What did you realize when you tried to submit your predictions? What changes were needed to the output of the predictor to submit your results?
I had to eliminate negative values because Kaggle rejects submissions with negative values, so I applied the `.describe()` method to see the distribution of my prediction. The minimum value of the prediction is `3.090189`, so it's safe to submit because there are no negative value in my predictions.

### What was the top ranked model that performed?
The top ranked model was `WeightedEnsemble_L3` with the score `-53.171997`.

## Exploratory data analysis and feature creation
### What did the exploratory analysis find and how did you add additional features?
I carried Exploratory Data Analysis by visualizing the distribution of all features through an histogram. I found that the datetime features would be more useful if I could extract additional information about the hour, day, and month. By using these new features, I could provide a more detailed information to my model for it to learn better.

### How much better did your model preform after adding additional features and why do you think that is?
The initial RMSE score for the first model is `-53.171997`. By providing the additional features the model perfomance improved with a new score of `-30.316675`


## Hyper parameter tuning
### How much better did your model preform after trying different hyper parameters?
After trying several hyperparameter tuning, by specifying values for individual model including neural network and LightGBM models and setting the hyperparameter_tune_kwargs by playing around with num_trials, scheduler, and searcher hyperparameters, the model performance did not improve but achieved a new best score of `-36.344086`.

### If you were given more time with this dataset, where do you think you would spend more time?
I would explore the data more and carryout feature engineering for creation of new feature that would inform the model bettr and I would also try more hyperparameter tuning.

### Create a table with the models you ran, the hyperparameters modified, and the kaggle score.
|model|presets|num_bag_sets|time_limit|score|
|--|--|--|--|--|
|initial|best_quality|None|600|1.79647|
|add_features|best_quality|None|600|0.67941|
|hpo|best_quality|1|900|0.48459|

### Create a line plot showing the top model score for the three (or more) training runs during the project.

TODO: Replace the image below with your own.

![model_train_score.png](.\images\model_test_score.PNG)

### Create a line plot showing the top kaggle score for the three (or more) prediction submissions during the project.

TODO: Replace the image below with your own.

![model_test_score.png](.\images\model_kaggle_score.PNG)

## Summary
This project introduced me to AutoML using AWS Sagemaker - AutoGluon. In this project, I followed the ML workflow starting from EDA to feature angineering to model building including hyperparameter tuning. The model created predicts bike sharing demand and the model performance improved as I revisited the ML workflow to optmize the model. I am always excited to learn more about Data Science and ML tools and this project reflected this.