# Biomedical Information Retrieval with AI: Boolean Query Formalization

## Overview
This repository contains code and resources for the research project *"Empowering Open Medium-Sized GPT Models: Fine-Tuning for Effective Boolean Query Formalization in Biomedical Systematic Reviews."* The project investigates how fine-tuned open-source models like BioGPT can generate high-quality Boolean queries for searching PubMed, aiding biomedical systematic literature reviews (SLRs). 

Our methodology introduces **semi-synthetic labeled data** for training, integrates **MeSH terms and keywords** to enhance search performance, and evaluates models using the **CLEF TAR and FASS datasets**.

---

## Features
- **Fine-tuned GPT Models** (BioGPT, BioT5) for generating PubMed Boolean queries.
- **MeSH & Keyword Generation** for enriching search queries.
- **Semi-synthetic dataset creation** for training AI models.
- **Comparison with ChatGPT and baseline retrieval methods.**
- **Experiments using CLEF TAR and FASS datasets.**

---

## Installation & Setup
### 1. Clone the Repository
```bash
git clone https://github.com/yourusername/BioNLP_BooleanQuery.git
cd BioNLP_BooleanQuery
```

### 2. Install Dependencies
This project requires Python 3.8+ and PyTorch.
```bash
pip install -r requirements.txt
```
---

## Dataset Description
We use two primary datasets for evaluation:

1. **CLEF TAR Dataset**: Used for evaluating search retrieval models.
2. **FASS Dataset**: A benchmark for biomedical systematic reviews.

Additionally, **semi-synthetic labeled datasets** are created by:
- Using PubMed article titles as research topics.
- Generating Boolean queries with ChatGPT 3.5.
- Extracting top-matching PubMed articles for training.
- Fine-tuning models with additional MeSH terms and keywords.

### 📂 Dataset Availability
The following datasets are included in this repository under the **`Datasets/`** folder:
- `Large_TitlesMeSHKeywords_TrainingData.txt` – Large dataset with titles, MeSH terms, and keywords.
- `Small_TitlesMeSHKeywords_TrainingData.txt` – Small dataset with titles, MeSH terms, and keywords.
- `Large_TitlesOnly_TrainingData.txt` – Large dataset with only article titles.
- `Small_TitlesOnly_TrainingData.txt` – Small dataset with only article titles.

---

## Model Training & Fine-Tuning
### 1. Fine-Tuning MeSH & Keyword Generation Models
- **Data Source**: Manually annotated PubMed articles.
- **Training Approach**: BioGPT fine-tuned on MeSH terms & keywords.

### 2. Fine-Tuning Boolean Query Generation Models
- **Input**: Research topic (article title) + generated MeSH & keywords.
- **Output**: Optimized Boolean query for PubMed.
- **Models Trained**:
  - **BioGPT**: Domain-specific Transformer for biomedical text.
  - **BioT5**: A T5-based model fine-tuned for biomedical tasks.

### Training Execution

---

## Usage Guide

---

## Results & Evaluation
### Key Findings:
- **Fine-tuned BioGPT outperforms PubMed’s default search engine.**
- **Achieves comparable or better performance than ChatGPT (zero-shot).**
- **Including MeSH terms & keywords improves recall but affects precision.**

Performance Comparison (Precision @1000):
| Model        | CLEF TAR | FASS |
|-------------|---------|------|
| PubMed Title | 0.0648  | 0.0734 |
| ChatGPT PE  | 0.1517  | 0.1594 |
| **Fine-tuned BioGPT** | **0.2661** | **0.2037** |

---
