# Book Recommendation System using Collaborative Filtering

## Overview

This project implements a **collaborative filtering–based recommender system** for books through user ratings. The objective is to compare **neighborhood-based methods** and **latent factor models** in terms of both **rating prediction accuracy** and **Top-N recommendation quality**.

Steps: data cleaning, exploratory analysis, feature engineering, model training, cross-validation, evaluation.

---

## Dataset

The data is taken from Kaggle, https://www.kaggle.com/datasets/arashnic/book-recommendation-dataset/code

* **Books**: ISBN, title, author, and publication metadata
* **Ratings**: User–book ratings on a 1–10 scale

Due to file size constraints, the datasets are **not included** in this repository.

### Data preprocessing steps

* Removed duplicate records
* Cleaned and standardized column names
* Handled missing author values
* Filtered unrealistic publication years
* Removed inactive users and rarely rated books
* Merged book metadata with user ratings

---

## Methods

Three approaches are implemented and compared.

### 1. Cosine Similarity

* Cosine similarity used to identify nearest neighboring books
* Generates interpretable, similarity-based recommendations

### 2. KNN

* Memory-based collaborative filtering
* Evaluated using 5-fold cross-validation
* Performance measured using RMSE

### 3. SVD

* Captures underlying user and item representations
* Evaluated using both RMSE and Top-N recommendation 

---

## Evaluation Strategy

### Rating Prediction

* **5-fold cross-validation**
* Metric: **Root Mean Squared Error (RMSE)**

Lower RMSE indicates better accuracy in predicting user ratings.

### Top-N Recommendation Quality

* **Leave-One-Out Cross-Validation (LOOCV)**
* Generated Top-10 recommendations per user
* Evaluated using **Hit Rate**, measuring whether the held-out item appears in the recommended list

---

## Results

* SVD shows lower RMSE compared to KNN, which indicates that it is has a better predictive performance
* KNN and SVD produced Top-N recommendations, while SVD exhibiting stronger ranking behavior
* Neighborhood-based methods is preferred for interpretability, while matrix factorization is preferred for better generalization

These findings are consistent with established results in recommender systems literature.


---

## Libraries Used

* Python
* pandas, NumPy, SciPy
* scikit-learn
* Surprise
* matplotlib

---

*This project reflects graduate-level applied work in recommender systems, with emphasis on statistical reasoning, evaluation rigor, and reproducibility.*
