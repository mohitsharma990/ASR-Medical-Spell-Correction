# 🩺 ASR Medical Noun Enhancement: A Hybrid NLP Approach

This project develops a specialized **hybrid spell correction system** for enhancing Automatic Speech Recognition (ASR) outputs in the **medical domain**. It is designed to accurately correct misspelled **medication names** and **medical terminology**, which are common points of failure for general ASR models.

The project was developed in a series of **Jupyter notebooks**, documenting a step-by-step approach from data analysis to a robust hybrid model architecture.

---

## 📚 Problem Statement

Automatic Speech Recognition (ASR) systems often struggle with **proper nouns** and **domain-specific vocabulary**.  
In the context of **medical conversations**, this can lead to **critical transcription errors** in medication names and medical terminology.

**Goal:** Build a **spell correction system** that specifically targets these noun-related errors, transforming incorrect ASR output into **accurate, clinically useful text**.

---

## 🚀 The Hybrid Pipeline

The final solution is a **multi-stage pipeline** that combines the strengths of different NLP architectures:

1. **T5 Model (Generative Correction)**
   - Fine-tuned **T5 (Text-to-Text Transfer Transformer)** model for end-to-end correction.
   - Handles a wide range of ASR errors: phonetic substitutions, segmentation issues, etc.
   - Uses a **Noun-Weighted Loss** to prioritize accuracy of critical medical terms.

2. **BERT Model (Contextual Post-Processing)**
   - **PubMedBERT**, a pre-trained BERT with deep medical domain knowledge.
   - Acts as a **second-pass correction** for remaining single-word noun/medical errors.
   - Leverages **contextual understanding** to fill in masked words.

3. **Dictionary Correction (Final Cleanup)**
   - Rule-based dictionary of **medication names** and **medical terms**.
   - Provides **deterministic corrections** for high-confidence known errors.
   - Ensures a **safety net** for the most crucial terms.

---

## 📊 Key Results

The hybrid approach demonstrated significant improvements over traditional baselines:

- **Word Accuracy** → Percentage of words correctly transcribed.  
- **Noun Accuracy** → Specialized metric for medical nouns/terms.  
- **BLEU Score** → Measures fluency and sentence-level quality.

---

## 📁 Repository Structure
├── 0_ASR_Baseline.ipynb         # Initial data exploration & dictionary-based baseline
├── 1_ASR_T5_Fine_Tuning.ipynb   # Fine-tuning T5 for text correction
├── 2_ASR_BERT_Pre_trained.ipynb # Contextual correction using PubMedBERT
├── 3_ASR_Hybrid.ipynb           # Final hybrid pipeline (T5 + BERT + Dictionary)
├── Report.pdf                   # Detailed methodology, challenges, and results
├── requirements.txt             # Python dependencies

---

## ⚙️ Setup Instructions

1. **Clone the repository**
   ```bash
   git clone https://github.com/yourusername/asr-medical-noun-enhancement.git
   cd asr-medical-noun-enhancement
	
 2.	Install dependencies

    pip install -r requirements.txt
