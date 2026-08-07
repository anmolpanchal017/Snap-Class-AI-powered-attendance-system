# ⚙️ SnapClass – AI-Powered Dual-Biometric Attendance System (Backend)

SnapClass is an AI-powered attendance management system that leverages **Face Recognition** and **Voice Biometrics** to automate student attendance. This repository contains the **Flask backend**, REST APIs, AI inference pipelines, and database integration that power the SnapClass web application.

> **Note:** This repository contains only the backend services and AI logic. The Streamlit web application is maintained in a separate repository.

---

## ✨ Features

- 🔗 RESTful APIs for frontend communication
- 👤 Student Registration APIs
- 📷 Face Recognition Pipeline
- 🎤 Voice Recognition Pipeline
- 📚 Subject & Attendance Management
- 🗄️ Supabase PostgreSQL Integration
- 🔒 Secure Attendance Verification
- ⚡ Fast AI Inference for Biometric Authentication

---

## 🧠 AI Pipelines

### 📷 Face Recognition

- Uses **dlib's HOG Face Detector** for face detection.
- Generates **128-dimensional facial embeddings** using **ResNet**.
- Trains a **Linear SVM Classifier** for identity prediction.
- Performs final verification using **Euclidean Distance Thresholding (≤ 0.60)** to reduce false positives.

---

### 🎤 Voice Recognition

- Uses **librosa** for audio preprocessing and Voice Activity Detection (VAD).
- Generates **256-dimensional speaker embeddings (d-vectors)** using **Resemblyzer**.
- Matches speakers using **Cosine Similarity (≥ 0.65)** for authentication.

---

## 🛠️ Tech Stack

- Python
- Flask
- PostgreSQL (Supabase)
- dlib
- OpenCV
- Resemblyzer
- librosa
- scikit-learn
- NumPy
- Pandas

---

## 🏗️ System Architecture

```
Streamlit Frontend
        │
        ▼
 Flask REST APIs
        │
 ┌──────┴─────────┐
 ▼                ▼
Face Recognition  Voice Recognition
 │                │
 └──────┬─────────┘
        ▼
Attendance Validation
        │
        ▼
Supabase PostgreSQL
```

---

## 🚀 Getting Started

### Clone the Repository

```bash
git clone https://github.com/your-username/snapclass-backend.git
cd snapclass-backend
```

### Create a Virtual Environment

```bash
python -m venv venv
```

### Activate Virtual Environment

**Windows**

```bash
venv\Scripts\activate
```

**Linux / macOS**

```bash
source venv/bin/activate
```

### Install Dependencies

```bash
pip install -r requirements.txt
```

### Configure Environment Variables

Create a `.env` file and add the required credentials:

```env
SUPABASE_URL=your_supabase_url
SUPABASE_KEY=your_supabase_key
SECRET_KEY=your_secret_key
```

---

## ▶️ Run the Server

```bash
python app.py
```

or

```bash
flask run
```

---

## 📂 Project Structure

```
snapclass-backend/
│
├── app.py
├── routes/
├── models/
├── services/
│   ├── face_recognition/
│   ├── voice_recognition/
│   └── attendance/
├── database/
├── utils/
├── requirements.txt
└── README.md
```

---

## 🗄️ Database

The backend uses **Supabase PostgreSQL** with a normalized relational schema to manage:

- Students
- Subjects
- Faculty
- Attendance Records
- Biometric Data

---

## 🔌 API Responsibilities

- Student Registration
- Face Enrollment
- Voice Enrollment
- Attendance Verification
- Attendance Logging
- Subject Management
- Attendance Retrieval

---

## 📊 Recognition Workflow

1. Receive biometric data from the frontend.
2. Detect and preprocess the input.
3. Generate biometric embeddings.
4. Compare with stored embeddings.
5. Validate using predefined thresholds.
6. Mark attendance if authentication succeeds.
7. Store attendance in the database.
8. Return the result to the frontend.

---

## 📖 Frontend Repository

This repository contains **only the backend implementation**.

The **Streamlit web application (UI)** is available in the companion frontend repository.

➡️ **Please check the previous/frontend repository for the complete user interface and client-side implementation.**

---

## 👨‍💻 Author

**Anmol Panchal**

If you found this project useful, consider giving it a ⭐ on GitHub.
