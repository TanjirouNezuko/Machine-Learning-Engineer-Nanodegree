# Project Components

## 1. ETL Pipeline
Extract, Transform, and Load process: Read the dataset, clean the data, and then store it in a SQLite database.

In a Python script, process_data.py, is a data cleaning pipeline that:
- Loads the messages and categories datasets
- Merges the two datasets
- Cleans the data
- Stores it in a SQLite database

## 2. ML Pipeline
Split the data into a training set and a test set. Then, create a machine learning pipeline that uses NLTK, as well as scikit-learn's Pipeline and GridSearchCV to output a final model that uses the message column to predict classifications for 36 categories (multi-output classification). Finally, export the model to a pickle file.

In a Python script, train_classifier.py, is a machine learning pipeline that:
- Loads data from the SQLite database
- Splits the dataset into training and test sets
- Builds a text processing and machine learning pipeline
- Trains and tunes a model using GridSearchCV
- Outputs results on the test set
- Exports the final model as a pickle file

## 3. Flask Web App
Provided with the flask web app template, but feel free to add extra features depending on your knowledge of flask, html, css and javascript. For this part: 
- Modify file paths for database and model as needed
- Add data visualizations using Plotly in the web app 

# File structure:
- app
  - template
    - master.html  # main page of web app
    - go.html  # classification result page of web app
  - run.py  # Flask file that runs app

- data
  - disaster_categories.csv  # data to process 
  - disaster_messages.csv  # data to process
  - process_data.py
  - InsertDatabaseName.db   # database to save clean data to

- models
  - train_classifier.py
  - classifier.pkl  # saved model 

- README.md

# Model Results: 

precision    recall  f1-score   support

               related       0.86      0.81      0.83      1356
               request       0.79      0.70      0.74       727
                 offer       0.00      0.00      0.00         2
           aid_related       0.80      0.71      0.75       775
          medical_help       0.55      0.29      0.38       100
      medical_products       0.63      0.31      0.41        62
     search_and_rescue       0.39      0.17      0.24        41
              security       0.00      0.00      0.00        29
              military       0.20      0.20      0.20        10
           child_alone       0.00      0.00      0.00         0
                 water       0.85      0.83      0.84       167
                  food       0.87      0.86      0.87       301
               shelter       0.75      0.67      0.71       210
              clothing       0.64      0.56      0.60        16
                 money       0.67      0.32      0.43        25
        missing_people       0.00      0.00      0.00        15
              refugees       0.27      0.09      0.14        33
                 death       0.52      0.29      0.38        41
             other_aid       0.54      0.29      0.38       295
infrastructure_related       0.47      0.08      0.14        87
             transport       0.00      0.00      0.00        33
             buildings       0.56      0.39      0.46        76
           electricity       0.20      0.05      0.08        21
                 tools       0.00      0.00      0.00         6
             hospitals       0.14      0.06      0.09        16
                 shops       0.00      0.00      0.00        12
           aid_centers       0.67      0.08      0.15        24
  other_infrastructure       0.33      0.12      0.17        43
       weather_related       0.83      0.55      0.66       289
                floods       0.67      0.29      0.40        42
                 storm       0.65      0.37      0.47        59
                  fire       0.00      0.00      0.00         8
            earthquake       0.88      0.68      0.77       164
                  cold       0.33      0.10      0.15        10
         other_weather       0.00      0.00      0.00        43
         direct_report       0.75      0.69      0.72       698

           avg / total       0.74      0.63      0.68      5836
