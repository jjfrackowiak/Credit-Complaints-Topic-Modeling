# Credit Complaints Topic Modeling (DS Studies, Project Winter 2023)

## Contents

- `Credict_complaints_TM_Frackowiak.pdf` — Full project report with methodology, analysis, and results
- `TM_credit_project.ipynb` — Jupyter Notebook containing preprocessing, modeling, and evaluation scripts

## Overview

This project aims to propose a framework for the classification of financial products in consumer credit complaints using advanced topic modeling techniques, including Supervised LDA and BERT-based models, to support regulatory compliance, operational efficiency, and customer insight generation.

---

## Objectives

- Classify consumer complaints into four product categories:
  - Checking or savings account
  - Credit card or prepaid card
  - Debt collection
  - Mortgage
- Apply topic modeling to uncover latent themes in complaints.
- Enhance business insight and support regulatory compliance.

---

## Dataset

- **Source**: [CFPB Consumer Complaints](https://www.consumerfinance.gov/data-research/consumer-complaints/)
- **Size**: 120,000 complaint documents
- **Balance**: Evenly distributed across four categories
- **Median Length**: 524 characters per document

---

## Methods

### Data Preprocessing

- Text normalization (lowercasing, punctuation removal, stopword filtering)
- Anonymized token filtering (e.g., removal of "XXXX")
- Lemmatization and tokenization
- Extraction of bigrams for enhanced context

### Feature Engineering

- Construction of a Term Frequency (TF) matrix
- Use of BERT embeddings for document representation

### Models Used

- **Decision Tree Classifier**  
  A benchmark supervised classifier used for comparison.
  
- **Supervised LDA (SLDA)**  
  Topic modeling technique that incorporates label information for better topic-product alignment.
  
- **BERT Topic Modeling**  
  Leverages transformer-based sentence embeddings combined with clustering and classification layers.

---

## Results

| Model                | ROC AUC (Test) | Balanced Accuracy |
|---------------------|----------------|--------------------|
| Decision Tree        | 87.59%         | 81.37%             |
| Supervised LDA       | 96.90%         | 87.60%             |
| BERT Topic + Logit   | 93.30%         | 89.90%             |

- **SLDA** provided the highest ROC AUC, effectively linking latent topics with complaint labels.
- **BERT Topic** showed the strongest performance on classification accuracy, benefiting from semantic embeddings.
- **Decision Tree** served as a strong but less flexible baseline.

---

## Key Findings

- Strong correlation observed between certain topics and complaint categories:
  - *Credit card complaints*: terms like “credit,” “limit,” and “score”
  - *Mortgage complaints*: topics with “loan,” “foreclosure,” “insurance”
- BERT-based topics were more nuanced and less redundant compared to SLDA topics.
- All models demonstrated clear ability to distinguish product categories based on textual patterns.

---

## Business Impact

- **Faster complaint routing** to relevant teams
- **Improved regulatory visibility** through structured topic mapping
- **Actionable customer insights** for product teams and compliance units

---

## Future Directions

- Add support for multilingual complaints
- Deploy models via API for live classification
- Incorporate sentiment analysis for risk scoring

---

## License

MIT License

---

## Author

Jan Frąckowiak
