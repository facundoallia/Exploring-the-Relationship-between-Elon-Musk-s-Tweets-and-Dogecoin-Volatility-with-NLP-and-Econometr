# Tweet, Trade, Profit: Exploring the Relationship between Elon Musk's Tweets and Dogecoin Volatility with NLP and Econometric Approach

<p align="center"><img src="https://github.com/facundoallia/Exploring-the-Relationship-between-Elon-Musk-s-Tweets-and-Dogecoin-Volatility-with-NLP-and-Econometr/blob/main/images/doge.jpg?raw=true" alt="dogecoin" style="width: 100%;">

In recent years, social media platforms have become a powerful tool for investors seeking to gain an edge in the financial markets. Among the most influential social media figures in the investment community is Elon Musk, the billionaire entrepreneur and CEO of companies such as SpaceX and Tesla. In particular, Musk's tweets about cryptocurrencies such as Dogecoin have been known to cause significant price movements in the market.

The hypothesis of this study is that Elon Musk's tweets about Dogecoin can significantly impact the cryptocurrency's volatility and price movements. By analyzing Musk's tweet history and correlating it with market data on Dogecoin, we aim to identify trading opportunities that can benefit from the resulting increase in volatility.
    
### Dogecoin prices and volatility
We use ccxt to create an instance of the Binance exchange API and fetch OHLCV data for the DOGE/USDT trading pair at a 1-hour timeframe since January 1st, 2021. We then retrieve the data in batches and append it to a Pandas DataFrame for further analysis.
    
<p align="center"><img src="https://github.com/facundoallia/Exploring-the-Relationship-between-Elon-Musk-s-Tweets-and-Dogecoin-Volatility-with-NLP-and-Econometr/blob/main/images/doge_prices_vol.png?raw=true" alt="dogecoin" style="width: 100%;">
    
### Elon Musk tweets
Elon Musk, the co-founder and CEO of SpaceX and Tesla, is one of the most popular figures in the tech industry today. Musk has a massive following on Twitter, where he frequently shares his thoughts and updates on his various companies. As a result, analyzing his tweets has become a popular way to gain insight into his business strategies and thought process.

