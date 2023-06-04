# Can Machine Learning Predict Fake News?

## Intro

In the hyperconnected world of social media and 24/7 news, there is more media out there than any one person can consume. Worryingly, there is a significant amount of news that is released that is either inaccurate, misleading, false, or all three. Major news publications have taken to having their own in-house fact-checkers, who can research various news articles and determine the truth-value of said articles. While it is certainly possible for fact-checkers to go through each article and determine the veracity of its contents, it would be extremely helpful if it was possible to train a model to predict whether the article was true or false. This could be used either as a pre-screening tool to flag articles more worthy of attention or as a research method into what drives fake news. If a model was accurate enough it could even be used as a built-in moderating tool for social media sites, screening out fake news before it even reaches the consumer. Some research questions I am interested in are as follows: Is it possible to predict when a news article is true or false? What words, phrases, or subjects are more likely to lead to a story being fake? Are there certain times of year where stories are more likely to be false? Is there an ethical problem with relying on a machine learning algorithm to determine what the truth is?

## The Data

The data for this project comes from Kaggle (Bisaillon 2020) and is an aggregation of around 40,000 news articles that have been categorized into True/False. Originally the data was in two separate datasets. I concatenated the two together and created an extra column that indicates if the article is True or False.

## The Analysis

For the purposes of the project, I decided to only use the text of the article as features for the model. First, I prepared the text for analysis by converting all words to lowercase, removing punctuation and special characters, removing stop words, and stemming words. I rejoined the tokenized words and added them as their own column in the original dataset. I then created the feature variable as the processed text and established the target variable as the “True” indicator. Following this, I split the data into the train and test set with an 80-20 split.

I fit a term frequency-inverse document frequency (TF-IDF) vectorizer to the features. As opposed to simple term frequency, TF-IDF also searches for the frequency of the term within all the documents available, giving a more holistic understanding of the importance of any given words.

I built two different models: a random forest classifier and a logistic regression model. I evaluated both using a confusion matrix, precision score, and ROC Curve. The model which scored the highest was then used in a cross-validation test to see how it would perform against unseen data.

The random forest classifier performed remarkably well. It had a very low rate of false predictions, with a precision score of 98.49%. The ROC Curve below illustrates just how successful this model was at predicting if the news article was fake or not. The false positive rate and the true positive rate were nearly identical.

## The Conclusions

As the above analysis shows, I was able to successfully build a model to predict the veracity of a news article in the dataset. The model performed well against the test set and in cross-validation. At this point, I can confidently say that a model can be built to predict the truth/falsity of a news article at least within the dataset.
