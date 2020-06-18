# SG Apartment Resale Price Estimator

## Introduction

The Housing and Development Board (HDB) is a state controlled authority that is responsible for public housing in Singapore. They develop and maintain a large variety of flat types and layouts catering to different house budgets. 

Singapore Citizens can lease out these flats for a period of 99 years. But for permanent residents, they can make purchase only from the secondary resale market. And we can see that there is a thriving market for the resale of the HDB flats with nearly 1500 transactions happening every month.

Since there is no stipulated method for determining the resale price, it is vital that the buyer is able to gauge the real value of the property so that they are able to negotiate properly for the sale. It can also help the seller to set a reasonable price for the sale.

Here, we are building an accurate predictor for the resale price based on the data available on previous sales.

## Data Description

The predictor is built on the data provided on the HDB webiste for sales made between Q1 2017 – Q1 2020. A basic overview of the original data is given in the picture below.

**image 1**

The dataset contained records on 70104 resale transactions that happened during this period.

## Methodology

The dataset was analysed using different visualisations and by using various statistical indexes. Based on the analysis, a set of relevant features were selected (some of the exisiting features were transfromed appropriately and new features were engineered) and were used for building the model.

The selected set of features can be see in the picture appended below.

![Final Dataframe](https://github.com/muhammedsalihk/SG-Apartment-Resale-Price-Estimator/blob/master/Images/Final%20DF.png)

The data was divided into two sets (train and test) in an 80-20 ratio. Multiple regressors were tried and for each regressor, the hyperparameters were tuned based on a 4 fold cross validation approach using sklearn’s GridSearchCV. Finally, the performance of the different models with the tuned set of hyperparameters were evaluated on the test set.

The evaluation metric used for determining the performance of the models was R2 score. The coefficent of variation (std. deviation/mean or in other words mean squared error / mean of the values) was also kept track of so that a more intutive measure of the performance could be obtained. Please note that the choices were made solely on the basis of the R2 score.

## Results

The following models were evaluated for performance.

    1. Ridge Regression
    2. Lasso Regression
    3. Decision Tree Regressor
    4. Random Forest Regressor
    5. Gradient Boosting Regressor
    6. XGBoost Regressor

The performance of the different models are summarised below.

**image 3**

The **XGBoost Regressor** performed the best and gave an **R2 score of nearly 0.95** on the test set. And hence we can go ahead and use the model built using XG boost for our HDB resale price predictor.
