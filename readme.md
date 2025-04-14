# MemoTag Speech Intelligence Module

## Overview
The MemoTag Speech Intelligence module processes anonymized voice clips to extract key speech and linguistic features that could indicate early cognitive impairment. The system leverages audio analysis, natural language processing, and unsupervised machine learning to provide interpretable insights and risk scores.

## Features

### Audio Processing
- **Feature Extraction:**  
  Duration, pause count, pause duration, pause rate, pitch (mean, std), speech_rate_acoustic, spectral_centroid, spectral_rolloff, jitter, and 13 MFCC-based features.
- **Transcription:**  
  Converts speech to text using the SpeechRecognition library and Google’s Speech API.

### Linguistic Analysis
- **Tokenization & Statistics:**  
  Computes word count, sentence count, average words per sentence, hesitation markers, and hesitation rate using NLTK.
- **Advanced Measures:**  
  Calculates vocabulary diversity (type-token ratio), unique word ratio, content word ratio, filler word ratio, proper noun ratio, and computes speech rate as words per minute (WPM).

### Enhanced Feature Engineering (Future Integration)
- **Forced Alignment:**  
  Placeholder for aligning audio with transcribed sentence boundaries to calculate pauses per sentence.
- **Word Substitution Detection:**  
  Uses transformer-based models to flag potential semantic mismatches in word usage.
- **Task-Specific Assessments:**  
  Logic to compare responses against expected words (e.g., naming tasks, sentence completion).
- **Dependency Parsing:**  
  Utilizes spaCy to detect incomplete sentences based on syntactic structure.

### Unsupervised Machine Learning
- **Dimensionality Reduction:**  
  PCA is used to reduce the feature space.
- **Clustering:**  
  KMeans groups samples based on similar speech profiles.
- **Anomaly Detection:**  
  Isolation Forest flags outliers which are integrated into a composite risk score.

### Reporting & API
- **Visualizations:**  
  Generates PCA scatter plots, feature importance bar charts, and feature correlation heatmaps.
- **Formal Report:**  
  Uses Jinja2 templating to generate an HTML report summarizing the analysis, key features, and clinical recommendations.
- **API Function:**  
  The `predict_cognitive_decline_risk` function outputs a risk score along with key speech indicators for a given audio file.

## Extracted Features Overview

The system outputs a comprehensive CSV file (`cognitive_decline_analysis.csv`)

 **Clone the Repository:**  
   ```bash
   git clone https://github.com/AnMaster15/Voice-Based-Cognitive-Decline-Pattern-Detection.git
   cd Voice-Based-Cognitive-Decline-Pattern-Detection

