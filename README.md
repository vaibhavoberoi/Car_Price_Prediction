# Car_Price_Prediction
Fitting a Multiple Linear Regression model to identify the features that impact the market price of a car.

Kaggle describes the problem as follows:

Geely Auto, a Chinese automobile company aspires to dive in the US market. They want to discover the factors that affect the costing of cars in the US automobile market.

We are given a dataset with 25 possible predictors. Our aim is to identify the most significant variables in order to accurately predict the market price of a car. We fit a multiple Linear Regression on the datasetand follow a top-down approach for finalizing the predictor variables.

Below are the steps followed :
1.Data was uploaded and cleaned-checked for missing values and outliers. We performed the EDA on the data. We considered only company name as the independent variable for model building by splitting the car name. 
2. Dropped Car_ID as it was not needed in the analysis . It just shows the no of observation.
3. The car name was incorrect in the data set his we replaced it with correct name #'mazda' if x=='maxda' #'porsche' if x=='porcshce' #'toyota' if x=='toyouta' #'volkswagen' if x=='vokswagen' #'nissan' if x=='Nissan' #'volkswagen' if x=='vw'
4.Fuel System mpfi is same as mfi. Hence we made 'mpfi' if x=='mfi' in data . 
5. Engine type dohcv seemed a typo for dohc.Hence replaced it with correct name. 'dohc' if x=='dohcv'
6. Visualised the data to check the correlation among the variables. Outcome: Wheelbase and car length are highly correlated. Car length and Car width are highly correlated. Curbweight and car width are highly correlated etc . These may cause multicollinearity in the model.
7. We then checked the categorical variable. And did on hot encoding .
8. Then we splitted the data into Test and Train and performed scaling on numerical variables.
9 We then divided the data into X Train and Y train 10. We then built a linear model using -RFE. We predicted top 12 variables. ['carwidth', 'curbweight', 'enginesize', 'boreratio', 'stroke', 'CarName_bmw', 'CarName_porsche', 'enginelocation_rear', 'enginetype_rotor', 'cylindernumber_three', 'cylindernumber_twelve', 'cylindernumber_two'], 
11.We then found the model is overfitted .So we started manually. We deleted variables where the p value was high as well as the vif was high We selected the 9th model as final.

Below are the variables which are significant in predicting the price of a car: 
Enginesize, CarName_bmw, CarName_porsche, enginelocation_rear, cylindernumber_two

References:
1. Kaggle
https://www.kaggle.com/ashydv/car-price-prediction-linear-regression/data

2. Machine Learning by Andrew NG, Coursera
https://www.coursera.org/learn/machine-learning
