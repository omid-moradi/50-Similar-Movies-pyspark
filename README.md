# Movie Recommendation System with Pyspark using Cosine Similarity
## Overview
This PySpark project aims to build a movie recommendation system based on user ratings. We have two datasets:


1. **u.item**:

    - Contains movie information, including an ID column and the movie name.
We focus on the ID column and movie names for our recommendation system.



2. **u.data**:

    - Contains user ratings for movies, including userID, movieID, rating, and timestamp.
Our goal is to suggest similar movies based on users’ scores.



## Cosine Similarity
Cosine similarity is a metric used to measure the similarity between two vectors. In our case, we treat each movie as a vector, where each dimension represents a user’s rating. The cosine similarity between two movie vectors indicates how similar their rating patterns are. A higher cosine similarity means the movies are more alike in terms of user preferences.
Mathematically, the cosine similarity between vectors A and B is calculated as:
$$\text{Cosine Similarity} = \frac{{\sum_{i=1}^{n} A_i \cdot B_i}}{{\sqrt{\sum_{i=1}^{n} A_i^2} \cdot \sqrt{\sum_{i=1}^{n} B_i^2}}}$$

## Movie Introduction Standards
To recommend movies, we follow these standards:


1. **Score Threshold**:

    - We consider a minimum cosine similarity score of 97% as a threshold for recommending similar movies.
If the cosine similarity between two movies exceeds this threshold, they are considered similar.



2. **Co-Occurrence Threshold**:

    - We validate movie proposals based on co-occurrence.
If both movies have been seen by different users (co-occurrence count ≥ 50), we recommend them.

## Results
To demonstrate the effectiveness of our movie recommendation system, let’s consider an example. Suppose we provide the algorithm with the movie ID **56**, which corresponds to the movie “**Pulp Fiction**”. We want the system to suggest similar movies based on user ratings and cosine similarity.

### Example Recommendation for Movie ID 56 (Pulp Fiction)
1. **Movie: Smoke**
    - Cosine Similarity Score: **0.9743** (exceeds the threshold)
    - Co-occurrence count: **68** (seen by different users)
    - Recommendation: **Highly similar to** “**Pulp Fiction**.”
2. **Movie: Reservoir Dogs**
    - Cosine Similarity Score: **0.9740** (exceeds the threshold)
    - Co-occurrence count: **134** (seen by different users)
    - Recommendation: **Strongly related to** “**Pulp Fiction**.”
3. **Movie: Donnie Brasco**
    - Cosine Similarity Score: **0.9738** (exceeds the threshold)
    - Co-occurrence count: **75** (seen by different users)
    - Recommendation: **Recommended alongside** “**Pulp Fiction**.”
These recommendations are based on the cosine similarity between movie vectors and satisfy both the score and co-occurrence thresholds. Users who enjoyed “Pulp Fiction” are likely to appreciate these similar movies as well.

Feel free to explore more recommendations using our movie recommendation system! 🎥🍿