#  Book Recommendation System

##  Overview
This project is a **Hybrid Book Recommendation System** that predicts and suggests books based on a combination of **content-based filtering** and **collaborative filtering**. It enhances the user experience by providing personalized book recommendations.

## 🎯 Objective
The goal of this project is to create an **intelligent book recommendation system** that predicts books a user might like based on:
- **Book content (title, genre, author, description)**
- **User interactions (ratings, shelvings, past preferences)**
- **Similarity between books and users' reading habits**

By utilizing **machine learning techniques**, this system helps users discover books efficiently.

---

##  Dataset
The dataset consists of information about books, including:
- **Title** – Name of the book.
- **Shelvings** – Number of users who added the book to their virtual bookshelf.
- **Ratings** – Average rating of the book given by users.

This dataset forms the foundation for training the recommendation system.

---


##  Methodology
This system uses a **hybrid approach** that combines **content-based filtering** and **collaborative filtering**:

###  1. Content-Based Filtering
- This approach recommends books **similar** to the ones the user has interacted with.
- We use **TF-IDF (Term Frequency-Inverse Document Frequency)** and **cosine similarity** to measure how similar books are based on their textual features (title, description, etc.).
  
###  2. Collaborative Filtering (Using K-Nearest Neighbors)
- This approach recommends books based on **other users’ preferences**.
- We implement **K-Nearest Neighbors (K-NN)** to find books that are frequently liked by users with similar tastes.
- The **K-NN model** identifies the **k most similar books** based on the user-item interaction matrix, where:
  - **Books are treated as data points**
  - **Users’ ratings form a high-dimensional feature space**
  - The model finds books that are closely related based on distance metrics.

- **How K-NN works in this system:**
  1. Construct a **book-user matrix** where each book is represented as a row, and each column represents a user's rating.
  2. Compute **similarities** between books based on their rating patterns.
  3. Identify the **k most similar books** using distance metrics like **cosine similarity** or **Euclidean distance**.
  4. Recommend books that are rated highly by users who have read similar books.

- Example:
If a user rates "Book A" highly, K-NN finds books that have similar user rating patterns and suggests them.


###  3. Hybrid Recommendation
- The final recommendation combines the scores from both **content-based filtering** and **collaborative filtering (K-NN)** to provide **more accurate suggestions**.
- The **hybrid score** is calculated as a weighted combination of content similarity and K-NN-based recommendations.

---

##  Prediction and Ranking
The recommendation system ranks books based on:
1. **Hybrid Score** – A combination of content similarity and collaborative filtering predictions.
2. **Popularity** – Number of times a book has been shelved and its rating.
3. **User Preferences** – Books with high engagement are prioritized.

Example **hybrid recommendation output**:

The Kill Artist (Gabriel Allon #1) - Hybrid Score: 0.4953
The Collector (Gabriel Allon #23) - Hybrid Score: 0.4817
Mr. Blue - Hybrid Score: 0.3000
