WeRateDogs
A Data-Wrangling project by Shaimaa Badawy as part of Udacity's Data Analysis Nanodegree funded by itida

## Table of Contents

- Introduction
- Gathering Data
- Assessing Data
- Cleaning Data
- Analysis


## Introduction

This project makes part of the coursework of Udacity's Data Analysis Nanodegree. Its objective is to demonstrate skills for the Data Wrangling phase of the Data Analysis Process. 
Data Wrangling is a key part in analytics, and is typically described as the one where analysts and data scientists spend the most part of their time.

The project gathers data from different sources related to the WeRateDogs twitter account, which posts and rates photos of folowers' dogs (Archived tweets, results from algorithm to predict the breed, Twitter API). 
After assessing and cleaning the data, reports are written to communicate the results of an initial analysis. 

## Gathering Data:
I gathered the required data for this project from three different resources:
	1-	WeRateDogs Twitter archive, which an enhanced version delivered to us “Udacity Students” by Udacity team.
	2-	image_predictions.tsv hosted on Udacity’s servers, I downloaded it using requests library.
	3-	More data about the tweets gathered by using Twitter API.
## Assessing Data:
I assessed the gathered data both visually and programmatically.
	1.	Visual Assessment:
	To get sense of the gathered data, done by using head(), tail(), and sample() functions.
	2.	Programmatically Assessment:
	Done by using info(), value_counts(), max() functions.
	After assessing data I found some problems stated in the following assessing report:

	Assessing Report
	Quality Issues:
	- twitter-archive-enhanced.csv
	•	some tweets are retweets (Solved)
	•	some tweets are reply (Solved)
	•	some tweets missing in image_predictions.tsv (Solved)
	•	source column has HTML Tags. (Solved)
	•	timestamp column in wrong datatype, it should be datetime. (Solved)
	•	tweet_id column in 3 dataframes is in wrong datatype, it should be string. (Solved)
	•	rating_denominator has different values other than 10. (Solved)
	•	rating_numerator has values less than 6.(my rule here that it is okay if the rating less than 10, that may point to dislike to that dog but less than 6 may be due to different reasons) (Not Solved)
	•	some of dogs' names are wrong (some are not even a name and some are in lowercase) (Solved)
	- image-predictions.tsv
	•	columns p1, p1_conf, p1_dog, p2, p2_conf, p2_dog are not descriptive. (Solved)
	- twitter_json.txt
	•	retweet_count and favorite_count are in wrong datatype (float), they should be int (Solved)
	Tidiness Issues:
	- twitter-archive-enhanced.csv
	•	four columns for dog stage, it should be one column. (Solved)
	- image-predictions.tsv
	•	three columns for prediction, three columns for confidence, three columns for the breed. (Solved)
	•	this dataset contains extra data related to Tweets, it should be merged with Archive dataset
	- twitter_json.txt
	•	time column for the tweets repeated in twitter-archive-enhanced.tsv, also this data should be merged in same table represented in twitter-archive-enhanced.csv (Solved)

## Cleaning Data:
First, I made a copy from all the gathered dataframes. Then, I cleaned the data programmatically using the 3 steps process: define, code, test.
I used some functions during the cleaning such as, drop(), replace(), astype(). And I used regex patterns to find Information.
After the wrangling process, I stored the final cleaned dataframe into csv file to apply the analysis process on it. “twitter_archive_master.csv” 

## Analysis to answer the following questions:
- What dog stage receives more likes and retweets?
- What dog stage receives the best ratings?
- What is the most twitter source used?
- Analyzing number of tweets posted over time.
- What is the average retweet count for each Dog stage?
- What are the Top 10 Dog breeds rated?

Analyzing number of tweets posted over time:
- By displaying number of tweets posted each month, I found the account grew very well in the first 2 month then the number of tweets decreased dramatically after March 2016.

Analyzing number of tweets from different twitter sources:
- Most of followers of this account use iPhone app

Analyzing retweet count for each dog stage
- the most popular dog stage between followers is doggo stage, it gots the most average retweet count

Analyzing rating and favorite count for each dog stage
- People loves the pupper dogs, they got the most rating and favorite count

Top 10 Dog Breeds
- In order based on Number of tweets:
	- Golden retriever
	- Brador retriever
	- Pembroke
	- Chihuahua
	- Pug
	- Chow
	- Samoyed
	- Pomeranian
	- Toy poodle
	- Malamute
