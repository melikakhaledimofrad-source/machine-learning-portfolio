# Machine Learning Portfolio

Welcome to my Machine Learning repository. This repository documents hands-on experiments, algorithms, and practical implementations.

---

## Projects Directory

| # | Project Name | Tech Stack | Description | Notebook |
|---|--------------|------------|-------------|----------|
| 01 | Pet Store Recommendation System | Python, Scikit-learn, Pandas, NumPy | An item-based collaborative recommendation engine using K-Nearest Neighbors (KNN) and Euclidean distance to recommend missing pet products to customers. | [View Project](./01-customer-recommendation-system.ipynb) |

---

## Project 01: Pet Store Recommendation System Overview

### Objective
Analyze customer order histories in a pet store, find the most behaviorally similar customer using vector distance metrics, and suggest items they have not purchased yet.

### Workflow and Architecture
1. **Data Preprocessing:** Exploding nested order lists into granular product rows.
2. **Feature Engineering:** Creating an interaction matrix using pandas crosstab.
3. **Similarity Modeling:** Fitting NearestNeighbors on customer vectors using Euclidean metric.
4. **Recommendation Logic:** Vector subtraction between the nearest customer and the new customer to identify unpurchased items.

---

## Skills and Technologies
- **Languages:** Python 3
- **Data Manipulation:** Pandas, NumPy
- **Machine Learning:** Scikit-Learn (NearestNeighbors, Distance Metrics)
- **Tools:** Jupyter Notebook, Git, GitHub

---
### Developed by: Melika Khaledi Mofard
