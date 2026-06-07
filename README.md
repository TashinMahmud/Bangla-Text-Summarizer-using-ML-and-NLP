# ✍️ Multilingual T5 (mT5) Abstractive Bangla Text Summarizer

<div align="center">

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/TashinMahmud/Bangla-Text-Summarizer-using-ML-and-NLP/blob/main/Bengali_Summarization_Data_Collection.ipynb)
[![Python](https://img.shields.io/badge/Python-3.10%2B-3776AB?style=flat&logo=python&logoColor=white)](https://www.python.org/)
[![PyTorch](https://img.shields.io/badge/PyTorch-EE4C2C?style=flat&logo=pytorch&logoColor=white)](https://pytorch.org/)
[![HuggingFace](https://img.shields.io/badge/%F0%9F%A4%97-Transformers-FFD21E?style=flat)](https://huggingface.co/google/mt5-small)

---

An academic research project implementing abstractive text summarization for the Bengali language. This repository houses the data collection notebooks, reference materials, presentations, and design specifications for fine-tuning Google's **mT5 (multilingual Text-to-Text Transfer Transformer)** small model on news corpora and articles.

</div>

---

## 📖 Research & Academic Deliverables

This repository is part of the **CSE 498R** capstone research sequence. The following documentation files outline the methodology and background literature:

*   **[`CSE498R - LITERATURE REVIEW.pdf`](CSE498R%20-%20LITERATURE%20REVIEW.pdf)**: Analysis of existing neural abstractive summarization frameworks and limitations in low-resource Indic languages.
*   **[`CSE498R.30 - Presentation.pptx`](CSE498R.30%20-%20Presentation.pptx)**: Project presentation, experimental configs, and model performance comparisons.
*   **[`FINAL REPORT.docx`](FINAL%20REPORT.docx)**: Full thesis report detailing data structures, model hyper-parameters, loss functions, and evaluation metrics (ROUGE-1, ROUGE-2, ROUGE-L).

---

## 🏗️ Summarization & Crawling Flow

The project focuses on scraping raw Bengali datasets and compiling them into tokenized sequences suitable for sequence-to-sequence transformers:

```
+-----------------------------------------------------+
|              WEB SCRAPING & COLLECTION              |
|  Crawls Bangla news media portals (e.g. Prothom Alo) |
+--------------------------+--------------------------+
                           | (Raw Article HTML)
                           v
+-----------------------------------------------------+
|              TEXT PARSING & CLEANING                |
|  - HTML Tag Stripping (BeautifulSoup)               |
|  - Unicode Normalization & Stopwords Filtering       |
+--------------------------+--------------------------+
                           | (Cleaned Bangla Text)
                           v
+-----------------------------------------------------+
|             TOKENIZATION & EMBEDDING                |
|  - SentencePiece vocab mapping (250k tokens)        |
|  - Embedding layer projection                       |
+--------------------------+--------------------------+
                           | (Tokens IDs)
                           v
+-----------------------------------------------------+
|               google/mt5-small ENGINE               |
|  Fine-tuning sequence outputs via PyTorch loss loops |
+-----------------------------------------------------+
```

---

## ⚡ Tech Stack & Core Libraries

*   **Deep Learning Platform**: PyTorch (GPU accelerated via CUDA).
*   **Model Pipeline**: Hugging Face Transformers & Tokenizers.
*   **Data Scraper**: BeautifulSoup (bs4), Requests (for crawling article text feeds).
*   **Analysis/Scaffold**: Jupyter Notebook, Pandas, NumPy.

---

## 🚀 Getting Started

### 1. Execute the Data Collection
Open the Colab badge at the top of this page or load the notebook locally:
```bash
# Start Jupyter
jupyter notebook Bengali_Summarization_Data_Collection.ipynb
```
The notebook executes web crawler functions to download, parse, and clean raw articles, exporting the final dataset to: `data/article.txt`.

### 2. Dependencies
Install the required packages to run the notebook locally:
```bash
pip install torch transformers sentencepiece beautifulsoup4 requests pandas numpy
```

---

## 👥 Authors

*   **Md. Tanjeelur Rahman Labib**
*   **Tashin Mahmud Khan**
*   **Md. Tasin Hossain Toha**
*   **Md. Saikot Hossain Sojib**

---

## 📜 License

Licensed under the MIT License.
