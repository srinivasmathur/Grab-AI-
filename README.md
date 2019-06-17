# Grab-AI Safety -
This repository contains the python code along with the trained model 

# Problem Statement
The multiple Telematics data was provided for each bookingID.There are 10 datasets containing about 16,00,000 each and 20,018 unique bookingIDs with the label.The objective is to make a model that can detect dangerous driving trips.

# Approach
# 1) Preprocessing
  a)Grouping data- The data set contained several telematics datapoints for single bookingID.So, I grouped it by bookingID by taking median of all the datapoints  
