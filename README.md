# TASK2
Uzbek Sentiment Analysis (POS / NEG / NEUTRAL)
Project Overview

This project focuses on sentiment analysis for Uzbek language text, where user comments are classified into three categories:
  Positive
  Negative
  Neutral
The main goal is to build, train, and evaluate machine learning models that can accurately detect sentiment in Uzbek comments collected from different domains (movies, applications, social comments, news discussions, etc.).

I created a high-quality Uzbek sentiment dataset from scratch.
Dataset properties:
Total samples: 465
Balanced dataset:
155 Positive
155 Negative
155 Neutral
Language: Uzbek
Format: text + label.CSV

Why this matters:
Balanced datasets reduce model bias
Manually curated data increases label quality
Mixed domains improve generalization
Example dataset format:
  ("film juda zerikarli va syujeti sust", "negative")
  ("filmni katta qiziqish bilan tomosha qildim", "positive")
  ("film oddiy, lekin tomosha qilish mumkin", "neutral")


I trained two different approaches:
  Approach 1: Traditional ML (baseline)
TF-IDF
Classical classifiers (used for baseline comparison)
  Approach 2: Transformer-based Model (main model)
Model: xlm-roberta-base
Framework: HuggingFace Transformers
Tokenizer: AutoTokenizer
Training: HuggingFace Trainer API
Training details:
Epochs: 3
Max sequence length: 128
Learning rate: 2e-5
Batch size: 8
Optimizer: AdamW


Final Evaluation Results (Transformer Model)
Epoch	Training Loss	Validation Loss	Accuracy	F1	Precision	Recall
1	No log	1.104298	0.408602	0.334814	0.388889	0.408602
2	No log	0.872333	0.655914	0.649473	0.655165	0.655914
3	No log	0.866041	0.645161	0.633545	0.655972	0.645161


Accuracy: 0.7526881720430108
              precision    recall  f1-score   support

    negative       0.71      0.71      0.71        31
     neutral       0.70      0.84      0.76        31
    positive       0.88      0.71      0.79        31

    accuracy                           0.75        93
   macro avg       0.76      0.75      0.75        93
weighted avg       0.76      0.75      0.75        93


| Model Type          | Accuracy   | Stability | Uzbek Support |
| ------------------- | ---------- | --------- | ------------- |
| Classical ML        | Lower      | Medium    | Weak          |
| Transformer (XLM-R) | **Higher** | **High**  | **Strong**    |
