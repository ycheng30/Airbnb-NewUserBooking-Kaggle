
Competition:
-------------------------------
https://www.kaggle.com/c/airbnb-recruiting-new-user-bookings


Where to find the original data:
-------------------------------
https://www.kaggle.com/c/airbnb-recruiting-new-user-bookings/data


About the competition:
-------------------------------
An important characteristic of this competition is that there is a time cut-off
between training and testing data -- training data end on 7/1/2014, and testing
data start on that data. Moreover, the session informations are available only 
for the data points after 2014. 

For this competition I used 4 classifiers: (1) XGB trained on all (training) data, (2)
RandomForests trained on all data, (3) XGB classifier trained on recent 
(aka fresh) data only, and  (4) RandomForests trained on fresh data only.
The results from each clasifier formed the final prediction via weighted voting. 


Module Description:
-------------------------------

(1) feature_extraction_sessions.py:
    This will extract frequency counts from the “sessions.csv” data (which encodes the 
    web sessions log for users).
    The extracted features will be saved in the code directory. 

(2) data_preparation.py:
    This will make the data ready for the classifiers.
    The data processing includes:
        — Dealing with missing data.
        - Applying one-hot-encoding to categorical features.
        - Parsing dates (and extraction of simple numerical features).
        - Adding to the training and testing data the features that
          were extracted from sessions.csv file in the previous step.

(3) prediction.py:
    This will use the output of the previous step, to do the predictions.
    The final predictions will be saved in a file called 
    'final_prediction.csv' 
