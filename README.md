# RECOMMENDATION-SYSTEM

"COMPANY": CODTECH IT SOLLUTIONS

"NAME": T.SRIYANSH

"INTERN ID":CT04DM652

"DOMAIN": MACHINE LEARNING

"DURATION": 4 WEEKS

"MENTOR": NEELA SANTHOSH

 DESCRIPTION 

 
  **Building a Recommendation System Using Collaborative Filtering and Matrix Factorization**

 **Introduction**
Recommendation systems are essential tools in modern digital platforms, helping users discover relevant content based on their preferences and behavior. In this project, we implement a **movie recommendation system** using **collaborative filtering (CF)** and **matrix factorization (MF)** techniques. The system is built using the **MovieLens 100K dataset**, which contains 100,000 movie ratings from users. We compare different recommendation approaches—**user-user CF, item-item CF, and Singular Value Decomposition (SVD)-based MF**—and evaluate their performance using **Root Mean Squared Error (RMSE)**.



 **Dataset Overview**
The **MovieLens 100K dataset** consists of:
- **100,000 ratings** (1-5 scale) from **943 users** on **1,682 movies**
- Movie metadata (title, genres, release date)
- No duplicate ratings (ensured via preprocessing)

 **Data Preprocessing**
1. **Loading & Merging Data**  
   - Ratings (`u.data`) and movie details (`u.item`) are loaded and merged.
   - Duplicate entries (if any) are handled by taking the **average rating per user-movie pair**.

2. **Train-Test Split**  
   - The dataset is split into **80% training** and **20% testing** for evaluation.

3. **User-Item Matrix**  
   - A pivot table is created where rows represent **users**, columns represent **movies**, and values are **ratings** (0 if unrated).



 **Recommendation Techniques Implemented**

 **1. User-User Collaborative Filtering**
- **Concept**: Recommends movies based on ratings from similar users.
- **Steps**:
  1. Compute **cosine similarity** between users.
  2. Find **top-K similar users** for a target user.
  3. Predict ratings for unrated movies using a **weighted average** of similar users' ratings.
- **Pros**:
  - Works well when user preferences are stable.
  - Good for cold-start recommendations if user history is available.
- **Cons**:
  - Computationally expensive for large user bases.
  - Struggles with sparse data.

 **2. Item-Item Collaborative Filtering**
- **Concept**: Recommends movies similar to those a user has liked.
- **Steps**:
  1. Compute **cosine similarity between movies** (based on user ratings).
  2. For a target user, find **top-K similar movies** to those they rated.
  3. Predict ratings using a **weighted average** of similar movies.
- **Pros**:
  - More stable than user-user CF (item similarities change less frequently).
  - Works well when the item catalog is smaller than the user base.
- **Cons**:
  - Requires frequent updates if item features change.

 **3. Matrix Factorization (SVD)**
- **Concept**: Decomposes the user-item matrix into **latent factors** (hidden features).
- **Steps**:
  1. Normalize ratings by subtracting user means.
  2. Apply **Singular Value Decomposition (SVD)** to extract latent features.
  3. Reconstruct the rating matrix for predictions.
- **Pros**:
  - Handles sparsity better than CF.
  - Captures complex patterns via latent factors.
- **Cons**:
  - Requires tuning (number of latent factors, regularization).


**Key Findings**
1. **Matrix Factorization (SVD) performs best**, likely because it captures **latent patterns** in user preferences.
2. **Item-Item CF is better than User-User CF** for this dataset, possibly due to more stable movie similarities.
3. **Cold-start problem**: All methods struggle with new users/movies (no prior ratings).



 **Conclusion**
This project demonstrates how **collaborative filtering and matrix factorization** can be used to build an effective recommendation system. While **SVD-based MF** provides the best accuracy, **item-item CF** is a strong alternative for scenarios needing interpretability. Future improvements could include:
- **Hybrid models** (combining CF with content-based filtering).
- **Deep learning approaches** (Neural Collaborative Filtering).
- **Real-time updates** for dynamic recommendations.
