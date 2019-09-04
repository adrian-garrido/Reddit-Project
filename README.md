### REDDIT PROJECT ###

### Executive Summary

User engagement is the core of Reddit's success. We have some of the most engaged users in the industry, and are now the social platform with the third biggest amount of users per month. But improvements can always be made. By providing users with better recommendations to other similar subreddits, we can extend the time they spend on our platform substantially.

I created an automatic process that compares two subreddits and calculates a score based on how similar their posts are. With this we can create a system that identifies similar subreddits that can be recommended to the user in each subreddit. This has the potential to keep users in our platform for a longer period of time, increasing our advertising value.

### Objective

Creating a simple function that takes the names of 2 subreddits, collects data from each subreddit, and creates multiple models that predict wether a post comes from one subreddit or the other.

#### Data Collection

Using Reddit's API, the function collects a maximum of 1,000 posts from each subreddit. Then it extracts the title and text from each post, combining them into one long string.

### Data Cleaning

Using RegEx, urls, mentions of other subreddits, numbers, and special characters were removed.

### Transforming data

Count Vectorizer and Tfidf Vectorizer were used to transformed the data so it could be interpreted by the models.

### Models

The function instantiates and fits three different models.

The first one is a Logistic Regression model and uses the Count Vectorizer transformer.

The second one is a Random Forest Classifier model and uses the Tfidf Vectorizer transformer. This model was also ran through a Grid Search CV, in order to test out different hyperparameters and find the most optimal ones.

The last one is a Multinomial Naive Bayes model and uses the Count Vectorizer transformer.

### Function Outputs

The function gives feedback during each process. It also checks for errors in the data, it checks to see if there is enough posts, and warns the user if the classes used are unbalanced. Finally, it provides scores for each of the models as well as a list of the most important words according to Tfidf Vectorizer.
