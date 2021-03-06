# Grab-AI : Safety Challenge

# Problem Statement
Multiple Telematics data is provided for each bookingID.There are 10 datasets containing about 16,00,000 rows each and 20,018 unique bookingIDs with the label.The objective is to make a model that can detect dangerous driving trips.

# Approach
## 1) Preprocessing
  a) Grouping data : The data set contained several telematics datapoints for single bookingID.So, I grouped it by bookingID by taking the median of all the datapoints.
  
  b) Feature Engineering : I created following features.
  
    1)number_of_trips- I contains total number of trips made by a bookingID.
    2)acc_product- It is product of accelereations in x,y and z direction
    3)speed_acc_x- It is product of speed and and acceleration in x direction
    4)speed_acc_y- It is product of speed and and acceleration in y direction
    5)speed_acc_z- It is product of speed and and acceleration in z direction
    6)speed_gyro_x- It is product of speed and and gyroscope reading in x axis
    7)speed_gyro_y- It is product of speed and and acceleration reading in y axis
    8)speed_gyro_z- It is product of speed and and acceleration reading in z axis
    
  Justification for the features-
  
   1)number_of_trips- If a person makes more number of trips in a given period of time, it is very likely that he may drive fast and try to make his way through narrow spaces by taking sudden turns.
    
   The following features can give some idea about reckless driving.High speed accompanied with high acceleration in left or right direction can be dangerous.
   
   2)acc_product 
   3)speed_acc_x 
   4)speed_acc_y 
   5)speed_acc_z 
   6)speed_gyro_x 
   7)speed_gyro_y 
   8)speed_gyro_z  
  
 c) Feature Scaling- All the features were scaled using MinMaxScaler.
 
## Modeling: 
I created an ensemble of three models.

1)XGBOOST

2)Catboost

3)Catboost bagged 10 times.

Used GridsearchCV to fine tune the hyperparameters of each model.

The final ensemble model was trained on all the datasets (df1,df2....) except the df0 which was used as  a test set.

The Model achieved Roc_auc score of 0.704 on the test set.

# How to test the Model

Please specify the path of the hold-out set in markdown cell 'Add hold-out data set here' in the jupyter Notebook.
