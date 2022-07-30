
# Title : Car Price Prediction.

welcome to my project, I'm Irvan Sikajudin, a Data Science enthusiast, this project contains several processes, starting from Data Understanding, EDA, Deep dive EDA, Data Preprocessing, Split Data to Train data and Test Data then train several models that are considered suitable with existing data.


<h1>About Data</h1>
With the rise in the variety of cars with differentiated capabilities and features such as model, production year, category, brand, fuel type, engine volume, mileage, cylinders, colour, airbags and many more, we are bringing a car price prediction challenge for all. We all aspire to own a car within budget with the best features available. To solve the price problem we have created a dataset of 19237 for the training dataset and 8245 for the test dataset.

<h1>Dataset Description</h1>
Train.csv - 19237 rows x 18 columns (Includes Price Columns as Target)
Attributes
ID
Price: price of the care(Target Column)
Levy
Manufacturer
Model
Prod. year
Category
Leather interior
Fuel type
Engine volume
Mileage
Cylinders
Gear box type
Drive wheels
Doors
Wheel
Color
Airbags</br>

Test.csv - 8245 rows x 17 columns</br>
Source of Data MATHCO.THON: The Data Scientist Hiring Hackathon by TheMathCompany


Brief summary of the Solution implemented:
----------------------------------------------------------------------------------
1. Loaded the train data set and did basic data cleaning and feature engineering.
2. Having more number of categorical features, used LabelEncoder and OneHotEncoder method from sklearn.
3. Visualized all the columns using both histogram and boxplot to check the presence of outliers and did outlier treatment using "Interquartile range method" or IQR method.
4. Visualized the correlation among all the features, dropped the one feature "Cylinders" which has more positive correlation with the "Engine volume" column and the latter one is enough to explain the importance of the feature.
5. Built a linear regression model, during the residual analysis found that Linear regression assumptions are not completely followed. The R2 scores of both the train and test data are very low i.e, in the range of 18-19% and the root mean squared log error (RMSLE) of both the train and test data are in the range of 16-17% respectively.
6. As per the residual analysis, the linear regression, Lasso and Ridge regression model are not a best choice to do solve this multivariate regression problem. Hence, tried with Decision tree regressor and Random forest regressor algorithm.
7. After experimenting with all the hyperparameters, got this combo (max_depth = 20, min_samples_leaf = 5, criterion = 'friedman_mse'), Decission tree algorithm got an R2 scores of both the train and test data are  95% and the root mean squared log error (RMSLE) of both the train and test data are in the range of 4% respectively. and the Random Forest algorithm got an R2 scores of both the train and test data are 96% and the root mean squared log error (RMSLE) of both the train and test data are in the range of 3% respectively.
8. Saved the model to local disk using joblib library.
9. Then loaded the actual test data, did similar data cleaning and feature engineering, and made predictions using the decision tree regressor model that we built on the training data.

