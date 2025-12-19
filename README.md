# Movie Recommendation System – Hybrid Approach

## Overview
This project implements a movie recommendation system based on the MovieLens dataset, combining Content-Based Filtering, Collaborative Filtering, and a Hybrid Recommendation Model.  
The goal is to analyze how different recommendation paradigms perform individually and how their weighted hybridization improves recommendation quality.

The system was developed as a Bachelor thesis project at the Faculty of Technical Sciences (FTN), Software Engineering and Information Technologies (SIIT).

---

## Objectives
- Implement and compare multiple recommendation strategies
- Analyze strengths and weaknesses of:
  - Content-Based Filtering (CB)
  - Collaborative Filtering using SVD
- Design a hybrid recommender system with adjustable weighting
- Evaluate models using standard recommendation metrics
- Ensure modular and reproducible experimentation

---

## Dataset
- MovieLens Dataset (GroupLens Research)
- Includes:
  - User ratings
  - Movie metadata (genres, titles)
- The dataset was preprocessed and split into training and test sets using an 80/20 ratio

---

## Recommendation Approaches

### Content-Based Filtering
- Uses movie metadata such as genres
- Represents movies as feature vectors
- Computes similarity between movies
- Generates recommendations based on user preferences

Advantages:
- No cold start for items
- Personalized recommendations

Limitations:
- Limited diversity
- Cannot capture collective user behavior

---

### Collaborative Filtering (SVD)
- Based on the user–item interaction matrix
- Applies Singular Value Decomposition (SVD)
- Learns latent factors representing users and items

Advantages:
- Captures collective behavior
- Strong performance on dense datasets

Limitations:
- Cold start problem
- Requires sufficient interaction data

---

### Hybrid Recommendation Model
The final recommender combines Content-Based and Collaborative Filtering predictions using a weighted sum:

HybridScore = α * CF_score + (1 − α) * CB_score


- Multiple alpha values in the range 0.1 to 0.9 were evaluated
- Enables control over the influence of each model
- Demonstrates trade-offs between personalization and collective behavior

---

## Evaluation Metrics
Models were evaluated on an unseen test set using the following metrics:

- Mean Absolute Error (MAE)
- Root Mean Squared Error (RMSE)
- Precision@K
- Recall@K

The hybrid model shows improved performance compared to individual approaches, depending on the chosen alpha parameter.

---

## Experimental Pipeline
1. Load and preprocess MovieLens data
2. Perform train–test split (80/20)
3. Train:
   - Content-Based model
   - Collaborative Filtering (SVD) model
4. Generate predictions
5. Normalize model outputs
6. Combine predictions using hybrid weighting
7. Evaluate using standard metrics

All evaluation functions were implemented in a modular manner to support experimentation.

---

## Future Improvements
- Integration with Apache Spark for large-scale data processing
- Real-time recommendation pipeline
- Hyperparameter optimization
- Cold-start handling strategies
- Deployment as a REST API

---

## Author
Stefan Djurica  
Faculty of Technical Sciences, University of Novi Sad  
Software Engineering and Information Technologies (SIIT)
