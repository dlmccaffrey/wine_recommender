# wine_recommender

This is a wine recommender project that I'm proposing for the Data Incubator Fellowship application. I would like to create a hybrid recommender engine that people can use while they are in tasting rooms. I envision an engine that can connect to a wine rating app, such as Hello Vino, or can take wines or wine characteristics as input. When given the tasting room menu (such as through a URL), it will be able to predict the person's ratings for the wines and the user can plan their tasting accordingly. Currently, I am working with the wine.com API to get my data.

**Files:**  
(Jupyter Notebooks are in chronological order)  
testing_wine_api.ipynb - a Jupyter Notebook that I used to explore the wine.com API  
creating_database.ipynb - a Jupyter Notebook that I used to refine data collection from the API, clean the data, and do some initial data exploration  
uci_data_testing/testing_recommender.ipynb - a Jupyter Notebook that I used to test out the recommender algorithm from the LightFM module  
uci_data_testing/code_for_app.ipynb - a Jupyter Notebook that used what I learned about LightFM to create code that is more suitable for the application

**Comments on the scores:**  
I am not able to access the user ratings through the API yet, but I am able to access the highest professional rating of each wine. This is in the 'Score' column of the main_wines database. Presumably, these come form a pool of several "users" (the professional raters). Looking at "Boxplot grouped by Varietal Name" in data_exploration.ipynb, you see that the boxplots are fairly homogenous, indicating that the region does not make much difference in the rating. This justifies my endeavor because the region does not help determine which wines the user will like, i.e. just because you are in Italy, it does not mean you will like the wines. What does make a difference is the varietal, as seen in "Boxplot grouped by Region Name" in data_exploration.ipynb. There is a lot of scatter in the scores, with a number of outliers. This shows that varietal, combined with users, can help to determine wines that a person will like. This is why I believe a hybrid engine will work for this project.

**Update 11/13/16:**  
I have not heard back from Wine.com about getting full access to the API and I feel it would be rude to start scraping so soon, so I am testing out the code for the recommender with the Wine Quality dataset from UCI Machine Learning repository: https://archive.ics.uci.edu/ml/datasets/Wine+Quality

The recommender I'm using is a hybrid engine implemented in the LightFm Python module: http://lyst.github.io/lightfm/docs/home.html

The data only has one column of ratings, so I'm not able to make a true recommender system, but it does have many feature variables. I synthesized some data for testing purposes and used the features to create working code for the app.

Out of respect for the researchers, I have not put any data files on github, only the Jupyter notebooks. The uci_data_testing/testing_recommender.ipynb notebook has all the links for finding the correct data.