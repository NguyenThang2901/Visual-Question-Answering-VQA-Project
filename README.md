
# Generative VQA: A Complete Visual Question Answering Pipeline

## Overview

This repository features a comprehensive **Visual Question Answering (VQA)** system, covering the entire workflow—from generating datasets with **generative AI** to training a **custom deep learning architecture** capable of answering natural-language questions about animal images.

---

## Key Highlights

- **Automated Dataset Creation** powered by BLIP and Gemini APIs  
- **Image Captioning** performed using BLIP  
- **Question–Answer Generation** via Gemini API  
- **Tailored VQA Architecture**: CNN + LSTM + Attention + LSTM Decoder  
- **Model Training & Evaluation** with visual feedback and loss monitoring  
- **Google Colab Compatible**: Simple setup with GPU acceleration

---

## Project Workflow

### Stage 1: Automated Dataset Generation

```mermaid
graph LR
    A[Animal Image] --> B[BLIP Captioning]
    B --> C[Caption Text]
    C --> D[Gemini Q&A Generation]
    D --> E[Q&A JSON Dataset]
````

* **BLIP**: Produces descriptive captions for each image
* **Gemini API**: Transforms captions into relevant question–answer pairs

---

### Stage 2: Model Training & Evaluation

* **Input Format**: (Image, Question) → VQA Model → Predicted Answer
* Model Components:

  * **CNN**: Extracts visual features from the image
  * **LSTM (Question Encoder)**: Processes the input question
  * **Attention Mechanism**: Aligns textual and visual information
  * **LSTM (Answer Decoder)**: Generates the final answer sequence
* **Evaluation**: Includes prediction visualization and loss tracking during training

---

## Execution Guide

1. Launch the notebook in Google Colab
2. Activate GPU: Go to Runtime → Change runtime type → GPU
3. Mount Google Drive to save outputs and checkpoints 
4. Configure paths within the notebook
5. Run the following functions in order:

   * Captioning: generate_caption()
   * Q&A Generation: get_gemini_qna_json()
   * Model Training: train_vqa()

> Make sure to set your Gemini API Key:

```python
os.environ['GOOGLE_API_KEY'] = 'YOUR_API_KEY_HERE'
```

---

This project was developed for the **Deep Learning course** at **Ton Duc Thang University**.

