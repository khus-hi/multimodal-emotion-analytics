# Multimodal Emotion Recognition Analytics Dashboard

This repository contains a **single end-to-end notebook** and a **Power BI dashboard** for analyzing a multimodal emotion recognition model.

The project uses predictions generated for each modality (Audio, Video, Fusion) and visualizes them using a professional analytics dashboard built in **Power BI Service**.

---

## Dataset Used

### RAVDESS — Ryerson Audio-Visual Database of Emotional Speech and Song  
This project uses the **RAVDESS dataset**, a widely used benchmark dataset for emotion recognition.

**Key properties:**
- High-quality recordings of emotional speech
- 8 emotion classes:
  - *neutral, calm, happy, sad, angry, fearful, disgust, surprised*
- Audio + Video modalities available
- Recorded at consistent frame rate and audio quality

**Why this dataset?**
- Balanced and clean  
- Excellent for multimodal emotion research  
- Provides consistent labels across actors  
- Supports audio, video, and multimodal fusion ML models  

**Download link:**  
https://zenodo.org/record/1188976

> **Note:**  
> The dataset itself **is NOT included** in this repository due to licensing.  
> Only the **processed predictions CSV** used for Power BI is included.

---

## Files in this Repository

### `multimodal_emotion_pipeline.ipynb`
A single notebook containing:
- Data loading and preprocessing  
- Parsing the `multimodal_predictions_with_flags.csv` file  
- Calculating accuracy metrics  
- Getting the data ready for Power BI  
- Exporting cleaned outputs for dashboard use

### `data/multimodal_predictions_with_flags.csv`
Final structured prediction table used inside Power BI.

Columns include:
- `fname`, `actor`, `true_emotion`
- `audio_pred`, `audio_conf`, `audio_correct`
- `video_pred`, `video_conf`, `video_correct`
- `fusion_pred`, `fusion_conf`, `fusion_correct`

### `analytics/multimodel emotion.png`
PDF of the Power BI dashboard. 

Link: https://app.powerbi.com/view?r=eyJrIjoiNmVjM2RiMjEtMGM1Ni00ZGQwLThmOGYtNmUzZGRlMWFhMzlhIiwidCI6ImQ1N2QzMmNjLWMxMjEtNDg4Zi1iMDdiLWRmZTcwNTY4MGM3MSIsImMiOjN9

---

## 📊 Power BI Dashboard

The dashboard was built entirely in **Power BI** using the predictions CSV file.

### **Analytics:**
- **KPI Cards:**  
  Fusion Accuracy, Video Accuracy, Audio Accuracy  
- **Model Accuracy by Emotion:**  
  Bar chart comparing Audio / Video / Fusion for all 8 emotions  
- **Classification Breakdown:**  
  Count of predictions per emotion  
- **Confusion Matrix:**  
  True vs Predicted emotion (Fusion Model)  
- **Confidence vs Correctness Scatter Plot:**  
  Fusion Model confidence correlation  
- **Slicer:**  
  Filter dashboard by emotion
---

## Project Overview

The project evaluates a multimodal emotion recognition system with the following components:

### **Modalities (Upstream Model Outputs):**
- **Audio Model:**  
  CNN on Mel-spectrograms  
- **Video Model:**  
  CNN/ViT on extracted face frames  
- **Fusion Model:**  
  Combined audio + video embeddings

### **What This Repository Focuses On**
This repo focuses on **analysis & visualization**, not model training.

Using predictions stored in CSV format, we perform:
- Performance analysis  
- Per-emotion accuracy comparison  
- Visualization of confusion patterns  
- Error breakdown  
- Confidence–accuracy correlation  

These insights are displayed using an attractive, professional Power BI dashboard.
