# Tweet Classification for Loneliness

## Overview
This repository contains code for classifying tweets as either "lonely" or "not lonely." The model uses a fine-tuned BERT model for sequence classification.
This is a work in progress and currently on hold ...

### Data Source
The data is sourced from [Kaggle](https://www.kaggle.com/datasets/arshkandroo/behavioural-tweets?select=Lonely_Tweets.csv). Tweets were scraped using the Tweepy API and preprocessed using the NLTK library by the original data collectors. The dataset includes two types of tweets:
- `Normal_Tweets.csv`: Tweets labeled as "not lonely".
- `Lonely_Tweets.csv`: Tweets labeled as "lonely."

### Key Steps
1. **Data Cleaning**:
   - Corrupted files were saved as clean `.csv` files.
   - Index columns were removed, and labels (`0` for normal, `1` for lonely) were added.
2. **Filtering**:
   - Lonely tweets were filtered for keywords (e.g., "alone," "lonely," "no one") to improve quality.
   - Combined dataset includes both normal and filtered lonely tweets.
3. **Dataset Preparation**:
   - Converted the data into a `Hugging Face` dataset.
   - Split into training (80%), validation (10%), and test (10%) sets.
4. **Model Fine-Tuning**:
   - Used `BERT-base-uncased` for sequence classification.
   - Fine-tuned with `Trainer` API for two epochs.
5. **Prediction**:
   - Classifies input tweets using the trained model.