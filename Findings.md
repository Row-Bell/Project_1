# Findings

## Getting Twitter Information from Elon Musk
### Data Sourcing Research
As a team we spent a considerable amount of time researching for the Twitter and Bitcoin data. The initial data set retrieved was incomplete and at times un-cleanable. With a longer time frame for the project, we would have explored cleaning the initial raw data using python and its available libraries. In our research for alternatives we discovered multiple data sources:
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
![Crypto Tweets](Bitcoin_Data.png)
![Word Cloud](Word_Cloud.png)

# Find trends and correlation, if any, in Bitcoin valuations based on the social media activity of @elonmusk (tweets, retweets, replies, likes)
![Correlation](correlation_code.png)
![Daily](Heatmap_Daily.png)
We anticipated finding changes in volume with Bitcoin when Elon tweets about cryptocurrency.
As seen in the heatmap and code above, to our surprise, there is little to no correlation between Elon Musk's cryptocurrency related tweets and Bitcoin volume.


## Compare historical Bitcoin valuation and volume data to social media activity
Here in the heatmap below, we have narrowed down the Bitcoin return data to hourly data. In narrowing down the data we anticipated to find correlation with the more granular dataset. What we found was there was little to no correlation between Elon's cryptocurrency tweets and Bitcoin's valuation and volume. In this plot we saw a slight difference where is is some correlation, but frankly too small to sway our conclusion.



![Daily Returns](daily_volume_with_elons_tweet_events.png)

![Hourly](Heatmap_Hourly.png)

In the presentation, a question was posed asking if the tweets around the time period from and since the purchase of bitcoin assets by Tesla, is there correlation between Bitcoin's valuation and volume and Elon Musk's Twitter activity. As shown below in the heatmap, there is still little to no correlation. Though the variance as evidence below is wider than the historical data from previous years.
![2020_2021 Heatmap](Heatmap_2020_2021.png)


## Determine if the public follows Elon Musk for his tweets on cryptocurrency.
Using the dataframe created by the browser based web scrapping tool, we gathered data to determine if Elon Musk has more twitter activity from his followers on his cryptocurrency related tweets vs his other tweets. As evidenced by the HvPlot of Elon's Musk Tweets, you can see that for Tweet Replies, Retweets, and Tweet Likes, we saw far more activity from his followers for his cryptocurrency tweets, green bars, than all other tweets as highlighted in the orange bars. In our discussion of those results we came to the conclusion that tweet replies were a more active user response than a tweet like or retweet.

![Scatter Plot](Scatter_Plot_of_Elons_Tweet_Activity.png)
![Elon Tweets](hvplot_bar_df.png)

In the plot below you can see that Elon's tweet activity began to increase in 2018 and has been hot of late. The plot shows the huge spikes in in followers retweeting and liking his tweets, however, no significant change was found in the daily returns of Bitcoin.

![Daily Returns](Daily_Returns_vs_Elons_Tweets.png)

# Next Steps
## Evolving the project

 The next steps in the evolution of this project would be:
 
1. Add more twitter users who tweet about cryptocurrency
2. Gather datasets from other social media platforms 
3. Analyse cryptocurrency related tweets/posts to determine correlation to the market
3. Determine what crypto hashtags are more prevalent to see if find a trend or correlation.

We strongly believe that there is a correlation in social media activity and the cryptocurrency market, with more twitter users and data, we believe we will find that social media has a significant impact on the cryptocurrency market. In working with a larger dataset and more social media user's activity out aim is to look for those thought leaders in this space to analyze their impact on cryptocurrency volume and valuations.
Our theory is that the user who replies to cryptocurrency related tweets is more likely to take action based on Elon's or others tweets. This is where we would take the above questions and project next.
