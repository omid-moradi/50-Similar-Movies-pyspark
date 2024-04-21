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