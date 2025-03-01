---
layout: post
title: "NDCG Score: Fine-Tuning Recommendation System Evaluation"
date: 2025-02-20
categories: 
author: Nikhil Singh
background: '/img/ndcg-score.jpg'
---

# NDCG Score: Fine-Tuning Recommendation System Evaluation

## Table of Contents
1. [Introduction: Why NDCG?](#introduction-why-ndcg)
2. [Basic Fundamentals: DCG & IDCG](#basic-fundamentals-dcg--idcg)
3. [Hello World Example: Simple NDCG Demo](#hello-world-example-simple-ndcg-demo)
4. [Handling Larger Systems: Implicit vs. Explicit Data](#handling-larger-systems-implicit-vs-explicit-data)
5. [Managerial Perspective: Leveraging NDCG Insights](#managerial-perspective-leveraging-ndcg-insights)
6. [Real-Life Use Case: E-Commerce Recommendations](#real-life-use-case-e-commerce-recommendations)
7. [New Metrics: Hitrate NDCG & Beyond](#new-metrics-hitrate-ndcg--beyond)
8. [Conclusion](#conclusion)
9. [References](#references)

---

## Introduction: Why NDCG?
NDCG (Normalized Discounted Cumulative Gain) is a ranking-centric metric. Unlike accuracy-based approaches, it emphasizes the position of relevant items, crucial to understand user satisfaction in recommender systems.

- `NDCG score` also explains how well the top-N recommendations match the actual user interactions.
- `DCG` explains the *gain* of items based on positions. `NDCG` normalises it.

From a ML lead point of view, a higher NDCG means users see more relevant items up front. It is consistent with other KPIs like engagement and conversion.

---

## Basic Fundamentals: DCG & IDCG
- **DCG**: Summation of relevance scores, discounted by log of the position.

$$DCG = \sum_{i=1}^{k} \frac{rel_i}{\log_2(i+1)}$$

- **IDCG**: Ideal DCG—what your DCG would be if all relevant items were at the top.  

- **NDCG**: Normalizes results for easy comparison across different datasets.

$$NDCG = \frac{DCG}{IDCG}$$

---

## Hello World Example: Simple NDCG Demo
*How a small difference in ordering affects NDCG.*

```
Scenario              k   NDCG Score
------------------------------------
Bad Predictions       5    0.6957
Better Predictions    5    0.7182
Ideal Ranking         5    1.0000
Truncated (k=4)       4    0.3520
Tied Scores           5    0.5000
```


🔗 **[Open NDCG Sample Notebook](https://github.com/nikhilsingh13/PythonHacks/blob/main/blog-work/ndcg-score/ndcg_sample_nb1.ipynb)**


---

## Handling Larger Systems: Implicit vs. Explicit Data
1. **Explicit**: Ratings, likes, or feedback forms. NDCG evaluates how well you’re ranking items users explicitly rated highly.  

    🔗 **[Script for NDCG score on explicit dataset & algo comparison](https://github.com/nikhilsingh13/PythonHacks/blob/main/blog-work/ndcg-score/surprise_explicit_ndcg.py)**

    - `surpriselib` is used for trying different algorithm.

    ```
    Algorithm       NDCG@10  Runtime (s)
    --------------------------------------
    SVD             0.0470   3.35
    SVD++           0.0692   48.73
    NMF             0.0062   3.02
    KNNBasic        0.0004   28.34
    KNNWithMeans    0.0016   31.12
    KNNWithZScore   0.0014   33.73
    KNNBaseline     0.0010   37.54
    SlopeOne        0.0015   23.65
    CoClustering    0.0058   2.91
    ```

2. **Implicit**: Clicks, spend time (behavioural data), or purchases. NDCG helps interpret real-world engagement signals, highlighting the top actions you most want to rank first.

🔗 **[Script for NDCG score calculation on implicit dataset & comparison](https://github.com/nikhilsingh13/PythonHacks/blob/main/blog-work/ndcg-score/pyspark_ndcg_implicit.py)**

Once you check / run the script preparing a linear rec-sys model on `lastfm` data available publicly ([here](http://mtg.upf.edu/static/datasets/last.fm/lastfm-dataset-360K.tar.gz)).

The results are:    

    - NDCG@10 - All Products: 0.0025                                                  
    - NDCG@10 - Top Played Products Only: 0.0022

> This is not a good NDCG. A low NDCG score suggests weak recommendation quality. This is expected because of high sparsity and noise in implicit datasets. Also, the model we trained is a linear ALS model.

> ALS: a matrix factorisation model which assumes structured rating behaviour. 
    In an implicit dataset (clicks, plays, purchases, etc.), such structure is not usually captured.

An improvement could be to try:

1. Weighted confidence-based ALS
2. Hybrid model
3. Noise filtering before trying ALS

---

## Managerial Perspective: Leveraging NDCG Insights
- **Strategy**: Align recommended items with high-relevance or high-value categories.  
- **Goal Tracking**: A higher NDCG correlates with increased user satisfaction, retention, and ultimately revenue.  
- **Dashboard Integration**: Combine NDCG with business KPIs (sales, CTR) to see direct impact of your recommendation algorithm adjustments.

---

## Real-Life Use Case: E-Commerce Recommendations
- **Example**: Online retailer boosting conversions by rearranging product listings.  
- **Process**: Use NDCG to measure whether the “top recommended products” truly match user interest.  
- **Result**: Data-driven, consistent improvements in A/B tests—clear wins for the product team.

---

## New Metrics: Hitrate NDCG & Beyond
- **Hitrate NDCG**: A blend of immediate user “hits” and the ranking-based viewpoint.  
- **Other Variants**: MRR (Mean Reciprocal Rank), MAP (Mean Average Precision), etc.  
- **Why Expand?**: Different business objectives—some might care about quick discovery (hitrate), others about deep engagement (DCG-based).

---

## Conclusion
NDCG is not just a metric—it’s a direct KPI through which one can see 
- ranking performance
- user engagement

and can connect business outcomes.

---

## References
- 🔗 [NDCG paper](https://arxiv.org/abs/1304.6480)
- [MovieLens Dataset](https://grouplens.org/datasets/movielens/)
- [Jupyter Notebook / GitHub Repo](#)
