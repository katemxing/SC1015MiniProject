SC1015 Mini-Project: Steam Store Games Analysis


## Description

<img src="https://user-images.githubusercontent.com/89787115/164893872-55ae3b2c-204b-41c1-97c6-bcbea336129f.png" alt="image" style="zoom: 20%;" />

This is a Mini-Project for SC1015 Introduction to Data Science and Artificial Intelligence.

It focuses on the analysis of [Steam Store Games (Clean dataset)](https://www.kaggle.com/datasets/nikdavis/steam-store-games) scraped from Steam and SteamSpy APIs by Nik Davis on Kaggle, and also the analysis of [Steam Reviews](https://www.kaggle.com/datasets/andrewmvd/steam-reviews) from Steam Store by Larxel.


## Motivation and Problem Definition

- We define good games as those with scores above the Q3 quantile of the rating among all games on [Steam Database](https://steamdb.info/).
- Can we predict a game as good/bad game just by its attributes?
- Which model is the best for abovementioned classification?
- When players evaluate a good/bad game, what words do they use?

### About Datasets

- **steam.csv**: Game data from Steam. Each row has a unique AppID and is usually a separate release, excepting some re-releases and remasters.

- **steamspy_tag_data.csv**: Contains tags from SteamSpy and the number of votes for each tag for each game. Higher numbers can be considered more strongly associated with that tag.

- **dataset.csv**: The dataset contains all the publicly available reviews of specific games we used in English from Steam Reviews portion of Steam store run by Valve. Each review is described by review text, the id of game it belongs to, review sentiment (positive or negative) and a number of users who thought the review was helpful.

  Extracted from [Steam Reviews](https://www.kaggle.com/datasets/andrewmvd/steam-reviews).

## Models Used

- Decision Tree
- Random Forest
- Sentiment Analysis
- Naive Bayes

## Table of Contents of our Jupyter Notebook

[FinalProject.ipynb](https://github.com/katemxing/SC1015MiniProject/blob/main/FinalProject.ipynb)

| Step | Description                     |
| ---- | ------------------------------- |
| 1    | **Data Preparing**              |
| 2    | **Exploratory Data Analysis**   |
| 3    | **Machine Learning**            |
| 4    | **Natural Language Processing** |
| 5    | **Conclusion**                  |

## What have we learnt from this Mini-Poject?

## Contributors

Babu Rishe (@Rishe2000): Natural Language Processing, Naive Bayes 

Wong Ri Hong (@bakase-e): Decision Tree, Random Forest

Xing Mian (@katemxing): Data preperation, Exploratory Data Analysis

## References

1. [SteamDB Team. (2021, June 7). Introducing Steam Database’s new rating algorithm.](https://steamdb.info/blog/steamdb-rating/)
2. [Steam Store Games (Clean dataset)](https://www.kaggle.com/datasets/nikdavis/steam-store-games)
3. [Steam Reviews](https://www.kaggle.com/datasets/andrewmvd/steam-reviews) 

