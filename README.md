
# Bangla Text Summarizer using ML and NLP  

![Bangla Text Summarizer](https://img.shields.io/badge/Bangla-Text%20Summarizer-blue)  
A machine learning project utilizing Google's mT5 model to summarize Bangla text efficiently. This project combines cutting-edge Natural Language Processing (NLP) techniques and pre-trained transformer models to generate concise, meaningful summaries of Bangla text.  

## Table of Contents  
- [Introduction](#introduction)  
- [Features](#features)  
- [Technologies Used](#technologies-used)  
- [Setup Instructions](#setup-instructions)  
- [Usage](#usage)  
- [Project Structure](#project-structure)  
- [Contributors](#contributors)  
- [License](#license)  

---

## Introduction  
Bangla, spoken by over 230 million people worldwide, lacks sufficient computational resources for text summarization. This project bridges the gap by employing Google's multilingual mT5 model to generate summaries for Bangla text.  

### Objectives  
- Automate text summarization in Bangla.  
- Enhance Bangla text processing capabilities using state-of-the-art ML and NLP techniques.  
- Provide a user-friendly summarization tool.  

---

## Features  
- Summarizes Bangla text into concise and accurate outputs.  
- Leverages the pre-trained mT5 model for multilingual capabilities.  
- Custom preprocessing pipeline optimized for Bangla text.  

---

## Technologies Used  
- **Google's mT5 Model:** Pre-trained multilingual transformer.  
- **Python:** Programming language.  
- **Hugging Face Transformers Library:** NLP tools for mT5.  
- **NumPy & Pandas:** Data processing.  
- **TensorFlow/PyTorch:** Model fine-tuning (based on chosen framework).  

---

## Setup Instructions  

### Prerequisites  
- Python 3.11.9 or above.  
- Install dependencies from `requirements.txt`.  

### Steps  
1. Clone the repository:  
   ```bash  
   git clone https://github.com/your-username/bangla-text-summarizer.git  
   cd bangla-text-summarizer  
   ```  

2. Install required libraries:  
   ```bash  
   pip install -r requirements.txt  
   ```  

3. Download the pre-trained mT5 model:  
   ```bash  
   from transformers import MT5ForConditionalGeneration, MT5Tokenizer  
   tokenizer = MT5Tokenizer.from_pretrained("google/mt5-small")  
   model = MT5ForConditionalGeneration.from_pretrained("google/mt5-small")  
   ```  

4. Run the script to test summarization:  
   ```bash  
   python summarizer.py  
   ```  

---

## Usage  
1. Prepare the input Bangla text.  
2. Run the script:  
   ```bash  
   python summarizer.py --input_file <path_to_file> --output_file <output_path>  
   ```  
3. View the generated summary in the specified output file.  

---

## Project Structure  
```
bangla-text-summarizer/  
├── data/                     # Sample Bangla text files  
├── models/                   # Saved fine-tuned models  
├── scripts/                  # Scripts for preprocessing, training, evaluation  
├── requirements.txt          # Dependency list  
├── summarizer.py             # Main script for summarization  
├── README.md                 # Project documentation  
└── LICENSE                   # License file  
```  

---

## Contributors  
- **[Md. Tanjeelur Rahman Labib]** - Project Lead  
- **[Tashin Mahmud Khan]** - Contributor(s)
- **[Md. Tasin Hossain Toha]** - Contributor(s)
- **[Md. Saikot Hossain Sojib]** - Contributor(s) 

---

## License  
This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.  
