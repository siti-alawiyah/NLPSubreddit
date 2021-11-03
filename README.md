

# ![](https://ga-dash.s3.amazonaws.com/production/assets/logo-9f88ae6c9c3871690e33280fcf557f33.png) **Project 3: Web API s & NLP**

### Objective of the Project:

Use Pushshift API to collect 2 subreddits category: 

* [Makeup](https://www.reddit.com/r/Makeup/) 
* [Fragrance](https://www.reddit.com/r/fragrance/)

Use NLP to train classifier on which subreddit a post has been given to. 

* 1st Classifier: RandomForestClassifier with GridsearchCv
* 2nd Classifier: Naive Bayes with GridsearchCV 

### Summary of EDA

#### Word Cloud for Makeup Subreddit

![](https://github.com/siti-alawiyah/projects/blob/master/Project_3%20NLP%20and%20webscrapping%20on%20Subreddit/Images/makeup%20word%20cloud.png)

#### Word Cloud for Fragrance Subreddit

![](https://github.com/siti-alawiyah/projects/blob/master/Project_3%20NLP%20and%20webscrapping%20on%20Subreddit/Images/fragrance%20word%20cloud.png)

## Modelling Process

Makeup and Fragrance Subreddit are combined into 1 dataframe: df_

Function called preprocess to do the following:

* lowercase text
* remove whitespace
* remove numbers
* remove special characters
* remove emails
* remove stop words
* remove additional stopwords such as: makeup and fragrance
* remove NAN
* remove weblinks
* tokenize

select columns: subreddit and cleanmsg to be put to modelling

convert fragrance: 0, makeup 1 as their binary labels



## Results

### RandomForestClassifier

Best Parameters: ![](https://github.com/siti-alawiyah/projects/blob/master/Project_3%20NLP%20and%20webscrapping%20on%20Subreddit/Images/rf%20bestparams.png)

Results:![](https://github.com/siti-alawiyah/projects/blob/master/Project_3%20NLP%20and%20webscrapping%20on%20Subreddit/Images/rf%20results.png)

### Naive Bayes

Best Parameters: 

![](https://github.com/siti-alawiyah/projects/blob/master/Project_3%20NLP%20and%20webscrapping%20on%20Subreddit/Images/nb%20bestparams.png)

Results:

![](https://github.com/siti-alawiyah/projects/blob/master/Project_3%20NLP%20and%20webscrapping%20on%20Subreddit/Images/nb%20results.png)

## Conclusion and Future Work

### Conclusion

•All models can classify which subreddit a post has been given to.

•Best model recommendation: Naive Bayes

​	• difference between the test/training AUC score and accuracy score is less than 0.01 

​	•AUC score and accuracy score is also the highest

​	• Lower false negative and false positive

​	• Higher Recall(True Positive rate) 



### Future Work:

* Explore other model such as GradientBoosting/Logistic Regression
* Remove top features that was given by RandomForest and re-run to explore if the classifier are able to classify which post belongs to which subreddit
#NLPSubreddit
