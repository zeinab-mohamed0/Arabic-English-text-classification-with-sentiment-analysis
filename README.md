# Arabic-English-text-classification-with-sentiment-analysis

# Overview
A complete NLP pipeline that automatically detects whether input text is Arabic or English, then classifies its sentiment using language-specific trained models. Built as a structured Python project with clean separation of concerns across four modules.

# Project structure
Project/
    ├── main.py                  # Entry point — handles user input and output
    ├── langclassifier.py        # Language detection (Arabic vs English)
    ├── arabictext.py            # Arabic sentiment classifier
    ├── englishtext.py           # English sentiment classifier
    │
    ├── arabic_model.pkl         # Trained Arabic Naive Bayes model
    ├── arabic_vectorizer.pkl    # Arabic TF-IDF vectorizer
    │
    ├── data/
    │   ├── ar_reviews_100k.tsv  # Arabic reviews dataset
    │   └── sentiment_data.csv   # English sentiment dataset
    │
    ├── models/                  # Saved model files
    ├── victorizers/             # Saved vectorizer files
    ├── word clouds/             # EDA word cloud outputs
    │
    └── Task 1 Phase 1.ipynb     # Arabic classifier notebook
        Task 1 Phase 2.ipynb     # English classifier notebook
        Task 1 Phase 3.ipynb     # Language classifier notebook


# System Workflow
User Input (main.py)
       ↓
Language Detection (langclassifier.py)
       ↓
  ┌────┴────┐
Arabic   English
  ↓          ↓
arabictext.py   englishtext.py
  ↓          ↓
   Final Result (language + predicted class)


## Phases
# Phase 1 — Arabic Text Classifier

Dataset: Arabic 100K Reviews
Data preprocessing and cleaning
Exploratory Data Analysis (class distribution, text length, word frequency, word clouds)
Feature extraction with TF-IDF
Model training with Gaussian Naive Bayes
Evaluation with a classification report and a confusion matrix

# Phase 2 — English Text Classifier

Dataset: Sentiment Analysis Dataset
Same pipeline as Phase 1 applied to English text

# Phase 3 — Language Classifier

Combined samples from Phase 1 (Arabic) and Phase 2 (English)
Trained a binary classifier to distinguish between Arabic and English text
Proper stratified splitting to ensure balance from both datasets

# Phase 4 — Full System

Integrated all three models into a structured Python project
No Jupyter Notebooks — pure .py files only
Modular design with clear responsibilities per file
