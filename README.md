# Wrangle-and-Analyze-Data

## Introduction
Real-world data rarely comes clean. Using Python and its libraries, I will gather data from a variety of sources and in a variety of formats, assess its quality and tidiness, then clean it. This is called data wrangling. I will document my wrangling efforts in this Jupyter Notebook, plus showcase them through analyses and visualizations using Python (and its libraries) and/or SQL.

The dataset that I will be wrangling (and analyzing and visualizing) is the tweet archive of Twitter user @dog_rates, also known as WeRateDogs. WeRateDogs is a Twitter account that rates people's dogs with a humorous comment about the dog.

## Gathering Data
- **WeRateDogs Twitter archive:-** This file can be downloaded from the link given in the portal

- **Tweet image predictions:-** Indicates what breed of dog (or other object, animal, etc.) is present in each tweet according to a neural network. This file (image_predictions.tsv) is hosted on Udacity's servers and should be downloaded programmatically using the Requests library and the following URL: https://d17h27t6h515a5.cloudfront.net/topher/2017/August/599fd2ad_image-predictions/image-predictions.tsv

- **Tweet's JSON Data:-** Using the tweet IDs in the WeRateDogs Twitter archive, we can query the Twitter API for each tweet's JSON data using Python's Tweepy library and store each tweet's entire set of JSON data in a file called tweet_json.txt file.

## Assessing Data
<ul>
<li>Once the the data is gathered we can assess the data in two ways:-</li>
<ul>
  <li>**Visual Assessment:-**In this process we put an eye on the gathered
data and get overall overview.For this purpose I opened the Csv file
in the excel sheet and also made use of jupyter notebook to see
different parts of the data.</li>
<li**>Programmatic Assessment:-**In this part I made use of different
pandas methods to analyse the data such as
info,describe,sum,value_counts,shape,head etc</li></ul>
  <ul>
### Quality

#### **Twitter Archive Table**
#### Visual Assessment
<ol>
<li>rating_numerator should not have values greater than 10 as rating_denominator is 10.</li>
<li>rating_denominator should have all the values 10.But there are values other than 10 also.</li>
<li>timestamp column contains +0000 which looks redundant.</li>
<li>Some of the names mentioned in the dogs column is actually not the name such as a,an etc.</li>
<li> In some of the columns there is None instead of NaN such as <b>name,doggo,floofer,pupper,puppo</b> columns</li>
</ol>

#### Programmatic Assessment
<ol start='6'>
<li>tweet_id,in_reply_to_status_id,in_reply_to_user_id,retweeted_status_user_id,retweeted_status_id columns are int but it should be str.</li>
<li>timestamp,retweeted_status_timestamp columns are object instead of datetime.</li>
<li>in_reply_to_status_id,in_reply_to_user_id,retweeted_status_id,retweeted_status_user_id,retweeted_status_timestamp,expanded_urls contains null values.</li>
<li>Twitter archive table has more number or rows than twitter api table

</ol>



#### **`Image Predictions Table`**

<ol>1.datatype of tweet_id is int,which should be str.</ol>
<a id='tidiness'></a>
## **Tidiness**
<ol>
<li>.Melt all the four columns of dogs name in `twitter archive table`</li>
<li> text column in `twitter archive table` should be split into two different columns i.e text and url.</li>
<li>Certain rows in extended urls columns contains two observations i.e two urls in `twitter archive table`.</li>
</ol>

<a id='clean'></a>
## Cleaning Data
This is the final stage of data wrangling.This stage consists of 3 parts
Define:-Here I defined the cleaning step which is to be
performed.For example If we need to drop some unnecessary
columns ,we can mention here.In this project different definitions
include:-
Merging all the 3 dataframes
Combining dog stages into one column.
Replacing names that doesn't look realistic.
Dropping the unwanted columns.
Code:-Here,we write the actual code with performs the action
written in the defined part.For example here we write code to drop
the columns.
Test:-Finally in this part we check whether the above written code
works as per our requirement i.e we check whether those columns
have been dropped or not for which we have written the code.
## Conclusion:-
Data wrangling is the backbone of the data analysis process.For this
purpose there are several python libraries which has been used such as
numpy,pandas,matplotlib etc.After completing the wrangling process
several meaning observations can be seen.
