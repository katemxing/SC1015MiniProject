# SC1015 Mini-Project: Steam Store Games Analysis


## :video_game:Description
<img src="https://user-images.githubusercontent.com/89787115/164893872-55ae3b2c-204b-41c1-97c6-bcbea336129f.png" alt="image" style="zoom: 20%;" />

This is a Mini-Project for SC1015 Introduction to Data Science and Artificial Intelligence.

It focuses on the analysis of [Steam Store Games (Clean dataset)](https://www.kaggle.com/datasets/nikdavis/steam-store-games) scraped from Steam and SteamSpy APIs by Nik Davis on Kaggle, and also the analysis of [Steam Reviews](https://www.kaggle.com/datasets/andrewmvd/steam-reviews) from Steam Store by Larxel.


## :thought_balloon: Motivation 
During the COVID-19 pamdemic in 2020, more than 20.3 million people were gaming on Steam. Video gaming is one of the industries that boomed during the pandemic. With the upsurge of the global interest in gaming:

- How can developers identifiy if their game is success? 
- Can they identify what is good, what is bad game? 
- Can they get useful insights from the reviews provided by the users? 
- Most Importantly, from a gamer's  perspective, is it possible to identify whether a game is worth playing or not?

## 	:grey_question:Problem Definition
- We define good games as those with scores above the Q3 quantile of the rating among all games on [Steam Database](https://steamdb.info/).
- Can we predict a game as good/bad game just by its attributes?
- Which model is the best for abovementioned classification?
- When players evaluate a good/bad game, what words do they use?

## :label:About Datasets

- **steam.csv**: Game data from Steam. Each row has a unique AppID and is usually a separate release, excepting some re-releases and remasters.

- **steamspy_tag_data.csv**: Contains tags from SteamSpy and the number of votes for each tag for each game. Higher numbers can be considered more strongly associated with that tag.

- **dataset.csv**: The dataset contains all the publicly available reviews of specific games we used in English from Steam Reviews portion of Steam store run by Valve. Each review is described by review text, the id of game it belongs to, review sentiment (positive or negative) and a number of users who thought the review was helpful.

  Extracted from [Steam Reviews](https://www.kaggle.com/datasets/andrewmvd/steam-reviews).

## :computer:Models Used

- Decision Tree
- Random Forest
- Naive Bayes Classifier
- Sentiment Analysis


## :orange_book:Table of Contents of our Jupyter Notebook

| Step | Description                     |
| ---- | ------------------------------- |
| 1    | **Data Preparing**              |
| 2    | **Exploratory Data Analysis**   |
| 3    | **Machine Learning**            |
| 4    | **Natural Language Processing** |
| 5    | **Conclusion**                  |

## :black_nib:What we have learnt from this Mini-Poject?

- Encoding categorical data using LabelEncoder
- Using wordcloud for visualization
- Other Models: Random forest, Naive Bayes
- Cleaning/processing data using scaling/delimiting
- Processing words & sentiment analysis
- Collaborating using google collab/GitHub

## :technologist:Contributors

Babu Rishe (@Rishe2000): Natural Language Processing, Naive Bayes Classifier

Wong Ri Hong (@bakase-e): Decision Tree, Random Forest

Xing Mian (@katemxing): Data preperation, Exploratory Data Analysis

## :books:References

1. [SteamDB Team. (2021, June 7). Introducing Steam Database’s new rating algorithm.](https://steamdb.info/blog/steamdb-rating/)
2. [Steam Store Games (Clean dataset)](https://www.kaggle.com/datasets/nikdavis/steam-store-games)
3. [Steam Reviews](https://www.kaggle.com/datasets/andrewmvd/steam-reviews) 

