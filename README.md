# Book Recommender System

## Overview
A hybrid book recommendation system implementing both Collaborative 
Filtering and Popularity-Based recommendation logic, built on a 
dataset of 270,000+ books, 1 million+ ratings and 278,000 users.

## Recommendation Approaches

### 1. Popularity-Based Recommender (Homepage: Top 50)
Identifies the most popular books globally by computing weighted 
average ratings. Only books with a minimum of 250 ratings are 
considered, filtering out statistically unreliable entries with 
few reviews. Used to surface trending titles on the homepage.

### 2. Collaborative Filtering (Core Engine)
Suggests books by identifying users with similar taste profiles 
based on historical rating patterns, the principle being that 
users who agreed in the past will agree in the future.

#### Key Concepts:
**User-Item Matrix:** Ratings data is pivoted into a matrix where 
rows represent books and columns represent users, with each cell 
containing the rating given.

**Data Filtering for Quality:**
- Only "educated users" (users who have rated >=200 books) are 
  included to ensure meaningful preference signals
- Only "famous books" (books with >=50 ratings) are included to 
  ensure sufficient rating density

**Cosine Similarity:** Each book is represented as a vector in 
high-dimensional user space. The similarity between two books is 
computed as the cosine of the angle between their vectors:

similarity = (A·B) / (||A|| × ||B||)

A cosine similarity of 1 means identical rating patterns; 0 means 
no similarity. The top-N most similar books are returned as 
recommendations.

## Dataset
Three CSV files from the Book Recommendation Dataset:
- **Books.csv** - ISBN, title, author, year, publisher, image URLs
- **Users.csv** - User ID, location, age
- **Ratings.csv** - User ID, ISBN, rating (scale 0–10)

## Tech Stack
- Python
- pandas, NumPy
- scikit-learn (cosine_similarity)
- HTML/CSS (frontend templates)
- Pickle (model serialisation)

## Author
**Rijul Thakur**

B.E. Computer Science and Engineering  
Chitkara University (2019–2023)  
Self-initiated project, 2024
