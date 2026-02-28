---
title: 'User Profiling in Social Media'
summary: 'A machine learning pipeline to infer age, gender, and personality traits from Facebook data — using liked links, status updates, and profile pictures.'
tags:
  - Machine Learning
  - Python
  - Classification
date: '2024-06-01T00:00:00Z'

external_link: ''

image:
  caption: ''
  focal_point: Smart

links: []

url_code: ''
url_pdf: ''
url_slides: ''
url_video: ''

slides: ''
---

## Overview

This project was completed as part of TCSS555 at the University of Washington, Tacoma, in collaboration with Sammy Franklin and Lang Wang. The goal was to build a system that infers user characteristics — **age range, gender, and the Big Five personality traits (OCEAN)** — from Facebook data provided by the myPersonality dataset. Each team member owned a different data modality: I handled **Facebook Likes (relation data)**, Sammy handled status text, and Lang handled profile pictures.

---

## My Contribution: Inference from Liked Links

My responsibility was to develop the full pipeline for predicting **age range** and **gender** from users' Facebook liked links (relation data).

### Data Processing

The raw relation data mapped user IDs to liked page links. I restructured this into a user-centric format using Pandas: iterating through the relation data to consolidate each user's likes into a single row, then merging with the profile data via an inner join. For age inference, I applied a piecewise bucketing function to convert raw ages into four groups (under 25, 25–34, 35–49, 50+), encoded as integer labels for compatibility with sklearn models.

### Model Training

The consolidated like-link strings were fed into a **CountVectorizer**, producing a sparse binary matrix (users × unique like IDs) used as the feature matrix `X_train`. I experimented with several classifiers:

- Naive Bayes (initial baseline)
- Logistic Regression
- XGBoost
- Random Forest
- Support Vector Machines (gender only)

Ultimately, an **ensemble using majority voting** across Naive Bayes, Logistic Regression, and XGBoost yielded the best results. Both the vectorizer and trained models were serialized with Pickle for use at inference time.

### Prediction & Ensemble Voting

At prediction time, each model in the ensemble produced an independent prediction, stored in a DataFrame. The **mode** across models was taken as the final prediction — a simple but effective voting strategy. Age predictions were converted back to their string group labels before submission.

### Experiment: Removing Infrequent Likes

I ran an ablation experiment to test whether removing the least-frequently liked links improved accuracy. Removing up to 5 of the rarest links showed a modest **improvement in gender accuracy** locally, but **hurt age range accuracy** — and both metrics declined on the evaluation VM, suggesting the removal introduced noise rather than reducing it.

### Results

| Test Type        | Age Range Accuracy | Gender Accuracy |
|-----------------|--------------------|-----------------|
| Training Data   | 0.63               | 0.82            |
| Evaluation Data | 0.66               | 0.82            |

Gender, as a binary classification task, was the stronger result at **0.82** on both training and evaluation data. Age range accuracy improved by 3% from training to evaluation, finishing at **0.66** across four categories.

---

## Team Results Summary

| Modality       | Model                         | Age Acc | Gender Acc | OCEAN Avg RMSE |
|---------------|-------------------------------|---------|------------|----------------|
| Likes (Dean)  | Ensemble (NB + LR + XGBoost)  | 0.66    | **0.82**   | —              |
| Text (Sammy)  | MLP-2 (tag-partitioned sums)  | **0.562** | 0.731    | 0.726          |
| Text (Sammy)  | LSTM + LIWC                   | 0.508   | 0.675      | **0.716**      |
| Images (Lang) | 2D CNN (Keras/TensorFlow)     | —       | 0.65       | —              |

The like-based ensemble achieved the highest gender accuracy across all modalities, and every team member exceeded the baseline for at least one category.

---

## Tech Stack

- **Python**, Pandas, scikit-learn, XGBoost
- **PyTorch**, NLTK, GloVe embeddings (text models)
- **Keras / TensorFlow** (CNN for images)
- **Pickle** for model serialization
- Ubuntu server for evaluation
