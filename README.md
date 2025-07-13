# Loan Approval RAG Q\&A Chatbot

This project implements a Retrieval-Augmented Generation (RAG) Q\&A chatbot that answers questions about a loan approval dataset using LangChain, Hugging Face models, and a command-line interface. The chatbot retrieves relevant information from the dataset and generates natural language responses, making it ideal for interactively analyzing loan approval data.

The code is designed to run in **Google Colab** and is optimized for portability, making it suitable for deployment on GitHub. It uses lightweight models to ensure compatibility with Colab's free tier.

---

## 🧾 Project Overview

**Purpose**: Build a Q\&A chatbot to answer queries about the Kaggle Loan Approval Prediction dataset.

### 🛠 Technologies

* **LangChain**: For document retrieval and RAG pipeline.
* **Hugging Face**:

  * `distilbert-base-uncased` for embeddings
  * `distilgpt2` for text generation
* **Chroma**: Vector store for efficient document retrieval
* **Pandas**: For dataset processing

### 📂 Dataset

* `Training Dataset.csv` from [Kaggle Loan Prediction Dataset](https://www.kaggle.com/datasets/ninzaami/loan-predication)

---

## ✨ Features

* Retrieves relevant loan records based on user queries using semantic search
* Generates concise, natural language answers using a lightweight language model
* Handles questions about loan status, applicant details, and more
* Optimized for Google Colab (minimal resource requirements \~2GB VRAM)
* Well-commented code for easy understanding and future modifications

---

## 💡 Usage

### Example Queries

* `What is the loan status for Loan ID LP001002?`
* `How many loans were approved for married applicants?`
* `What is the average loan amount for self-employed applicants?`

### Output Format

Example output:

```
Answer: The loan status for Loan ID LP001002 is Approved.

Sources:
1. Loan ID: LP001002, Gender: Male, Married: No, ..., Loan Status: Y
2. ...
```

---

## 🧩 Code Structure

| Function            | Description                                             |
| ------------------- | ------------------------------------------------------- |
| `load_dataset`      | Loads the CSV and converts rows into text summaries     |
| `prepare_documents` | Splits data into chunks for retrieval                   |
| `setup_retriever`   | Creates Chroma vector store using DistilBERT embeddings |
| `setup_llm`         | Initializes `distilgpt2` for text generation            |
| `create_rag_chain`  | Combines retriever and generator into RAG pipeline      |
| `answer_query`      | Processes a single user query                           |
| `chatbot`           | Runs the main CLI loop for interaction                  |

---

## 🚀 Future Improvements

* Use more powerful models via APIs (e.g., OpenAI, Hugging Face)
* Add a GUI using **Gradio** or **Streamlit**
* Improve handling of statistical queries with built-in dataset analysis

---
