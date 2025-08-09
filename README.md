# Spam Detector (Building AI Project)
## Summary
This project is a simple spam detection model using Naive Bayes, created for the Building AI course. It classifies messages as spam or ham based on training data.
A tiny **spam vs. ham** text classifier built from scratch using a Multinomial Naive Bayes model in pure Python.  
This project is intentionally simple to satisfy the **Building AI** course project requirement: it demonstrates data handling, model training, evaluation, and prediction in a transparent way without external ML libraries.

## How it works
- Tokenizes text (lowercase + removes punctuation).
- Trains a Naive Bayes classifier with Laplace smoothing.
- Evaluates accuracy on a random train/test split.
- Predicts on any input message from the command line.

## Files
- `data/spam.csv` — small example dataset (label,text).
- `main.py` — model training/evaluation/prediction script.
- `README.md` — this file.

## Quick start
```bash
# 1) Run evaluation
python main.py --train data/spam.csv

# 2) Predict a custom message
python main.py --train data/spam.csv --predict "Free entry—claim your prize now!"
```

## Example output
```json
{"train_size":24,"test_size":8,"accuracy":0.875,"prediction":{"label":"spam","probs":{"spam":0.929,"ham":0.071},"text":"Free entry—claim your prize now!"}}
```

## Why this meets Building AI criteria
- **Problem framing:** detect unsolicited/spam messages.
- **Data:** small labeled examples included; easy to extend.
- **Method:** classical ML (Naive Bayes), explained in code.
- **Evaluation:** reports accuracy on a held-out test set.
- **Ethics & limitations:** small dataset → not production-ready; may misclassify nuanced messages; users should avoid deploying for filtering critical communications.

## How to extend
- Add more labeled messages to `data/spam.csv` for better accuracy.
- Try character n-grams or TF–IDF weighting.
- Compare against a logistic regression baseline (optional).
- Localize to Arabic by adding Arabic samples and adjusting tokenization.
