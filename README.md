# Movie-feature-analysis-with-NLP

## Background ##

We all love watching movies! Most people have a preference for movies of a similar genre. Websites such as Netflix provide lists of movies based on genres, which makes it easier for users to select the movie that interests them based on the genre he/she is more inclined towards. Also users can find similar movies and TVs on Taste, which is a platform that personalizes recommendations based on users’ ratings and reviews. The algorithm behind is based on the users’ ratings.

## Problems to solve ##

However, both genres and users’ ratings have some limitations. First, movies within a genre sometimes share common intuition-based base parameters, but that would be too broad. For example, comedy, it contains different subtypes and even movies within the same comedy subgroup may not be the most similar movies for each other.

Another problem is often referred to as “new item cold start problem”. The number of ratings for new released movies would be very limited, making it hard to find similar ones for this movie. 

Facing the above two problems of current movie recommender systems, we proposed to find movie similarity from plot summaries using k-means and we will visualize the result.

## Data Source ##

We crawled a list of movies in recent 10 years on IMDB from 2009-01-01 to 2019-10-31 and used IMDbPY API to get each movie's features including each movie's title, release year, genre, plot summaries, the number of votes and rating.

Source code can be found on Github: https://github.com/Zoe0409/Movie-plot-analysis-with-NLP/blob/master/dataset/Collect%20data%20from%20IMDB.ipynb.

## Research Design and Expected Output##

Our project includes four parts:

 - Data Collection: (Saved in dataset folder)
 
 - Exploratory Data Analysis: (Saved in analysis folder -- IMDB movies exploratory data analysis.ipynb)
 
 - Topic Modeling: (Saved in analysis folder -- IMDB Movies topic modeling using sklearn.ipynb)
 
 - Similarity Calculation: We used two bases to calculate similarity
        
        - Key words: (Saved in analysis folder -- IMDB Movies similarity from key words.ipynb)
        
        - Plot summaries: (Saved in analysis folder --  IMDB Movies similarity from plot summaries.ipynb)


## Evaluation Metrics ##

To evaluate model performance, we can use MAE and RMSE. In terms of similarity itself, here are a few ways to evaluate but all these approaches would be based on subjective judgement:

- Spot check: pick our familiar movies and TVs, check the top 50 most similar items for each of them, and see if the result makes sense;

 - Baseline from other platforms: get the similar movies/TVs list from other platform as baseline and compare that with our result.
 
 ## Conclusions and Applications ##
 
 1.There are a lot of movies with "Christmas" topic in plot.

--> Send out notifications about these movies to users during Christmas season.

2. Keywords and plot similarity gave different results.

--> Movie recommendation platforms can display both results and allow users to make their own choices.

3. Similarity score between movies can be based on different metrics.

--> Construct an aggregated similarity score to reflect the real similarity between two movies and use it to generate predicted ratings through KNN. 

4. Movie platforms can send out recommendations generated from different methods to users to test which one is favored by them. 
