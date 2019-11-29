# Movie-plot-analysis-with-NLP

## Background ##

We all love watching movies! Most people have a preference for movies of a similar genre. Websites such as Netflix provide lists of movies based on genres, which makes it easier for users to select the movie that interests them based on the genre he/she is more inclined towards. Also users can find similar movies and TVs on Taste, which is a platform that personalizes recommendations based on users’  ratings and reviews. The algorithm behind is based on the users’ ratings.

## Problems to solve ##

However, both genres and users’ ratings have some limitations. First, films within a genre sometimes share common intuition-based base parameters, but that would be too broad. For example, comedy, it contains different subtypes and even movies within the same comedy subgroup may not be the most similar movies for each other.

Another problem is often referred to as “new item cold start problem”. The number of ratings for new released movies would be very limited, making it hard to find similar ones for this movie. 

Facing the above two problems of current movie recommender systems, we proposed to find movie similarity from plot summaries using k-means and we will visualize the result.

## Data Source ##

We will scrape IMDB’s movie name, genre, plot summaries and ratings. We will also manually fill a test set to evaluate the unsupervised model.

## Research Design ##

The first step is to use NLTK package to tokenize plot summaries into individual sentences or words and stem the words. We consider wrapping tokenization and stemming in a function to handle a large amount of data, passing the text as the function argument to be tokenized and stemmed. To convert textual plot summaries to numbers for the computer to be able to extract meaning from them, we will create a TF-IDF Vectorizer to recognize words that are unique and important to the documents. We can pass the wrapping function as the tokenizer argument while creating the TF-IDF vector of the text. After that, we will be able to calculate the similarity distance for all of our movies using cosine_similarity from the sklearn package. 

## Expected Output ##

We will get the quantified similarity of each movie based on their plot summaries. We also expect to divide movies into clusters according to the similarity of plot. To visualize the result, we'll create a dendrogram to represent how closely the movies are related to each other. 

## Evaluation Metrics ##

To evaluate model performance, we can use MAE and RMSE. In terms of similarity itself, here are a few ways to evaluate but all these approaches would be based on subjective judgement:

- Spot check: pick our familiar movies and TVs, check the top 50 most similar items for each of them, and see if the result makes sense;

 - Baseline from other platforms: get the similar movies/TVs list from other platform as baseline and compare that with our result.
