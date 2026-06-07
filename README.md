# ✍️ Bangla Text Summarizer using ML and NLP

[![Python](https://img.shields.io/badge/Python-3.11-3776AB?style=for-the-badge&logo=python)](https://www.python.org/)
[![PyTorch](https://img.shields.io/badge/PyTorch-EE4C2C?style=for-the-badge&logo=pytorch&logoColor=white)](https://pytorch.org/)
[![Hugging Face](https://img.shields.io/badge/Hugging%20Face-Transformers-FFD21E?style=for-the-badge&logo=huggingface)](https://huggingface.co/)
[![mT5 Model](https://img.shields.io/badge/Model-mT5--Small-blue?style=for-the-badge&logo=google)](https://huggingface.co/google/mt5-small)

A machine learning and natural language processing (NLP) application designed to automate text summarization in the Bangla language. By leveraging Google's pre-trained multilingual **mT5 (multilingual Text-to-Text Transfer Transformer)** framework and custom fine-tuning pipelines, the system generates concise, coherent, and abstractive summaries of Bangla documents, news articles, and texts.

* **Abstractive Summarization**: Generates new sentences that capture the core theme, unlike extractive methods.
* **Bangla-Specific Preprocessing**: Optimized tokenization, punctuation handling, and stopword filtering for Bengali scripts.

---

## 🏗️ Summarization Pipeline

The model utilizes a custom text processing pipeline before feeding tokenized inputs into the sequence-to-sequence transformer model.

```
                     [ Raw Bangla Text ]
                              │
                  [ Preprocessing Pipeline ]
             (Sentence Tokenization, Stopwords)
                              │
                    [ mT5 Tokenization ]
                              │
                [ Fine-Tuned mT5 Model ]
             (google/mt5-small + PyTorch)
                              │
                [ Decoded Summary Output ]
```

### Key Stages
1. **Preprocessing**: Normalizes Bangla Unicode characters and filters out corpus noise.
2. **Tokenization**: Uses the SentencePiece tokenizer trained on multilingual corpora to accommodate Bengali vocabularies.
3. **Seq2Seq Inference**: mT5 model architecture processes the input embedding representations to generate natural Bangla summary statements.

---

## ⚡ Tech Stack & Core Libraries

* **Core Framework**: [google/mt5-small](https://huggingface.co/google/mt5-small) — transformer model for multilingual sequence-to-sequence tasks.
* **Deep Learning Engine**: PyTorch / TensorFlow.
* **NLP Toolkit**: Hugging Face Transformers & SentencePiece.
* **Data Processing**: Pandas, NumPy, and Scikit-Learn.
* **Data Collection**: BeautifulSoup / Scrapy (for crawling news articles in notebooks).

---

## 🚀 Quick Start Guide

### 1. Prerequisites
Ensure you have the following installed on your machine:
* Python 3.11+
* CUDA-compatible GPU (highly recommended for fine-tuning, though CPU can run inference)

### 2. Installation & Setup
Clone the repository and install the required dependencies:
```bash
# Clone the repository
git clone https://github.com/TashinMahmud/Bangla-Text-Summarizer-using-ML-and-NLP.git
cd Bangla-Text-Summarizer-using-ML-and-NLP

# Install dependencies
pip install -r requirements.txt
```

### 3. Model Download & Execution
You can download the pre-trained mT5 model automatically and test summarization using the inference script:

```python
# python snippet inside summarizer.py
from transformers import MT5ForConditionalGeneration, MT5Tokenizer

tokenizer = MT5Tokenizer.from_pretrained("google/mt5-small")
model = MT5ForConditionalGeneration.from_pretrained("google/mt5-small")
```

Run the summarizer script against a sample file:
```bash
python summarizer.py --input_file data/article.txt --output_file output.txt
```

---

## 🧭 Project Directory Layout

```
Bangla-Text-Summarizer-using-ML-and-NLP/
├── data/                                      # Sample Bangla raw text files
├── models/                                    # Local fine-tuned checkpoint weights
├── scripts/                                   # Model preprocessing, training, and evaluation scripts
├── bangla-text-summarizer--main/
│   └── article.txt                            # Collected corpus data
├── Bengali_Summarization_Data_Collection.ipynb # Jupyter Notebook for scraping and corpus collection
├── summarizer.py                              # Main inference CLI script
├── requirements.txt                           # Model dependencies
└── README.md                                  # Project documentation
```

---

## 👥 Contributors

* **Md. Tanjeelur Rahman Labib** — Project Lead
* **Tashin Mahmud Khan** — Contributor
* **Md. Tasin Hossain Toha** — Contributor
* **Md. Saikot Hossain Sojib** — Contributor

---

## 📜 License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for complete details.
