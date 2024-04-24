# SC1015 FCSB Group 2
We decided to use a dataset from Kaggle titled: "[Popular Video Games 1980 - 2023 🎮]"(https://www.kaggle.com/datasets/arnabchaki/popular-video-games-1980-2023/data)  by randomarnab.

# About
This is a Mini-Project SC1015 (Introduction to Data Science and Artificial Intelligence) which focuses on popular video games. For detailed walkthrough, view the source code in order from:

1. [Data Preparation and Cleaning](https://github.com/prisca-sp/sc1015/blob/main/Data%20Preparation%20and%20Cleaning%20New.ipynb)
2. [Exploratory Data Analysis(EDA)](https://github.com/prisca-sp/sc1015/blob/main/EDA%20analysis.ipynb)
3. [Natural Language Processing(NLP) using TF-IDF and sentiment analysis](https://github.com/prisca-sp/sc1015/blob/main/NLP%20with%20TFIDF%20and%20Sentiment%20Value.ipynb)
4. [Clustering Model](https://github.com/prisca-sp/sc1015/blob/main/Unsupervised%20machine%20learning%20algorithm-clustering.ipynb)
5. [Logistics Regression Model 2](https://github.com/prisca-sp/sc1015/blob/main/Supervised%20machine%20learning%20algorithm-Logistics%20regression-Model%202(final).ipynb)

# Contributors
1. [@prisca-sp](https://github.com/prisca-sp) (Prisca) - Data Preparation & Cleaning, Exploratory Data Analysis (EDA)
2. [@Infernoexe](https://github.com/Infernoexe) (Mei Ting) - Data Preparation & Cleaning, Natural Language Processing (NLP)
3. [@luiSA07A](https://github.com/luiSA07A) (Luisa) - Machine Training for Clustering and Logistics Regression Model

# Table of content
1. [Motivation behind Problem Statement](https://github.com/prisca-sp/sc1015?tab=readme-ov-file#1-motivation-behind-problem-statement)
2. [Problem Statement](https://github.com/prisca-sp/sc1015?tab=readme-ov-file#2-problem-statemment)
3. [Data Preparation and Cleaning](https://github.com/prisca-sp/sc1015?tab=readme-ov-file#3-data-preparation-and-cleaning)
4. [Exploratory Data Analysis(EDA)](https://github.com/prisca-sp/sc1015?tab=readme-ov-file#4-exploratory-data-analysiseda)
5. [Natural Language Processing(NLP) using TF-IDF and sentiment analysis](https://github.com/prisca-sp/sc1015?tab=readme-ov-file#5-natural-language-processingnlp-using-tf-idf-and-sentient-analysis)
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
Unicode was also removed from reviews and summary to clean the strings.

# 4. Exploratory Data Analysis(EDA)
Through the use of different graphs such as jointplot, bar graphs, pie charts, word clouds , heatmaps and line charts, there were a few main observations. 'Adventure' was the genre with the largest proportion of popular games. While the average ratings of most genres fluctuated between 3.0 to 4.0 over the years, 'Visual Novel' maintained its position as highest rating, while MOBA reflected an anomaly of a 2.0 rating.

'Interested', 'Playing', 'Review count' showed higher correlation, so we shall place more focus on these variables. To understand more about the words that appeared in the word cloud on Reviews, we will be utilising TF-IDF.

# 5. Natural Language Processing(NLP) using TF-IDF and sentiment analysis
To allow the algorithm to read texts, we removed all redundant unicode characters and completely non-English words. As long as the reviews contain English words, even though they may include Spanish, sentiment analysis will still be valid, through calculation using TextBlob.

Sentiment Analysis was used to identify which reviews were positive and negative. Any value above 0 is considered a positive review, while anything below 0 is considered a negative review.

Lemmatization of words from reviews and summary was done to make analysis more compact, allowing words to be in a singular form for the algorithm to find similarities more easily. Stop-words were also used to remove redundant and common filler words such as 'and', 'the'. 

TF-IDF weight increases proportionally to the number of times a word appears in a dataset, but is offset by the number of datasets that contain the word. Stop words or connecting words rank low although they appear many times, as they do not mean much to the document. Through a matrix with TF-IDF weights for each word, we obtained a list of feature names that represent which words are included in these vectors and appear the most often.

Comparison between reviews and summary was done to determine the relevancy of the words. From there, we can determine which words are more relevant and frequent, giving us a gauge of what kind of games people usually prefer and what kind of audience the games generally cater to.

# 6. Machine Learning Models
1. Clustering
   a. KMEANS clustering (Final cluster groups)
     - Variables used
       - Currently Playing, Ratings, Review counts and Interested
     - 3 Groups
         - High Popularity
         - Moderate Popularity
         - Low Popularity
   b. DBSCAN
   c. Gaussian mixture
   d. Hierarchical clustering

2. Logistics Regression
   - Trained Models
      a. Model 1 (class Imbalance Problem)
      b. Model 2 (Final model)
   - Variables used
        - TF-IDF features from Summary of game
        - Cluster groups

# 7. Conclusion
- There is 5 variables that show the level of player engagement for every game to help us indicate their popularity in clustering.
  - Fairly Good and High Correlated Variables (at least R=0.63)
    - Currently Playing, Interested, Review Count and Total Plays
    - Totals Plays will be ommited as we only want to extract data from players currently playing the game and not the ones who have stopped
    - Low Correlated Variable (~R=0.4)
       - Rating
       - Important as it reflects the overall satisfaction players and performance of games
- Game developers and publishers can leverage capitalize on the growing popularity of the Brawler genre by creating innovative and engaging titles that cater to the specific preferences of players interested in dynamic combat and multiplayer interactions characteristic of Brawler games. (Cluster insight)
- Clustering was valuable for grouping similar data points based on their numerical features, such as popularity metrics in the context of video games. We wanted to get a more meaningful evaluation of which genres would make the game popular according to the summary of the game.
- By analyzing patterns and trends in the evolution of video game genres and using regression models and Natural Language Processing, we gained new insights.
- The consistent appearance of genres like Adventure and RPG in top combinations suggests a preference for immersive storytelling and character-driven gameplay. Additionally, genres such as Brawler, Simulation, Arcade, and Visual Novels, when combined with Adventure and RPG, can increase a game's appeal.
- Game developers are encouraged to create games with a blend of genres, incorporating Adventure and RPG alongside Brawler, Simulation, Arcade and Visual Novels. This approach can lead to the development of more unique and diverse gaming experiences, catering to a broader audience. Combining genres not only enhances gameplay but also increases the chances of creating innovative and engaging games.
- From NLP, it was discovered that the gaming community focuses more on the characters, world-building, gameplay and story of the game. Some seem to negatively review games where these expectations aren't met, as many words appeared in both the positive and negative results. There were also series that they enjoyed more (Mario, Pokemon) compared to the others (Sonic the Hedgedog, Resident Evil). There is also a vocal minority of people who seem to dislike adventure and action type of games.

With all of these conclusions, game creators can have a better idea of what elements the community is looking out for in games currently that will captivate them to play and enjoy themselves. This will allow the interested audience to play the games and gain popularity from there.

# 8. Learning Beyond the Course
- Utilisation of visualisation tools such as wordclouds, bar-line charts, pie charts etc.
- Natural Language Processing, TextBlob, TFIDF
- Cleaning of language (Removing non-English reviews)
- Logistic regression, clustering models

# 9. References
- Randomarnab. (2023, April). Popular Video Games 1980 - 2023 🎮. Kaggle. https://www.kaggle.com/datasets/arnabchaki/popular-video-games-1980-2023/data
- D. Mesut. (2023, October). 🕹️NLP - Based Game Recommendation🎮. Kaggle. https://www.kaggle.com/code/dumanmesut/nlp-based-game-recommendation 
- Akash. (2022, September 10). Making Natural Language Processing easy with TextBlob. Analytics Vidhya. https://www.analyticsvidhya.com/blog/2021/10/making-natural-language-processing-easy-with-textblob/ 
- Ragnar. (2021). Keywords Extraction Using TF-IDF Method. Kaggle. https://www.kaggle.com/code/rowhitswami/keywords-extraction-using-tf-idf-method 
