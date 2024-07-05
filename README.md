# Recommander-System

## Model Development

The recommender system algorithm we will use is the : Matrix Factorization Algorithm. In a first place, we will do a simple Matrix Factorization based on a Funk SVD that will predict a score when we link a user to a movie

We have an algorithm that can predict a score for a user-movie pair. Now, our goal is to predict a score for a couple of users and a movie. Here are two methods to achieve this:

#### Method 1: Average of Individual Ratings
- Approach: Calculate the predicted rating for a movie by taking the average of the ratings given by the two users in the couple.
    
#### Method 2: Fusion of Users
- Approach: Create a new user profile that combines the preferences of both users in the couple.


## Recommendation Algorithm

We already have a function that predicts a score for a movie based on the preferences of a couple of users. With approximately 4000 movies, we plan to loop through all movies, compute scores, and return the top 10 recommendations. However, for datasets with many more movies, it may become impractical to check every movie. In such cases, we propose taking a subset of movies and applying the same prediction function.

Here are 3 algorithms depending on the preferences of the couple:

#### Algorithm 1: Match a Movie (Including Seen Movies)
- Objective: Recommend movies that match the couple's preferences, regardless of whether both have already seen the movie.

#### Algorithm 2: Exclude Movies Seen by at least One Member
- Objective: Recommend movies that at least one member of the couple has not seen before.

#### Algorithm 3: Exclude Movies Seen by Both Members
- Objective: Recommend movies that neither member of the couple has seen before.


