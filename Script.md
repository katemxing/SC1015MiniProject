# Steam Store Games Analysis

## Introduction

Did you know that during the covid pandemic in 2020, more than 20.3 million people were gaming on Steam? Video gaming was one of the industries that boomed during the covid pandemic. With this surge in global interest for gaming, how can game developers identify if their game is a success? Can they identify what was good and what was bad about their game? Can they gain useful insights from the reviews provided by the users? Most importantly, from a gamer’s perspective, is it possible to identify if, a game is worth playing or not? 

I’m Rishe, and together with my group mates, Kate (Xing Mian) and Ri Hong, we will be exploring the games found in Steam Store. Kate will provide detailed Exploratory data analysis of the dataset from Steam and Ri Hong will explain the machine learning methods that were used to predict if a game is good. Lastly, I will talk about the the natural language processing technique we applied to the dataset. 

## Data Cleaning

After observing the dataset, we found issues that may affect the subsequent analysis and improve them as follows: First, the release day is shown in the form of year, month, and day, but what we only need is the year, so we just simply removed redundant information. Secondly, some of those numerical values are too large, and they have different units. We solved this by normalizing playtime and ratings to a range between 0 and 1, respectively, and calculating the percentage of positive ratings. Thirdly, the delimiter is ‘genres’, ‘categories’ and ‘steamspyt_ags’ might be troublesome, so we removed them and combined these categorical data into separate lists. Lastly, to define positively rated games, we use the algorithm on Steam Database and classified those 'SteamDB_rating' >Q3 quartile of overall 'SteamDB_rating as ‘tier’=1, and the rest should be ‘tier’=0;

 Here is the dataset before and after cleaning.

## EDA

 Now we move to the part of Exploratory Data Analysis and we observe some critical points. From the above graph, we can see that most of the numerical values,except for 'release_date','required_age'and 'price', are quite skewed to both or either sides. By plotting out the graph on Steam Database rating and tier, it can be easily seen that the rating is not heavily skewed, and there are 20369 tier 0 games, and 6706 tier 1 games. By generalizing the word cloud of ‘genres’, we found that indie, action, and casual games have the largest frequency.

 Through exploring bivariate data analysis on the most voted tag of each individual game, release date, and owners and developers versus ‘SteamDB_rating’, respectively, we concluded as follows: 

 ‘Audio_production’ has the lowest average rating among all genres, while the highest average goes to games that are labeled as RPG, game_evelopment, and sexual_content; The earlier the year of release, the higher the rating; The more the owners, the higher the rating; and at last, we extracted top 10 developers base on the average rating of their works, as shown here.

 As for the multivariate analysis, ‘release_date’ has a relatively strong correlation with playtime; while playtime has a relatively strong correlation with tier and ‘SteamDB_rating’.

## Machine Learning

 We found that some of the games were unplayed after purchase or had very little ratings, so we decided to extract rows which had >50 total ratings and >0 average playtime only to model.

 In order to employ machine learning techniques on the categorical data, we used label encoding on ‘developer’ and ‘most_voted_tag’ to convert it from textual to numerical form which can then be modeled. In addition, tags which had a frequency below 50 were combined into a category of “others”. We did a 75/25 train-test split on the extracted data to predict which tier (tier 0 or tier 1) a game would belong to based on its attributes. We used these 3 different models: decision trees, random forest and naive bayes, as our modeling features do not have strong correlation with the ‘tier’ of a game or each other.

 For the decision trees, we did bivariate classification on both ‘price’ and ‘median_playtime’ as these 2 attributes had the highest correlation with ‘tier’, alongside multivariate classification. Median playtime only yielded around 62% accuracy on train data and 55% accuracy on test data, compared to price which had 63% on both train and test. Additionally, median playtime had a very high false negative rate on both train and test data. Multivariate classification had higher accuracy on train at 70% compared to both bivariate models, but still only had 62% accuracy on test data(around the same as price).

 Since the decision trees were not very accurate, we also employed random forest to explore many different trees, but we only obtained slightly higher classification accuracy compared to the decision trees. The random forest model had 79% accuracy on train data, much higher than decision trees, but only slightly higher 64% accuracy on test data, still not very good for prediction.

 From the random forest model, we also found that price and median playtime were the 2 features of highest importance, both were above 20%, coincident with these 2 attributes highest correlation with tier. Meanwhile, we can see that age requirements and English availability are insignificant in importance, less than 2% when determining the tier of a game. 

 Naive bayes produced similar results as decision tree, but with lower accuracy overall. Bivariate classification on median playtime was around 51% accurate on train and test data, price was again higher at 58% accuracy on both train and test data, while multivariate classification was highest at 60% accuracy on train and test.

 Overall, all 3 models were not very accurate in predicting tier of a game

## Natural Language Processing

Moving on, I will explain how sentiment analysis was performed on the reviews, to understand how users felt about the games. Firstly, we extracted a dataset with Steam reviews from Kaggle and filtered out the reviews for the top-rated game, which is Portal 2. Then we proceeded on to clean the data by firstly removing rows with empty reviews. WE also removed common English words such as articles like “a”, “the” from the reviews for more accurate analysis. With this list of processed reviews, we were able to identify the top 30 most commonly used words when users liked a game. We also proceeded to calculate the percentage of positive words in the reviews. Finally, we did sentiment analysis on the reviews where the program determines if the review was positive or negative. This was accomplished using VADER, a library that uses a list of lexical features to calculate the text sentiment of the reviews. This allowed us to determine to a certain extent if the review was positive or negative. 

## Conclusion

To summarize, we had done EDA on the game datasets from Steam and also came up with machine learning models that can predict the success of a game based on different factors. Although our models were able to predict the success fairly accurately, we would like to stress that there are other factors that are at play when determining the success of a game. For example, the brand image of the developers of the game plays a crucial role when users contemplate on choosing to play a game. One interesting data we observed was that even though a lot of people buy games, it does not necessarily mean they will play those games. Another interesting fact was that the genre of games with the highest rating were Indie games, games that are developed by individuals or smaller development teams. This shows that if we have an idea to develop a game, it is definitely worth taking a shot as there is a good chance it might be well received by gamers. In conclusion, we were exposed to the natural language processing aspect of data science and we also managed to explore different classification techniques like random forest and naïve bayes classifier. With that we will conclude our project. Thank you!