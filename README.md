# wine_recommender

This is a wine recommender project that I'm proposing for the Data Incubator Fellowship application. I would like to create a hybrid recommender engine that people can use while they are in tasting rooms. I envision an engine that can connect to a wine rating app, such as Hello Vino, or can take wines or wine characteristics as input. When given the tasting room menu (such as through a URL), it will be able to predict the person's ratings for the wines and the user can plan their tasting accordingly. Currently, I am working with the wine.com API to get my data.

Files:  
(Jupyter Notebooks are in chronological order)  
testing_wine_api.ipynb - a Jupyter Notebook that I used to explore the wine.com API  
creating_database.ipynb - a Jupyter Notebook that I used to refine data collection from the API, clean the data, and do some initial data exploration

Comments on the scores:  
I am not able to access the user ratings through the API yet, but I am able to access the highest professional rating of each wine. This is in the 'Score' column of the main_wines database. Presumably, these come form a pool of several "users" (the professional raters). Looking at "Boxplot grouped by Varietal Name" in data_exploration.ipynb, you see that the boxplots are fairly homogenous, indicating that the region does not make much difference in the rating. This justifies my endeavor because the region does not help determine which wines the user will like, i.e. just because you are in Italy, it does not mean you will like the wines. What does make a difference is the varietal, as seen in "Boxplot grouped by Region Name" in data_exploration.ipynb. There is a lot of scatter in the scores, with a number of outliers. This shows that varietal, combined with users, can help to determine wines that a person will like. This is why I believe a hybrid engine will work for this project.