# WeRateDogs_tweets_DataWrangling

This project aims to gather, assess, and clean a dataset contains tweet archive of Twitter user @dog_rates, also known as WeRateDogs.

There are 3 files I used to gather the data from and they can be mentioned as follows:

twitter-archive-enhanced.csv: The WeRateDogs Twitter archive.
image_predictions.tsv: The tweet image predictions, i.e., what breed of dog (or other object, animal, etc.) is present in each tweet according to a neural network.
tweet_json.txt: Each tweet's retweet count and favorite ("like") count at minimum, and any additional data you find interesting.
The dataset is messy and dirty where it has many quality and tidiness issues. Accordingly, in this notebook I tried to figure out some of these issues using Pandas, NumPy, Matplotlib, and Json libraries and solve it programmatically. As a result, 8 quality issues and 4 tidiness appeared as follows:

twitter-archive-enhanced.csv: 8 quality issues and 1 tidiness issue.
image_predictions.tsv: 1 tidiness issue
tweet_json.txt: 1 tidiness issue
One dataset should contain the whole records instead of three above
File 1: twitter-archive-enhanced.csv dataset
This is considered as the main file which contains the rating data. However, It has many quality issues that should be solved programmatically. These are the quality issues (Q.I.) I could figure out after the assessing using Pandas head(), tail(), info(), and describe() functions and more:

Q.I.1: timestamp column should be as datetime type instead of object type

Q.I.2: Some records with all-None stages (doggo,floofer,pupper,puppo) can be re-extracted from the text column to find the stage

Q.I.3: Delete records that not present dogs.

Q.I.4: Find the missed names in the name column

Q.I.5: Delete records that are not presenting as a new tweet

Q.I.6: Re-extract the rating numerator for invalid rantings or delete the records have no-valid rating in the text column

Q.I.7: Set the rating_denominator column values all to 10

Q.I.8: Extract the source name from the url given in the source column

Besides, there is a noticeable tidiness issue (T.I.) which also I solved programmatically:

T.I.1: Create one column for the dog stage dog_stage instead of the 4 excited columns

File 2: image-predictions.tsv dataset
The second file is about the algorithms used to predict the dog's breed in the specified tweet using the image-recognition techniques. Therefore, there are 3 used algorithms that gave 3 different results with confidence factor for each. As a result, I worked on extracting the best breed prediction (with the highest confidence factor) for each tweet id.

image.png

T.I.2: Create one column that represents the breed value instead of the used method

File 3: tweet_json.txt
The last file is a text file that contains information about each tweet. The file's data is collected using tweepy library to query the Twitter's API. From this file, I will get the like(s) count (favorite_count) and the retweet(s) count (retweet_count) for each tweet id by constructing a dataFrame using Pandas and NumPy.image.png

Conclusion
Finally, I joined the favorite_count, retweet_count, and breed columns into the cleaned twitter-archive dataset and saved the resultant dataset as twitter_archive_master.csv. Also, I accomplished a group of investigations and insights on the final dataset (twitter_archive_master.csv) that can be found in the act_report.html file.image.png
