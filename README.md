# Machine Learning Portfolio

Welcome to my Machine Learning repository. This repository documents hands-on experiments, algorithms, and practical implementations.

## Projects Directory

| # | Project Name | Tech Stack | Description | Notebook |
|---|---|---|---|---|
| 01 | Pet Store Recommendation System | Python, Scikit-learn, Pandas, NumPy | An item-based collaborative recommendation engine using K-Nearest Neighbors (KNN) and Euclidean distance to recommend missing pet products to customers. | [View Project](01-customer-recommendation-system.ipynb) |
| 02 | Movie Recommendation System | Python, Scikit-learn, Pandas, NumPy | A user-based collaborative filtering recommender using K-Nearest Neighbors (KNN) and Euclidean distance to recommend unviewed movie genres. | [View Project](02-movies-simple-recommendation-system-(2).ipynb) |

---

## Project 01: Pet Store Recommendation System Overview

### Objective
Analyze customer order histories in a pet store, find the most behaviorally similar customer using vector distance metrics, and suggest items they have not purchased yet.

### Workflow and Architecture
1. **Data Preprocessing**: Exploding nested order lists into granular product rows.
2. **Feature Engineering**: Creating an interaction matrix using pandas crosstab.
3. **Similarity Modeling**: Fitting NearestNeighbors on customer vectors using Euclidean metric.
4. **Recommendation Logic**: Vector subtraction between the nearest customer and the new customer to identify unpurchased items.

### Skills and Technologies
- **Languages**: Python 3
- **Data Manipulation**: Pandas, NumPy
- **Machine Learning**: Scikit-Learn (NearestNeighbors, Distance Metrics)
- **Tools**: Jupyter Notebook, Git, GitHub

---

## Project 02: Movie Recommendation System Overview

### Objective
Recommend unviewed movie genres to a new user (`user_id = 7`) by quantifying behavioral similarity across user genre interaction histories using K-Nearest Neighbors and Euclidean distance.

### Workflow and Architecture
1. **Data Preprocessing**: Expanding user watch histories containing genre lists into individual observation records.
2. **Feature Engineering**: Constructing a user-genre frequency matrix using `pandas.crosstab` (7 users × 11 genre features).
3. **Similarity Modeling**: Fitting `NearestNeighbors` on historical user vectors with the Euclidean distance metric ($K=5$).
4. **Recommendation Logic**: Filtering out genres already watched by the target user from the preference profile of the most similar historical user ($D \approx 1.732$, User 6).

### Output and Example Results
```text
Neighbors Distance : [1.73205081, 2.23606798, 2.64575131, 2.64575131, 3.0]
Nearest Neighbor   : User ID 6 (Index 5)
Target User Genres : ['mystery', 'thriller', 'adventure']
Nearest User Genres: ['mystery', 'sci-fi', 'thriller']
--------------------------------------------------
Recommendation Output: ['sci-fi']
--------------------------------------------------
