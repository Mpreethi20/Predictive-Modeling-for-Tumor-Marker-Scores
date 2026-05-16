# Predictive-Modeling-for-Tumor-Marker-Scores
Predicting CEA and CA27-29 tumor marker scores from vocal and speech patterns using Gradient Boosting, BERT, and GPT-3 feature engineering. Compares baseline vs. LLM-enhanced models on clinical storyline session data.
Project Overview
This project develops predictive models to estimate tumor marker scores (CEA and CA27-29) based on vocal and speech patterns recorded during storyline sessions. Advanced language models (BERT and GPT-3) were used to engineer additional features from participants' text responses to enhance predictive performance.

📂 Dataset
FileDescriptiondf_storyline_data.csvAssessment IDs, session dates, facial/speech/vocal pattern datadf_tumormarker_data.csvClinical tumor marker test results (CEA & CA27-29 scores, test dates)
Key Data Characteristics
Storyline sessions: Collected every 2 days
Tumor marker scores: Recorded once a week
Storyline data was aggregated weekly to align with tumor marker test frequency

⚙️ Feature Engineering
Language Model Features
Two LLMs were used to extract meaningful features from text responses:
GPT-3 (via LangChain)

Sentiment Analysis → sentiment scores from speech text
Topic Modeling → category and topic scores
Emotion Detection → anger, joy, fear scores

BERT

Contextual semantic features from speech transcripts
Emotion and sentiment embeddings

Example Features

wnlu_category_1_score — presence of specific categories from LLM analysis
mfcc_sma_13_percentile1_0 — 13th Mel-Frequency Cepstral Coefficient (timbral audio feature)


🤖 Modeling Approach
Primary Model: Gradient Boosting

Chosen for its ability to handle complex feature interactions
Well-suited for capturing subtle relationships in vocal/speech data

Models Compared
ModelTargetMAEMSER²Original DatasetCEA0.360.180.33Original DatasetCA27-296.0567.77-0.23GPT-3 EnhancedCEA0.490.36-0.20GPT-3 EnhancedCA27-295.8348.88-0.44BERT EnhancedCEA0.530.37-0.33BERT EnhancedCA27-295.7444.910.19

📊 Key Findings

BERT improved CA27-29 prediction (R² = 0.19), showing that semantic/emotional features can capture patterns relevant to this marker
LLM features did not improve CEA prediction — in some cases increased error, suggesting feature relevance is highly context-specific
Feature importance varied significantly between CEA and CA27-29, highlighting the need for target-specific feature engineering


⚠️ Limitations

Temporal data loss from weekly aggregation of bi-daily sessions
Not all LLM features were useful — some introduced noise rather than signal
Generalization uncertainty — mixed results across tumor markers suggest models may not be robust across different contexts
Infrequent tumor marker collection (weekly) may miss rapid clinical changes


🔭 Next Steps

 Collect more frequent and detailed storyline session data
 Explore additional LLMs and feature extraction techniques
 Hyperparameter tuning and ensemble methods
 Validate model generalizability on new/unseen datasets


🛠️ Tech Stack

Python (Pandas, Scikit-learn, Matplotlib, Seaborn)
BERT (Hugging Face Transformers)
GPT-3 (via LangChain)
Gradient Boosting (Scikit-learn)
Jupyter Notebook
