# Project 3 - NLP Subreddit Post Classifier

---
# Executive Summary

Reddit is a social news aggregation, content rating and discussion website, where users can submit content to the site such as links, text posts, images and videos, which are then voted up or down by other members. Posts are organized by subject into user-created boards called "communities" or "subreddits". As reddit has different user-created boards called sub-reddits, each sub-reddit contains a specific topic which the users can post Questions, Comments, and Answers to.

There are a wide range of topics on reddit, from simple topics like "askreddit", where anyone can ask a question and get their answers, to more complex topics like "learnmachinelearning", where one can learn about machine learning, and even fun topics like fat cats from "Chonkers". This wide range of sub-reddits is a great way to anyone to learn and gain knowledge about a specific topic.

As a avivd user of Reddit, I have explored the different data science related sub-reddits to understand what data science is about. There are How-to-start posts where links/guides are given to help anyone interested in the topic. These said posts have helped me out when I was starting out to learn about data science, and especially on learning how to code in python. In particular, learningpython has helped me to understand more about python programming language and places where I can learn how to code, and learningmachinelearning has helped me to understand deeper on what machine-learning is, and how it is related to data science in general.

Hence, I have decided to build a classifier model to classify posts about these 2 sub-reddits. The classifier model will be based on the content of the posts, and will be able to classify the posts into 2 categories - "learn python" and "learn machine learning".

One of the use cases is that anyone can post anything into the sub-reddits, this classification model may help to suggest to the user if the question they want to ask is placed in the correct sub-reddit.

---
## Steps Taken
1. Extraction of data via PushShift API
2. Data Analysis of the data extracted
   1. Date of the posts
   2. Word count of the title and selftext
   3. Further investigation of outliers
3. Data Cleaning/ Feature Engineering
   1. Combination of title and selftext
4. Data Modeling and Pre-processing of the data
   1. Data Modeling was done via pipeline, which includes data processing in the column transformer step
   2. Total 6 models were used, and they were used for each Count Vectorizer and Tfidf Vectorizer = 12 models in total
5. Results Evaluation
   1. Results were evaluated using both the accuracy score and ROC AUC score between the train and test sets
   2. The best models were selected for each Count Vectorizer and Tfidf Vectorizer
   3. Best model for Count Vectorizer = SGDClassifier
   4. Best model for TFIDF Vectorizer = xGBoostClassifier
6. Performance of the model against the unseen data
   1. Using the above 2 models for count vectorizer and tfidf vectorizer, the performance of the model against the unseen data was evaluated.

---
# Conclusions/Recommendations
## **Conclusions:**
1. Both countvectorizer and tfidfvectorizer are viable methods for the modeling process.
2. From result evaluation, most models are able to perform well, with exceptional generalisation from SGDClassifier and boosting algorithms (Adaboost and xGBoost).

## **Recommendations:**
1. The model is not perfect, as spam posts were removed from the data. In reality, there would always be spam posts. Further improvement/modeling can be done to include the classification of the spam posts.
2. Different sub-reddits can be used and tested on, as the chosen subreddits are quite different, which generally gave all models very good generalisation.