# Findings

## Getting Twitter Information from Elon Musk
### Data Sourcing Research
As a team we spent a considerable amount of time researching for the Twitter and Bitcoin data. The initial data set retrieved was incomplete and at times uncleanable. With a longer time frame for the project, we would have explored cleaning the initial raw data using python and its available libraries. In our research for alternatives we discovered multiple data sources:
### Twitter API
Found limited data and restrictions on the look back time frame to collect the data using the hobbyist API account. Applied for an Academic Developer account and was denied the application, thus leaving us with only a paid standard developer version as an option for the scope of the project. Further research revealed that the Twitter API was clunky to use and may not pull the data in a manner that will be time effective to clean.  

### Tweepy
Great library that facilitates pulling data from Twitter but requires access to the standard developer Twitter API.  

### TWINT
Twitter specific scrapping tool. I used this to create a dataframe of cryptocurrency related tweets as well as a dataframe for all tweets from Elon Musk within a 5 year time frame. The issue I ran into was the timestamp being lumped in with the tweet content. Cleaning that was a challenge and became time inefficient. Christian was simultaneously building a browser based web scrapping tool, the tool was able to create a dataframe with separate columns for time and tweet content. We were looking at concatenating both dataframes but ran into the tweet content not matching up. The browser scrapping tool brought in some Twitter count data with text instead of integers. With the help of the Instructor Leo and the TA's we were able to create a script to clean the data, thus, we continued the project with the dataset obtained from the web scraping tool.  

### TwitterScraper
Twitter Updated their website mid last year. That library is not up to date anymore. This scrapper also does not pull the retweet content or count.  

### Selenium
Automation library. Using the html source to extract the information from the website.
As we go through each post line by line - getting historical information is time consuming. Imagine doing this by hand for 10,000+ tweets
As I ran the twitter scraper for testing purposes - I wasn't able to login anymore due to the frequency of 'automated' logins. This needs to be kept in mind and adding some 'sleep time' (pause) to the automation.  

### Coinbase Pro
We were able to pull the cryptocurrency data from Coinbase Pro. The challenge with that data set was the time date was wonky and much time was being used to cleaning and format the data.  

## Gemini
Ultimately we sourced the data for Bitcoin from the Gemini. The data came in a better format that facilitated the cleaning of the data.  

# Does Elon Musk tweet about crypto?
Our findings confirmed what we already knew, Elon does tweet about cryptocurrency. 
In our journey scrapping Elon Musk's tweets we found 362 cryptocurrency related tweets in the last five years using these keywords:
- doge 
- bitcoin 
- crypto 
- coin 
- dogecoin 
- eth
- btc 
- currency 
- cryptocurrency 
- dogecoin
- ethereum
- blockchain
- coinbase
- ripple
- bitcoincash
- xrp


![Elon Tweets](hvplot_bar_df.png)

# Find trends and correlation, if any, in Bitcoin valuations based on the social media activity of @elonmusk (tweets, retweets, replies, likes)
![Correlation](correlation_code.png)
We anticipated finding changes in volume with Bitcoin when Elon tweets about cryptocurrency.
As seen in the heatmap and code above, to our surprise, there is little to no correlation between Elon Musk's cryptocurrency related tweets and Bitcoin volume.
## Compare historical crypto valuation and volume data to social media activity
Here in the heatmap below, we have narrowed down the Bitcoin return data to hourly data. In narrowing down the data we anticipated to find correlation with the more granular dataset. What we found was there was little to no correlation between Elon's cryptocurrency tweets and Bitcoin's valuation and volume. In this olot we saw a slight difference where is is some correlation, but frankly too small to sway our conclusion.
![Hourly](Heatmap_Hourly.png)

## Determine if the public follows Elon Musk for his tweets on crypto.
Using the dataframe created by the browser based web scrapping tool, we gathered data to determine if Elon Musk has more twitter activity from his followers on his cryptocurrency related tweets vs his other tweets. As evidenced by the HvPlot of Elon's Musk Tweets, you can see that for Tweet Replies, Retweets, and Tweet Likes, we saw far more activity from his followers for his cryptocurrency tweets, green bars, than all other tweets as highlighted in the orange bars. In our discussion of those results we came to the conclusion that tweet replies were a more active user response than a tweet like or retweet.

Our next hypothesis is that the user who replies to his cryptocurrency related tweet is more likely to take action based on Elon's tweets. This is where we would take this question and project next.
![Elon Tweets](hvplot_bar_df.png)