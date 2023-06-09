# IBM Applied Data Science Capstone Project
## Executive Summary
In this capstone project, my main adjective was to predict if the SpaceX Falcon 9,  will land successfully using machine learning techniques and past data.
The steps were as follows:
- Data collection, data wrangling, data formatting
- Exploratory data analysis
- Data visualization
- Machine learning prediction

We concluded that using a decision tree model would be the most accurate prediction model based on our training and test set.

## Introduction
In this capstone project, we will be predicting if the Falcon 9 rocket will land successfully. The Falcon 9 project is revolutionary because its cost is substantially cheaper than it would be for other competitor rockets. It costs 62 million to produce while others cost around 150 million. The reason it can save so much money is because of its ability to reuse the first stage.
What we are trying to answer is, for a set of features on the Falcon 9 rocket such as payload mass, orbit type, launch type, etc… will the rocket land successfully?

## Methodology
The overall methodology is as follows:
1) Data collection, wrangling, and formatting
- SpaceX API
- Web scraping
2) Exploratory data analysis (EDA)
- Pandas
- NumPy
- SQL
3) Data visualization
- Maplotlib
- Seaborn
- Folium
- Dash
4) Machine learning prediction
- Logistic regression
- Support vector machines (SVM)
- Decision tree
- K-nearest neighbors (KNN)

## Data Collection using SpaceX API
https://github.com/SamWeller3/IBM-Capstone-Project/blob/main/Data%20Collection%20though%20APIs.ipynb

The API used is: https://api.spacexdata.com/v4/launches/pa

Libraries/modules used: requests, pandas, numpy, datetime
- The API provides data about many types of rocket launches done by SpaceX, however we filtered the data to only give us data about Falcon 9 launches
- We use the json_normalize() function in python to convert everything intp json format
- Missing values are replaced with the mean of the column in belongs to
- We end up with 90 rows and 17 columns

## Data Collection with Web Scraping
https://github.com/SamWeller3/IBM-Capstone-Project/blob/main/Data%20Collection%20with%20Web%20Scraping.ipynb

Libraries or modules used: sys, requests, BeautifulSoup from bs4, re, unicodedata, pandas

- Data scraped from: List of Falcon 9 and Falcon Heavy launches – Wikipedia
- Website only contains data from Falcon 9 launches so no filtering is needed in that regard
- Use column/variable names from the HTML table using the find_all() function from BeautifulSoup
- A dataframe is then created with the extracted column names and entries filled with launch records that are extracted from table rows
- We end up with 121 rows (instances) and 11 columns (features)

## EDA with Pandas and Numpy
https://github.com/SamWeller3/IBM-Capstone-Project/blob/main/Data%20Wrangling.ipynb

Libraries or modules used: pandas, numpy, math

Functions from the Pandas and NumPy libraries such as value_counts() are used to derive basic information about the data collected, which includes:
- Number of launches for each launch site
- Number of occurences of each orbit
- Number and occurence of each mission outcome

## EDA with SQL
https://github.com/SamWeller3/IBM-Capstone-Project/blob/main/Exploratory%20Analysis%20with%20SQL.ipynb

Framework used: IBM DB2

Libraries or modules used: ibm_db

The data is queried using SQL to answer questions about the data such as:
- Names of unique launch sites
- Total payload mass carried by boosters by NASA
- Average payload mass carried by booster version F9 v1.1

The SQL statements used include: SELECT, DISTINCT, AS, FROM, WHERE, LIMIT, LIKE, SUM(), AVG(), MIN(), BETWEEN, COUNT(), and YEAR().

## Data Visualization using Matplotlib and Seaborn
https://github.com/SamWeller3/IBM-Capstone-Project/blob/main/SQL%20Visualizations.ipynb

Libraries or modules used: pandas, numpy, matplotlib.pyplot, seaborn

We created visualizations to understand the relationships between:
- Flight number and launch site
- Payload mass and launch site
- Success rate and orbit type

Functions use include are scatterplot(), barplot(), catplot(), and lineplot()

Example:


![image](https://user-images.githubusercontent.com/123184681/236897690-f2322f75-3fef-4dba-99ef-69767bdb9e22.png)


## Data Visualization using Folium
https://github.com/SamWeller3/IBM-Capstone-Project/blob/main/Data%20Visualization%20with%20Folium.ipynb

Libraries or modules used: folium, wget, pandas

We used Folium libraries to visualize data such as:
- Mark all launch sites on a map
- Mark the failed and sucessful launch sites
- Mark distances from the launch sites to the clostest hazard such as roads or cities

Example: Map showing failed and suceeded launches at a particular launch site

![image](https://github.com/SamWeller3/IBM-Capstone-Project/assets/123184681/86913292-2ad7-4649-b8c2-6688733c60ab)


## Machine Learning Prediction
https://github.com/SamWeller3/IBM-Capstone-Project/blob/main/Machine%20Learning%20%26%20Prediction.ipynb

Libraries or modules used: pandas, numpy, matplotlib.pyplot, seaborn, sklearn

We used function from the Scikit-learn library to create our machine learning models. The machine learning prediction phase took on the following steps:

1. Standardizing the data using the preprocessing.StandardScaler() function from sklearn
2. Splitting data into training and test sets
3. Creating four machine learning models which include logistic regression, support vector machine, decision tree, and K nearest neighbors
4. Fitting the models to the training set
5. Computing the accuracy based on how close it is to the test set and finding out which model worked the best

When comparing them all of them side by side, we look at the GridSearchCV score to predict accuracy and get the following results:
- Decision Tree: 0.8893
- K nearest neighbors (KNN): 0.8482
- Support vector machine (SVM): 0.8482
- Logistic Regression: 0.8464

As we can see, the decision tree has the highest score meaning it is the most accurate training model when compared to the test set. 

Decision tree's training model:

![image](https://github.com/SamWeller3/IBM-Capstone-Project/assets/123184681/67be4b14-6e51-4fb6-bea3-8e49ee6fe4ec)


## Conclusion 

The adjective of the project was to predict if the Falcon 9 launch will land or not based on variables such as launch site and payload mass. This was to help determine the launch of the cost and the likelyhood of the launch being successful. We used several machine learning algorithms and deployed them side by side to see which one works the best. We eventually decided that the decision tree model worked the best based on the test set.

