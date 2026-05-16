# Predictive Modeling for Tumor Marker Scores

## Overview
This project focuses on predicting tumor marker scores (CEA and CA2729) using speech, vocal, and language pattern data collected during storyline sessions.

The goal was to explore whether AI and machine learning models could identify meaningful relationships between vocal biomarkers and tumor marker levels.

## Technologies Used
- Python
- Pandas
- Scikit-learn
- GPT-3
- BERT
- Gradient Boosting
- NLP
- Feature Engineering

## Dataset
The project used:
- Speech and vocal pattern data
- Tumor marker clinical test data
- Weekly aggregated storyline sessions

## Feature Engineering
Additional features were generated using:
- Sentiment analysis
- Emotion detection
- Topic modeling
- MFCC audio features

## Models Used
- Gradient Boosting
- Baseline ML models
- GPT-3 enhanced models
- BERT enhanced models

## Results

| Model | MAE | MSE | R² |
|------|------|------|------|
| Original Dataset - CEA | 0.36 | 0.18 | 0.33 |
| Original Dataset - CA2729 | 6.05 | 67.77 | -0.23 |
| BERT - CA2729 | 5.74 | 44.91 | 0.19 |


## Key Findings
- BERT-based features improved CA2729 prediction performance.
- Speech emotion and semantic features showed predictive potential.
- Feature relevance differed between tumor markers.


## Future Improvements
- More frequent data collection
- Advanced deep learning models
- Ensemble learning approaches
- Better temporal alignment methods
