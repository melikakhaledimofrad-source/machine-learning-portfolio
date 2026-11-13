# Machine Learning Portfolio

Welcome to my Machine Learning repository. This repository documents hands-on experiments, algorithms, and practical implementations.

## Projects Directory

| # | Project Name | Tech Stack | Description | Notebook |
|---|---|---|---|---|
| 01 | Pet Store Recommendation System | Python, Scikit-learn, Pandas, NumPy | An item-based collaborative recommendation engine using K-Nearest Neighbors (KNN) and Euclidean distance to recommend missing pet products to customers. | [View Project](01-customer-recommendation-system.ipynb) |
| 02 | User-Genre Movie Recommender | Python, Scikit-learn, Pandas, NumPy | A user-based collaborative filtering recommender using K-Nearest Neighbors (KNN) and Euclidean distance to recommend unviewed movie genres. | [View Project](02-movies-simple-recommendation-system.ipynb) |
| 03 | IMDB Content-Based Movie Recommender | Python, Scikit-learn, Pandas, NumPy | A content-based movie recommendation system using text vectorization (CountVectorizer) and Cosine Similarity over metadata features (cast, director, genres). | [View Project](03-movie-recommendation-system.ipynb) |

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

## Project 02: User-Genre Movie Recommender Overview

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
```
گگگگ
## Project 03: IMDB Content-Based Movie Recommender Overview

### Objective
Develop a content-based recommendation engine on the IMDB Top 1000 dataset to suggest the top 5 most similar movies given an input movie title, evaluated via text token similarity across directors, main cast members, and movie genres.

### Workflow and Architecture
1. **Feature Selection & Missing Value Handling**: Filtered the essential feature subset (`Series_Title`, `Genre`, `Director`, `Star1`, `Star2`, and `Star3`) and handled potential missing records across metadata columns using `.fillna('')`.
2. **Text Preprocessing & Normalization**: Normalized multi-word entity names (directors and actors) by replacing spaces with underscores (`_`) to ensure full names are treated as distinct, single tokens during tokenization (e.g., `Christopher Nolan` $\rightarrow$ `Christopher_Nolan`). Cleaned commas and whitespace from the `Genre` strings.
3. **Feature Combination (`Movie_vector`)**: Combined all processed metadata attributes into a single comprehensive text representation per movie row using string aggregation (`.agg(' '.join, axis=1)`).
4. **Vectorization (`CountVectorizer`)**: Built a token count matrix ($1000 \times M$) converting combined text metadata into bag-of-words sparse vectors.
5. **Similarity Modeling (Cosine Similarity)**: Computed pairwise angular distances across all 1,000 films to produce a $1000 \times 1000$ symmetric similarity matrix.
6. **Recommendation Logic**: Queried movie index by title, extracted corresponding pairwise similarity scores, sorted in descending order, excluded the queried movie itself, and retrieved the top 5 nearest movie titles with their respective similarity metrics.

### Skills and Technologies
- **Languages**: Python 3
- **Data Manipulation**: Pandas, NumPy
- **Natural Language Processing / Vectorization**: Scikit-Learn (`CountVectorizer`)
- **Metric Computation**: Scikit-Learn (`cosine_similarity`)
- **Tools**: Jupyter Notebook, Git, GitHub

### Output and Example Results
Given an input movie title, the system successfully filters, vectorizes, and computes similarity scores to output the top 5 most contextually relevant movie recommendations based on shared cast, directors, and genres.

Recommendation Output: ['sci-fi']
--------------------------------------------------
