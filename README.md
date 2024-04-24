# SC1015 FCSB Group 2
We decided to use a dataset from Kaggle titled: "Popular Video Games 1980 - 2023 🎮" by randomarnab.
https://www.kaggle.com/datasets/arnabchaki/popular-video-games-1980-2023/data

# Contributors
1. github @ (name) - roles --> Data prep & cleaning, EDA...Slides, presenters
2. @
3. @

# Table of content
1. Motivation behind Problem Statement
2. Problem Statement
3. Data Preparation and Cleaning
4. Exploratory Data Analysis(EDA)
5. Natural Language Processing(NLP) using TF-IDF and sentient analysis
6. Machine Learning Models
7. Data Driven Insights
8. Conclusion
9. Learning Beyond the Course
10. References

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

# 7. Data Driven Insights

# 8. Conclusion

# 9. Learning Beyond the Course
- Utilisation of visualisation tools such as wordclouds, bar-line charts, pie charts etc.
- Natural Language Processing, TextBlob, TFIDF
- Cleaning of language
- Logistic regression, clustering models

# 10. References
