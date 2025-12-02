# 🩺 DoctorChat-GPT2-Fine-Tuning

This repository contains the code for fine-tuning a **GPT-2** Causal Language Model (CLM) to function as a conversational medical assistant or "Doctor Chatbot." The project utilizes a publicly available dataset of patient-doctor conversations.

## 📁 Repository Structure

The core functionality is contained within a single file:

* **doctorchat_model_using_gpt2.ipynb:** Contains the complete pipeline, including data loading, custom preprocessing for conversational format, model fine-tuning (using Hugging Face `Trainer`), evaluation, and a final inference example to test the model's capabilities.

## 📊 Dataset Overview

| Attribute | Details |
| :--- | :--- |
| **Source** | Hugging Face - `LinhDuong/chatdoctor-200k` |
| **Records** | 207,408 conversational samples |
| **Columns Used** | `instruction` (Patient Query) and `output` (Doctor Response) |

## 🛠️ Tools & Techniques Used

| Component | Technique/Model | Details |
| :--- | :--- | :--- |
| **Base Model** | GPT-2 (Causal Language Model) | Fine-tuned for conversational generation. |
| **Training Framework** | Hugging Face `transformers` and `Trainer` | Optimized training setup on GPU (if available). |
| **Data Format** | Custom conversational sequence (`[BOS]Instruction: <query>\nAssistant: <response>[EOS]`) | Ensures proper context learning for dialogue. |
| **Inference Parameters** | Sampling, Top-K, Top-P, and Repetition Penalty | Controls the quality and coherence of the generated medical responses. |

## 🧪 Model Performance (After 1000 Steps)

| Metric | Result |
| :--- | :--- |
| **Final Training Loss** | 2.689600 |
| **Final Validation Loss** | 2.552605 |

## ⚠️ **Important Note**

**This model is for educational and experimental purposes only. The generated output may contain medically inaccurate or unsafe advice (e.g., suggesting a cold bath or non-standard medication). Do not use this chatbot for real medical consultation or diagnosis.**
