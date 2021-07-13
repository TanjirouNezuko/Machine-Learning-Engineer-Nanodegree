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


