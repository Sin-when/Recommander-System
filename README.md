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

## Conclusion and Results

Our model that recommends movies for couples is acceptable because, for two users, I obtained these movies:
    
    1. Movie 1: Blood, Guts, Bullets and Octane (1998)
    2. Movie 2: Muppet Christmas Carol, The (1992)
    3. Movie 3: Other Sister, The (1999)
    4. Movie 4: Police Academy 5: Assignment: Miami Beach (1988)
    5. Movie 5: Tommy Boy (1995)
    6. Movie 6: Disclosure (1994)
    7. Movie 7: Autopsy (Macchie Solari) (1975)
    8. Movie 8: Rescuers, The (1977)
    9. Movie 9: Angela's Ashes (1999)
    10. Movie 10: Down Periscope (1996)

Upon examining them, they seem to have some similarities. Nevertheless, I'm unsure if using the Funk SVD algorithm was the best solution. In fact, my algorithm is mostly based on the ratings and not really on Users informations and Movies informations (that
is why I have not used the dataset IMDb which was only helping to add features to the movies). Perhaps I would have obtained more interesting results with a different recommender system algorithm.


