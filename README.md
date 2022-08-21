# Twitter Data Analysis — “WeRateDogs”

The project emphasizes everything I have learned which involves gathering data from a variety of resources in a variety of formats, assessing the data quality and tidiness, cleaning the data, and showcasing my wrangling efforts through analysis and visualizations.

## Gathering the Data

The data for this project came in three different formats:

**Directly download the WeRateDogs Twitter archive data (twitter_archive_enhanced.csv)**

`Twitter Archive File from WeRateDogs:` WeRateDogs downloaded their Twitter archive and sent it to Udacity via email exclusively for use in this project. This archive contains basic tweet data (tweet ID, timestamp, text, etc.) for all 5000+ of their tweets as they stood on August 1, 2017.

**Use the Requests library to download the tweet image prediction (image_predictions.tsv)**

`Image Prediction File:` The images in the WeRateDogs Twitter archive (that is the first dataset above) were run through a neural network that can classify breeds of dogs. The image predictions were stored in this file. This file was hosted on Udacity’s server in a TSV format and was downloaded programmatical using the URL the python Requests library.

**Use the Tweepy library to query additional data via the Twitter API (tweet_json.txt)**

`JSON File from Twitter API:` Using the tweet IDs in the WeRateDogs Twitter archive, I queried the Twitter API for each tweet’s JSON data using Python’s Tweepy library and stored each tweet’s entire set of JSON data in a file called tweet_json.txt file. Each tweet’s JSON data was written to its own line. Then I read the .txt file line by line into a pandas DataFrame.

Tweepy is an open-source Python package that gives you a very convenient way to access the Twitter API with Python. You can find more details on setting up an app in Twitter and accessing Twitter API using Python.

## Assessing the Data

The three data have been gathered and were properly assessed. With the assessment, I looked for quality and tidiness issues.

**Quality:** Low-quality data is commonly referred to as dirty data. Dirty data has issues with its content. The Data Quality Dimensions are Completeness, Validity, Accuracy, and Consistency.Quality issues worked on are:

**Quality issues**

1.Twitter_archive_data: Dog name are not consistence , some rows has dog name as ( 'a,an,the,my,very,such,his....')

2.Twitter_archive_data: tweet_id is integer,timestamp is object(wrong datatype)

3.Twitter_archive_data : removing the retweets and replies.

4.Twitter_archive_data:Extract the main_source of tweets from source cloumn

5.master : Removing outliers (rating_numerator ,rating_denominator)

6.image : p1,p2,p3 has a mixture of uppercase and lowercase

7.image:p1,p2,p3 has a mixture of hypen and Underscore

8.image: Renaming columns

**Tidiness:** Untidy data is commonly referred to as “messy” data. Messy data has issues with its structure. Tidy issues worked on are stated below

**Tidiness issues**

1.image & df_tweetdata:These data are part of the same observation unit as the Twitter_archive_data ,(one table with information about dog rating)

2.There are multiple dog stages columns present e.g. doggo, pupper, etc. They should be merged into one column

## Cleaning the Data

I cleaned all of the issues I documented that I documented during the assessing stage. It’s good to know that cleaning the data doesn’t mean changing the form of the data. It simply means improving the quality of the data so that one can work with it. The data is cleaned to improve its quality and tidiness.

I cleaned the data using the three cleaning processes which are Define, Code, and Test.

    Define: the issues that were gotten in the assessment are converted into cleaning tasks.
    Code: the cleaning task is converted into code and then run.
    Test: I used codes to test my cleaning efforts to make sure they worked.

## Storing the Data

After cleaning the data, I combined the three cleaned datasets using a common attribute, which is the Twitter id, and then saved the master dataset in a CSV file named `twitter_archive_master.csv`.

## Analysis and Visualisation

After the data was cleaned it was loaded into the master dataframe , i did some basic analysis like :

**Insights:**

* Most used Twitter source

* Dog Rating distribution

* Retweeting and Favoriting trend over time

* Top 6 common dog names

* Most Popular Dog_stage

* Dog stage with the higest image post

* Top 10 common dog_breed_prediction
