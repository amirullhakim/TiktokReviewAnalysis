# TikTok Google Play Store Review Sentiment Analysis

This project analyses TikTok Google Play Store reviews using Natural Language Processing. It classifies reviews into positive, neutral and negative sentiment, compares SVM, GRU and BERT, and identifies the main TikTok features linked to user complaints.

## Project Overview

- Raw reviews collected: **40,000**
- Cleaned reviews retained: **14,673**
- Review source: **TikTok Google Play Store**
- Region: **United States**
- Sentiment labeling: **VADER**
- Models compared: **SVM, GRU and BERT**
- Additional methods: **ABSA, opinion mining, trigrams and four-grams**

## Main Results

### Sentiment Distribution

| Sentiment | Percentage |
|---|---:|
| Positive | 52.38% |
| Negative | 31.71% |
| Neutral | 15.91% |

### Model Performance

| Model | Held-Out Macro F1 | Five-Fold Mean Macro F1 |
|---|---:|---:|
| BERT | 0.8918 | 0.8777 |
| GRU | 0.8169 | 0.8025 |
| SVM | 0.7952 | 0.8005 |

BERT achieved the best classification result, while SVM had the fastest training and inference time.

## Main Findings

- Account Management had the highest number of negative mentions.
- App Performance had the highest negative rate at **83.39%**.
- Common complaint phrases included:
  - `account permanently banned`
  - `banned no reason`
  - `multiple violations community guidelines`
  - `app keeps crashing`
  - payment processing problems

## Project Phases

1. Data Collection
2. Data Cleaning
3. Data Preprocessing
4. Exploratory Data Analysis
5. VADER Sentiment Labeling
6. Train, Validation and Test Split
7. Feature Engineering
8. Model Training
9. Model Evaluation
10. Opinion Mining
11. Aspect-Based Sentiment Analysis
12. Visualization and Recommendations

## Required Libraries

Install the required libraries in Google Colab:

!pip install -q pandas numpy scikit-learn nltk spacy tensorflow torch transformers datasets evaluate wordcloud seaborn matplotlib google-play-scraper langdetect contractions pyspellchecker

Install the spaCy English model:

!python -m spacy download en_core_web_sm

## Running in Google Colab

### 1. Upload or Open the Notebook

Open the project notebook in Google Colab.

### 2. Mount Google Drive

from google.colab import drive

drive.mount("/content/drive")

### 3. Change the Project Path

Change `DRIVE_PATH` to the folder where the project files will be saved.

DRIVE_PATH = "/content/drive/MyDrive/SMC_Project"

For example, if the Google Drive folder is named `TikTok_Sentiment_Project`:

DRIVE_PATH = "/content/drive/MyDrive/TikTok_Sentiment_Project"

The folder name must match the actual folder in Google Drive.

### 4. Run the Notebook

Run the notebook from top to bottom because later phases depend on files created by earlier phases.

Recommended order:

1. Install the required libraries.
2. Mount Google Drive.
3. Set `DRIVE_PATH`.
4. Run the phase-folder configuration.
5. Run Phase 1 until Phase 12.
6. Check that each phase saves its output successfully.

## Important Notes

- A Google Colab runtime reset removes variables from memory.
- Files saved in Google Drive will remain available.
- After a runtime reset, rerun the setup and path cells.
- BERT training should use a GPU runtime.
- Do not fit the TF-IDF vectorizer or tokenizer on the test set.
- Keep the test set separate until final evaluation.
- The GRU model uses post-padding and `use_cudnn=False` to avoid masking errors.

## Group Members

| Student ID | Name | Main Responsibility |
|---|---|---|
| 1211110167 | Muhammad Munif Haikal bin Mohd Nizam | SVM and text preprocessing |
| 1211111890 | Amirul Hakim bin Harunarrashid | GRU and VADER sentiment analysis |
| 1211110737 | Ahmad Airiel Harrith bin Ahmad Zahari | BERT and ABSA |

## Academic Use

This project was developed for the CDS6344 Social Media Computing group assignment at Multimedia University.
````
