# 🎓 Bachelor Thesis Project: Lecture Annotation with Code-Switched Speech

**Author:** Yusuf Ammar

**Supervisors:** Dr. Nada Sharaf, Dr. Caroline Sabty

**University:** German University in Cairo


## 🗣️ Project Overview

This project aims to simplify student note-taking by automatically annotating lecture slides using code-switched speech (English/Arabic) transcriptions. It was developed as part of my bachelor thesis at the German University in Cairo (Feb – July 2022).



## 💡 Key Features

- **Automatic Speech Transcription:**
    
    Code-switched lecture speech (English & Arabic) transcribed with a **13.3% Word Error Rate**, using Azure Speech Recognition.
    
- **Slide Matching:**
    
    Transcribed segments automatically matched to corresponding slides with **90% accuracy**, leveraging a deep learning sentence similarity model.
    
- **Web-Based Lecture Viewer:**
    
    A web interface built with Flask and JavaScript to view slides, record lectures, and generate annotated PDFs.
    
- **Student-Focused Output:**
    
    Outputs a fully annotated PDF with slide content and aligned speech transcriptions for easier review.
    
## ⚡ Challenges & Solutions

### **Challenges**

- ✅ Existing ASR systems only handle **one language at a time**, but lectures contain code-switched English/Arabic speech.
- ✅ Lecturers often **deviate from slides**, making it hard to accurately map speech to slides.

### **Solutions**

- 💡 **Post-processing approach for code-switching:**
    
    Recorded full audio, recognized in both languages, then split into chunks using slide-switch timestamps. Chunks were processed word by word, low-confidence words were filtered out (using thresholds determined by trial and error), and both outputs were combined to improve transcription accuracy.
    
    - 💡**Step 1: Time Alignment**
        
        Text was first split into chunks using slide-switch timestamps. Each chunk was matched to the slide being viewed at that exact time. This avoids errors from fixed silence-based splitting (which fails due to variable speaker pause patterns) and ensures each slide receives only the text spoken during its active display.
        
    - 💡 **Step 2: Sentence Similarity with Deep Learning Model**
        
        Chunks assigned to each slide were further split on silences longer than 5 seconds to detect topic shifts. Text from slides was extracted and each chunk was matched to slide content using a deep learning sentence similarity model to refine mapping accuracy.


## 🧑‍💻 Tech Stack

- **Python**, **Flask**, **JavaScript**, **HTML/CSS**
- **Speech Recognition:** Microsoft Azure Speech Services
- **Deep Learning:** Sentence similarity model for slide-text alignment

---

## 🗂️ Repository Contents

- `/notebooks`: Python notebooks (core processing and matching logic)
- `/demo`: Demo Video & Output PDF
- `/thesis`:  Thesis Paper (Final Submission) & Defense Presentation
- ⚠️ **Note:** Deep learning model files and raw audio data are not included (due to size >10GB). These are stored securely on local and external drives.

---

## 🎥 Demo & Materials

- **Demo Video:** Live experiment on a physics lecture (Newton's Laws), demonstrating transcription and slide annotation.
    - Link: https://www.youtube.com/watch?v=apqZKKyFAbQ
- **Demo Video Output PDF:** Shows final annotated document.
    - Link: https://drive.google.com/file/d/1HgX8TAlGpw16rvoNCuRg2Ft-ZW6knMQb/view?usp=drive_link

---

## 💬 Running Locally

If you'd like to run this project locally, please note:

- Model weights and audio files are not included in this repository.
- Azure Speech Services keys and setup are required (can be renewed if needed).

![1](https://github.com/user-attachments/assets/80bc33b3-0752-42b8-9b15-93c869753a09)
![2](https://github.com/user-attachments/assets/7c37ed72-b112-4cf6-88ac-5cd694a27016)
![3](https://github.com/user-attachments/assets/38f8d9a1-0471-4117-8a1a-c55d4f0a3c91)
