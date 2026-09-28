# Capstone Project — Arabic Stance Analysis of Social Media Posts on Sustainability Topics in the UAE

**Author:** Latifa Al Mansoori (202209021)
**Supervisor:** Dr. Linda Smail
**Institution:** Zayed University
**Program:** Capstone Project I

---

## Project Overview

This project investigates how sustainability discourse is expressed 
in Arabic social media posts originating from the UAE. A dataset of 
8,092 Arabic sustainability-related tweets (6,921 after deduplication) 
was classified into three stance categories: **Supportive**, **Critical**, 
and **Neutral**.

## Methodology

Three classification approaches were evaluated:

1. **TF-IDF + Linear SVM** (traditional machine learning)
2. **TF-IDF + Decision Tree** (traditional machine learning)
3. **AraBERT Fine-tuning** (transformer-based, using the 
   `aubmindlab/bert-base-arabertv02-twitter` checkpoint)

Each approach was evaluated under two preprocessing conditions:

- `svm_text`: aggressive normalization (URL/emoji/diacritic removal)
- `bert_text`: light preprocessing (URL/mention removal only)

## Key Results

| Model | Accuracy | Weighted F1 | Macro F1 |
|---|---|---|---|
| SVM + svm_text | 83.12% | 82.86% | 68.79% |
| SVM + bert_text | 83.12% | 82.68% | 64.06% |
| DT + svm_text | 75.47% | 76.12% | 67.53% |
| DT + bert_text | 71.77% | 72.27% | 57.97% |
| AraBERT + svm_text | 88.12% | 88.04% | 78.05% |
| **AraBERT + bert_text** | **88.46%** | **88.49%** | **79.24%** |
| Majority Baseline | 62.63% | 48.23% | 25.67% |

## Requirements

```bash
pip install transformers datasets accelerate evaluate
pip install scikit-learn pandas numpy matplotlib
pip install openpyxl python-calamine# Capstone-Arabic-Stance-Analysis
Zayed University Capstone Project I - Arabic Stance Analysis of Sustainability Tweets
