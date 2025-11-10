# 🌐 Multilingual Hate Speech Detection using Transformers

This project compares two transformer-based architectures — XLM-RoBERTa and mT5 — for detecting hate speech across multiple languages.
It explores both discriminative (classification) and generative (text-to-text) modeling paradigms for multilingual natural language understanding (NLU).

🚀 Overview
🎯 Objective

To develop and evaluate multilingual hate speech detection models capable of classifying text as hate or non-hate across diverse languages such as English, French, German, and Italian.

## 🧠 Models Compared

XLM-RoBERTa (Base) — a discriminative classifier fine-tuned for binary hate speech detection.

mT5 (Small) — a generative text-to-text model that outputs “yes” or “no” when prompted with “Is this hate speech?”.

## 🧱 Architecture Diagram

                ┌───────────────────────────┐
                │   Multilingual Text Input │
                └────────────┬──────────────┘
                             │
           ┌─────────────────┼───────────────────┐
           │                                     │
  ┌────────▼─────────┐                 ┌─────────▼────────┐
  │  XLM-RoBERTa     │                 │   mT5 Model      │
  │ (Discriminative)  │                 │ (Generative QA)  │
  └────────┬──────────┘                 └────────┬─────────┘
           │                                     │
           │                                     │
   Output: “Hate / Non-Hate”           Output: “Yes / No”
           │                                     │
           └────────────────────┬────────────────┘
                                │
                     ┌──────────▼──────────┐
                     │   Evaluation Layer  │
                     │  (Accuracy, F1 etc.)│
                     └──────────┬──────────┘
                                │
                      Final Comparative Report

## ⚙️ Workflow

1. Setup and Installation
   pip install transformers datasets evaluate torch

2. Data Loading & Preprocessing
- Load and balance multilingual dataset from CSV.
- Stratify samples to ensure equal distribution of hate and non-hate examples.

3. Model Training
- Fine-tune XLM-RoBERTa for 5 epochs.
- Fine-tune mT5 for 15 epochs using constrained “yes/no” generation.

4. Evaluation Metrics
- Accuracy, Precision, Recall, and Weighted F1 Score.
  
5. Multilingual Inference
- Evaluate on sentences in English, French, German, and Italian.

## 📚 Dataset

Multilingual HateSpeech Dataset (Kaggle)

A multilingual dataset containing hate and non-hate text samples across multiple languages.


## 🧩 Tech Stack

Language: Python

Frameworks: PyTorch, Hugging Face Transformers, Datasets, Evaluate

Models: XLM-RoBERTa, mT5-small

Metrics: Accuracy, Precision, Recall, F1

Environment: Google Colab / Jupyter Notebook

## 🔮 Future Work

Implement zero-shot cross-lingual transfer for unseen languages.

Extend dataset coverage with low-resource languages.

Integrate context-aware hate detection (e.g., sarcasm, code-switching).

Compare with LLMs (e.g., GPT, LLaMA) for multilingual moderation.

## 🏁 Summary

This project demonstrates the effectiveness of transformer-based multilingual models for hate speech detection.
By combining XLM-RoBERTa and mT5, it highlights the trade-offs between classification accuracy and generative interpretability — paving the way for safer, more inclusive multilingual AI moderation systems.
