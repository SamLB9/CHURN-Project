# CHURN-Project
# Analyze and predict service churn

A start-up sent me a dataset with information on all current and past customers who have subscribed to their services. This dataset contained a boolean variable 'IS_CHURN' with a value of 1 when the customer is still a subscriber and 0 otherwise. 
From this dataframe, I was able to make a classification with 'IS_CHURN' as the explained variable, and as explanatory variables the size of the customer's company, the length of time they've been a subscriber, the number of visits to their site, their conversion rate, the total amount paid for the service and other variables...

Here's what the dataset looks like:

![](https://github.com/Mougly9/CHURN-Project/blob/main/Dataframe%20visualization.png)

Before I could run the classification model, I had to clean up the data by deleting rows in the dataframe with missing values in the columns of interest, making a qualitative variable numeric and changing the type of a variable.

As a result, I was first able to analyze the rate of customers unsubscribed to services in the dataframe. 36.5% of customers have unsubscribed since the creation of the services.

After splitting the data into 4 (X_train, X_test, y_train and y_test), I was finally able to run the classification model, using the RandomForestClassifier() function from the sklearn library. 
Thanks to the fitted attribute feature_importances_, I was able to rank the most important variables in the model to assess whether a customer still subscribes to the services or not.

Here's the ranking illustrated by a histogram:

![](https://github.com/Mougly9/CHURN-Project/blob/main/Ranking%20importance%20bar%20chart.png)

I was now able to predict whether or not a customer had unsubscribed from the services, and thus measure the model's performance.

It is now interesting to measure the probability that a customer currently subscribed to the services will unsubscribe in the future. 
To do this, I've created a dataframe containing only customers who are still subscribers, and added a new variable symbolizing this probability.

Here's what this DataFrame looks like:

![](https://github.com/Mougly9/CHURN-Project/blob/main/Clients%20churn%20probability.png)

I also thought it would be interesting to analyze the relationships between the variables, and especially the relationship between the variable representing the probability of subscriber churn and the model's explanatory variables.

Here's a correlation matrix to help us to analyze that:

![](https://github.com/Mougly9/CHURN-Project/blob/main/Correlation%20matrix.png)

