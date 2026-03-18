# Yelp Network Analysis: Social Graph & Review Dynamics

## Overview

This project explores user behaviour and business interactions on a large-scale review platform by combining data cleaning, statistical analysis, and graph modelling.

The goal is to understand:
- How users interact with businesses  
- How social connections influence activity  
- Patterns in reviews, ratings, and engagement  

---

## Key Components

### 1. Data Processing Pipeline

Raw datasets were cleaned and structured using Python:
- Business data  
- User data  
- Reviews  
- Tips  

Cleaning involved:
- Handling missing values  
- Normalising formats  
- Extracting relevant features  
- Preparing data for graph construction  

---

### 2. Graph Construction

A heterogeneous network was constructed with:

#### Nodes
- Users  
- Businesses  

#### Relationships
- `FRIENDS_WITH` (user–user connections)  
- `REVIEWED` (user → business)  
- `TIPPED` (user → business)  
- `RECOMMENDED` (inferred relationships)  

This forms a multi-relational social graph capturing both interaction and influence.

---

## Network Visualisation

![Graph Visualisation](graph.png)

- Orange nodes represent businesses  
- Purple nodes represent users  

The graph highlights:
- Highly connected hubs (active users and popular businesses)  
- Community clusters  
- Sparse peripheral users  

---

## Statistical Analysis

### Review Distribution
- 5-star reviews dominate the dataset  
- Lower ratings (1–2 stars) are significantly fewer :contentReference[oaicite:0]{index=0}  

### Review Length vs Rating
- Mid-range ratings (2–4 stars) tend to have longer reviews  
- 5-star reviews are shorter on average :contentReference[oaicite:1]{index=1}  

This suggests that moderate experiences generate more detailed feedback.

---

### User Activity
- Most users write very few reviews:
  - Median: 2 reviews  
  - Average: approximately 2.2 reviews :contentReference[oaicite:2]{index=2}  

- A small number of users are highly active:
  - Top user: 577 reviews :contentReference[oaicite:3]{index=3}  

This indicates a long-tail distribution of engagement.

---

### Top Businesses by Review Count
- High engagement is concentrated among large chains such as Starbucks, McDonald's, and Chick-fil-A :contentReference[oaicite:4]{index=4}  

---

## Key Insights

- User activity follows a heavy-tailed distribution  
- A small number of users and businesses act as network hubs  
- Social connections and repeated interactions create clustered communities  
- Review behaviour varies with sentiment:
  - Extreme ratings tend to be shorter  
  - Moderate ratings tend to be more detailed  

---

## Tech Stack

- Python  
- Pandas, NumPy  
- Jupyter Notebooks  
- Graph modelling (Neo4j or equivalent)  

---

## Project Structure

```
.
├── data_cleaning/
│   ├── cleaning_business_dataset.ipynb
│   ├── cleaning_user_dataset.ipynb
│   ├── cleaning_reviews_dataset.ipynb
│   └── cleaning_tips_dataset.ipynb
│
├── graph_construction/
│   ├── Create_UserNode
│   ├── Create_BusinessNode
│   ├── Create_FRIENDS_WITH_Relationship
│   ├── Create_REVIEWED_Relationship
│   ├── Create_TIPPED_Relationship
│   └── Create_RECOMMENDED_Relationship
│
├── analysis/
│   ├── Sentiment Analysis.ipynb
│   ├── DescriptiveStatsForReviews.json
│   ├── StarRatingDistribution.json
│   ├── AverageTextLengthByRating.json
│   └── TopBusiness(reviewcount).json
│
└── visualisations/
    └── graph.png
```
---

## How to Run

1. Run the data cleaning notebooks:
```bash
jupyter notebook

Execute graph construction scripts (e.g., Neo4j or equivalent graph database)

Run analysis notebooks to reproduce results

Future Work

Apply community detection algorithms

Analyse information diffusion across the network

Build recommendation systems using graph structure

Study influence of highly central users