In this article, we will be analyzing a dataset of tweets posted by Elon Musk. The dataset was downloaded from [Data World](https://data.world/barbaramaseda/elon-musk-tweets) and consists of tweets that were collected automatically using an IFTTT applet. The dataset includes a variety of information such as the tweet text, username, link to the tweet, and the date it was posted.
    
<p align="center"><img src="https://github.com/facundoallia/Exploring-the-Relationship-between-Elon-Musk-s-Tweets-and-Dogecoin-Volatility-with-NLP-and-Econometr/blob/main/images/tweets.png?raw=true" alt="dogecoin" style="width: 100%;">
    
### Natural Language Processing    
Natural Language Processing (NLP) techniques are a set of tools and algorithms used to analyze and understand human language. With the explosion of data and information available on the internet, NLP has become increasingly important in fields such as machine learning, artificial intelligence, and data science.

When analyzing Elon Musk's tweets related to Dogecoin, applying these NLP techniques can help filter out irrelevant information and focus on the most important tweets. By tokenizing, removing stopwords, and lemmatizing the text, we can better understand the frequency and context of words related to Dogecoin, and potentially gain insights into Musk's thoughts and actions regarding this cryptocurrency.

After applying the filter, we end up with a smaller subset of tweets that are more likely to have an impact on DOGE/USDT price. The resulting dataset consists of 161 tweets that mention specific keywords. By filtering the tweets in this way, we are able to reduce the noise in the data and focus on the tweets that are most likely to have an impact on the price of DOGE/USDT.

To further explore the relationship between DOGE/USDT and Elon Musk's tweets, we can create a word cloud of the most common words in the filtered tweets. This visualization allows us to quickly identify the most frequently mentioned words related to DOGE/USDT and Elon Musk's tweets.The word cloud for the filtered tweets shows that the most common words include "doge", "crypto", "coin", and "buy", among others.
    
<p align="center"><img src="https://github.com/facundoallia/Exploring-the-Relationship-between-Elon-Musk-s-Tweets-and-Dogecoin-Volatility-with-NLP-and-Econometr/blob/main/images/wordcloud_doge.png?raw=true" alt="dogecoin" style="width: 100%;">
    
### Price analysis
We can visualize the percent change of DOGE after Elon Musk tweets in a Plotly chart:
    
<p align="center"><img src="https://github.com/facundoallia/Exploring-the-Relationship-between-Elon-Musk-s-Tweets-and-Dogecoin-Volatility-with-NLP-and-Econometr/blob/main/images/doge_price_tweets.png?raw=true" alt="dogecoin" style="width: 100%;">
    
As we can see in the graph above, the tweets led to important fluctuations in price, but not all the tweets produced positive impacts. In order to analyze the strong of the correlation, a first approximation is to compare the mean price change of DOGE/USDT with the mean price change after Elon Musk posts a DOGE-related tweet.

The mean price change before the tweet was found to be 0.03%, whereas after the tweets, the mean price change was found to be 1.71%. This suggests that Elon Musk's tweets had a significant impact on the price of the asset, causing a much larger price change than the average price change before the tweets. We may conclude that Elon Musk's tweets can be important signals for predicting future price movements of the asset, but for a deeper analysis we need to apply a stadistic model.

ANOVA is a statistical method used to analyze the differences among means and to test the hypothesis of whether these differences are statistically significant. In this case, we are using it to examine whether there is a significant relationship between the sentiment of Elon Musk's tweets (measured by Text_Polarity) and the percentage change in the price of DOGE (close_pct_change). The summary of the ANOVA model provides information about the model fit, including the R-squared value, F-statistic, and p-value, which can help us to determine the strength of the relationship between the two variables.
    
 <p align="center"><img src="https://github.com/facundoallia/Exploring-the-Relationship-between-Elon-Musk-s-Tweets-and-Dogecoin-Volatility-with-NLP-and-Econometr/blob/main/images/OLS_price_tweets.PNG?raw=true" alt="dogecoin" style="width: 50%;">
     
The ANOVA test results with a dependent variable of close_pct_change and an independent variable of Text_Polarity show that the model has an R-squared value of 0.006, indicating that only 0.6% of the variance in close_pct_change is explained by Text_Polarity. The F-statistic of 118.9 suggests that the model is statistically significant, and the P-value of less than 0.05 for Text_Polarity indicates that it is a significant predictor of close_pct_change.

Overall, the model suggests that Text_Polarity may have some predictive power over close_pct_change, but the low R-squared value indicates that it is not a strong predictor. The high kurtosis value and potential for outliers suggest that the model may not be entirely reliable, and further analysis may be necessary before using it as a base for a trading strategy.
     
 ### Volatility analysis
 We can visualize the percent change of DOGE volatility after Elon Musk tweets in a Plotly chart:

 <p align="center"><img src="https://github.com/facundoallia/Exploring-the-Relationship-between-Elon-Musk-s-Tweets-and-Dogecoin-Volatility-with-NLP-and-Econometr/blob/main/images/doge_vol_tweets.PNG?raw=true" alt="dogecoin" style="width: 100%;">
     
The chart reveals the presence of several volatility spikes that, in some cases, coincide with tweets by Elon Musk posted at the same time. Again, a first approximation is to compare the mean volatility change of DOGE/USDT with the mean volatility change after Elon Musk posts a DOGE-related tweet.

The mean volatility change was 0.4397%, while the mean volatility change after Elon Musk tweeted was 10.4296%. This suggests that Elon Musk's tweets had a considerable impact on the volatility of the market, but for a deeper analysis we need to apply a stadistic model.
     
 <p align="center"><img src="https://github.com/facundoallia/Exploring-the-Relationship-between-Elon-Musk-s-Tweets-and-Dogecoin-Volatility-with-NLP-and-Econometr/blob/main/images/OLS_vol_tweets.PNG?raw=true" alt="dogecoin" style="width: 50%;">
     
The model resulted in an R-squared value of 0.005, which indicates that only 0.5% of the variability in the vol_pct_change can be explained by Text_Polarity. On the other hand, the coefficient of Text_Polarity is 10.0714, which indicates that a one-unit increase in Text_Polarity is associated with increases in vol_pct_change. Also, the F-statistic of 98.14 indicates that the model is significant, meaning that there is strong evidence to suggest that there is a relationship between Text_Polarity and vol_pct_change. In conclusion, the analysis shows that Elon Musk tweets related to DOGE have a statistically significant relationship with DOGE volatility. However, the R-squared value suggests that other factors might have a more significant impact on DOGE volatility.

To go one step further, we can analyze the ANOVA table.The ANOVA table shows the degrees of freedom, the sum of squares, the mean square, the F-statistic, and the associated p-value for each of the variables in the model. The ANOVA table can be used to test the significance of the variables in the model and to compare the fit of different models.
     
 <p align="center"><img src="https://github.com/facundoallia/Exploring-the-Relationship-between-Elon-Musk-s-Tweets-and-Dogecoin-Volatility-with-NLP-and-Econometr/blob/main/images/ANOVA_vol.PNG?raw=true" alt="dogecoin" style="width: 50%;">
     
As per the ANOVA table output, the p-value for the variable "Text_Polarity" is less than the significance level of 0.05, which indicates that there is a significant relationship between "Text_Polarity" and "vol_pct_change" in the model. It means that Elon Musk tweets related to DOGE have a statistically significant impact on the volatility of the cryptocurrency.

Based on this analysis, it could be a good idea to use Elon Musk tweets related to DOGE as a signal of a potential increment in the volatility. Traders could use this signal to buy options or enter into volatility trades to profit from the expected increase in volatility. However, it is important to note that other factors should also be considered to avoid risks and maximize profitability.

###Possible trading strategies and final thoughts

As we could see in the statistical analysis of the correlation with prices and volatility, a trading strategy that seeks to predict jumps in volatility based on Elon Musk's tweets referring to Dogecoin would have more strength than a strategy that seeks to benefit from price changes.

We can attribute these results to the fact that the applied Natural Language Processing procedures filtered the tweets that were related to the topic, without distinguishing between those that had a positive or negative charge. Another possible approach to obtain a model with a higher correlation with positive price changes could include a sentiment analysis.

As for the possible strategies that take advantage of increases in volatility, they would involve the use of derivatives on DOGE/USDT. Exchanges such as Binance, ByBit and DeriBit offer the possibility of trading options on crypto assets.

Options trading strategies such as the straddles, strangles, straps, and strips can be powerful tools for traders looking to take advantage of potential volatility caused by Elon Musk's tweets related to DOGE. These strategies can help traders limit their exposition to price movement while profiting from the increased volatility caused by Musk's tweets:

**Straddle**: A straddle involves buying a call and a put option at the same strike price and expiration date. This strategy profits when the underlying asset's price moves significantly in either direction.

**Strangle**: A strangle is similar to a straddle, but instead of buying options at the same strike price, the call and put options have different strike prices. This strategy profits when the underlying asset's price moves significantly but is more flexible than the straddle as the options' strike prices can be adjusted to suit the trader's expectations.

**Strap**: A strap is a bullish options trading strategy that involves buying two call options and one put option at the same strike price and expiration date. This strategy is profitable if the underlying asset's price increases significantly.

**Strip**: A strip is a bearish options trading strategy that involves buying two put options and one call option at the same strike price and expiration date. This strategy is profitable if the underlying asset's price decreases significantly.

<p align="center"><img src="https://github.com/facundoallia/Exploring-the-Relationship-between-Elon-Musk-s-Tweets-and-Dogecoin-Volatility-with-NLP-and-Econometr/blob/main/images/vol_opt_strategies.png?raw=true" alt="dogecoin" style="width: 100%;">
     
