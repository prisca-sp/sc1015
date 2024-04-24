# SC1015 FCSB Group 2
We decided to use a dataset from Kaggle titled: ["Popular Video Games 1980 - 2023 🎮"](https://www.kaggle.com/datasets/arnabchaki/popular-video-games-1980-2023/data)  by randomarnab.

#About
This is a Mini-Project SC1015 (Introduction to Data Science and Artificial Intelligence) which focuses on popular video games. For detailed walkthrough, view the source code in order from:

1. [Data Preparation and Cleaning](https://github.com/prisca-sp/sc1015/blob/main/Data%20Preparation%20and%20Cleaning%20New.ipynb)
2. [Exploratory Data Analysis(EDA)](https://github.com/prisca-sp/sc1015/blob/main/EDA%20analysis.ipynb)
3. [Natural Language Processing(NLP) using TF-IDF and sentient analysis](https://github.com/prisca-sp/sc1015/blob/main/NLP%20with%20TFIDF%20and%20Sentiment%20Value.ipynb)
4. [Clustering model](https://github.com/prisca-sp/sc1015/blob/main/Unsupervised%20machine%20learning%20algorithm-clustering.ipynb)
5. [Logistics Regression Model 2](https://github.com/prisca-sp/sc1015/blob/main/Supervised%20machine%20learning%20algorithm-Logistics%20regression-Model%202(final).ipynb)

# Contributors
1. [@prisca-sp](https://github.com/prisca-sp) (Prisca) - Data Preparation & Cleaning, Exploratory Data Analysis (EDA)
2. [@Infernoexe](https://github.com/Infernoexe) (Mei Ling) - Data Preparation & Cleaning, Natural Language Processing (NLP)
3. [@luiSA07A](https://github.com/luiSA07A) (Luisa) - Machine Training for Clustering and Logistics Regression Model

# Table of content
1. [Motivation behind Problem Statement](https://github.com/prisca-sp/sc1015?tab=readme-ov-file#1-motivation-behind-problem-statement)
2. [Problem Statement](https://github.com/prisca-sp/sc1015?tab=readme-ov-file#2-problem-statemment)
3. [Data Preparation and Cleaning](https://github.com/prisca-sp/sc1015?tab=readme-ov-file#3-data-preparation-and-cleaning)
4. [Exploratory Data Analysis(EDA)](https://github.com/prisca-sp/sc1015?tab=readme-ov-file#4-exploratory-data-analysiseda)
5. [Natural Language Processing(NLP) using TF-IDF and sentient analysis](https://github.com/prisca-sp/sc1015?tab=readme-ov-file#5-natural-language-processingnlp-using-tf-idf-and-sentient-analysis)
6. [Machine Learning Models](https://github.com/prisca-sp/sc1015?tab=readme-ov-file#6-machine-learning-models)
7. [Conclusion](https://github.com/prisca-sp/sc1015?tab=readme-ov-file#8-conclusion)
8. [Learning Beyond the Course](https://github.com/prisca-sp/sc1015?tab=readme-ov-file#9-learning-beyond-the-course)
9. [References](https://github.com/prisca-sp/sc1015?tab=readme-ov-file#10-references)

# 1. Motivation behind Problem Statement
As of current, there are video games being released everyday, catered to different kinds of audiences. In 2023, more than 12000 games have been released. That is 32 games being released each day. In 2024, there has been 2403 games released and more are in the making. With such high numbers, there is furious competition between companies and indie game creators when releasing their game and ensuring that their games succeeds in the gaming scene. In order to keep up with the trend and ensuring that the games they create make a big hit to the scene, we have decided to look into the trend of games that are popular within the community currently to allow game creators and companies to have a better gauge on what type of games the community is looking for and what might be more attractive right now.

# 2. Problem Statemment
Identifying patterns and trends in the evolution of video game genres over time to predict emerging genres/shifts in popularity

Using regression models and Natural Language Processing, we aimed to analyse how different factors (ratings, reviews etc.) can contribute to a genre's popularity.
This is useful as it can offer developers or investors of video games insights as to what genre can potentially rise in the future.

# 3. Data Preparation and Cleaning
Variables that were not very useful and null columns were removed. To make analysis easier later on, we changed the value type of variables to floats and integers accordingly. As many games were classified under multiple genres, we created a column for each genre through one-hot encoding.

# 4. Exploratory Data Analysis(EDA)
Through the use of different graphs such as jointplot, bar graphs, pie charts, word clouds , heatmaps and line charts, there were a few main observations. 'Adventure' was the genre with the largest proportion of popular games. While the average ratings of most genres fluctuated between 3.0 to 4.0 over the years, 'Visual Novel' maintained its position as highest rating, while MOBA reflected an anomaly of a 2.0 rating.

'Interested', 'Playing', 'Review count' showed higher correlation, so we shall place more focus on these variables. To understand more about the words that appeared in the word cloud on Reviews, we will be utilising TF-IDF.

# 5. Natural Language Processing(NLP) using TF-IDF and sentient analysis
To allow the algorithm to read texts, we removed all redundant unicode characters and completely non-English words. As long as the reviews contain English words, even though they may include Spanish, sentiment analysis will still be valid, through calculation using TextBlob.

Lemmatization of words was done to make analysis more compact. To make the sentiment value more useful, we will find games that are above 4.0 rating containing the top words from the summary of games extracted from positive reviews. This will give us a more accurate result of what are the top and popular/highly rated games the people are looking out for.

TF-IDF weight increases proportionally to the number of times a word appears in a dataset, but is offset by the number of datasets that contain the word. Stop words or connecting words rank low although they appear many times, as they do not mean much to the document. Through a matrix with TF-IDF weights for each word, we obtained a list of feature names that represent which words are included in these vectors.

Comparison between reviews and summary was done to determine the relevancy of the words. From there, we can determine which words are more relevant and frequent, giving us a gauge of what kind of games people usually prefer and what kind of audience the games generally cater to.

# 6. Machine Learning Models
3 models, mainly Logistic Regression and Clustering.

The first Logistic Regression model mainly involves the variables Playing, Ratings and Interested. The variables are used to separate each game into one of the 3 categories - High, Moderate and Low.

# 7. Conclusion

# 8. Learning Beyond the Course
- Utilisation of visualisation tools such as wordclouds, bar-line charts, pie charts etc.
- Natural Language Processing, TextBlob, TFIDF
- Cleaning of language
- Logistic regression, clustering models

# 9. References
