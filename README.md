# 🎤 AI Interview Practice & Feedback Platform

## 📌 Overview

**AI Interview Practice & Feedback Platform** is a conversational AI system designed to help candidates practice interviews in a realistic and interactive manner.

The platform simulates an interviewer, asks domain-specific questions, accepts spoken responses, and provides structured feedback on **communication quality** such as speaking pace, clarity, and grammar.

---

## 🎯 Problem Statement

Many technically strong candidates struggle to clearly express their thoughts during interviews.

This project focuses on **practice, feedback, and improvement**, rather than simple question–answer automation.

---

## 🚀 Key Features

- Interactive interview-style conversation  
- Domain-based interview question flow  
- Speech-to-Text using efficient ASR models  
- Speaking pace analysis with real-time feedback  
- Grammar-aware response refinement  
- Simple web-based UI for easy interaction  
- Modular architecture for future extensions  

---

## 🧠 High-Level Architecture

### 🔁 Pipeline Flow

1. User selects interview domain  
2. User answers questions using voice or text  
3. Audio is converted to text (ASR)  
4. Speaking pace is calculated and evaluated  
5. Response is passed to interview logic  
6. AI generates next question and feedback  

> Training and large-scale fine-tuning components are documented for completeness.  
> The primary focus of this repository is **deployment, interaction flow, and evaluation logic**.

---

## 🔊 Audio-to-Text Processing

The platform uses **Faster-Whisper** for speech-to-text conversion due to its **speed and low memory footprint**.

### 🧮 Speaking Pace Calculation

```python
def calculate_speaking_pace(transcription, chunk_length):
    words = transcription.split()
    return len(words) / chunk_length
```

### 🧠 Pace Feedback Logic

```python
def pace_checker(pace):
    optimal_range = (1, 3)  # words per second

    if optimal_range[0] <= pace <= optimal_range[1]:
        return "Good pace"
    elif pace < optimal_range[0]:
        return "Too slow"
    else:
        return "Too fast"
```

This feedback helps candidates understand whether they are **rushing** or **speaking too slowly** during interviews.

---

## 🤖 Model & Interview Logic

- Conversational logic designed to simulate a real interviewer  
- Questions adapt based on previous responses  
- Grammar-level feedback improves clarity and structure  
- Easily extensible to new domains and interview styles  

> Large Language Model fine-tuning (QLoRA on Mistral-7B) is documented conceptually  
> and is **not required** to run the deployed application locally.

---

## 🏗️ Deployment Architecture

### 🎨 Frontend

- HTML / CSS based UI  
- Domain selection page  
- Interview interaction screen  

### ⚙️ Backend

- Flask-based server  
- Handles audio input, transcription, pacing logic, and interview flow  
- Modular design to allow model upgrades without UI changes  

---

## 🛠️ Installation & Local Setup

### 1️⃣ Clone the Repository

```bash
git clone https://github.com/AdityAiiitl03/ai-interview-practice-platform.git
cd ai-interview-practice-platform
```

### 2️⃣ Install Dependencies

```bash
pip install -r requirements.txt
```

### 3️⃣ Run the Application

```bash
python app.py
```

The application starts a local server and can be accessed via the browser.

---

## ✅ What This Project Demonstrates

- Practical use of AI for interview preparation  
- Speech analysis applied to real human behavior  
- End-to-end system thinking (UI → Backend → Evaluation)  
- Focus on usability and real-world constraints  

This project prioritizes **explainability and practical value** over experimental complexity.

---

## ⚠️ Limitations & Scope

- Large-scale model training requires cloud GPUs and is not included in local execution  
- Demo focuses on interaction flow and feedback rather than model benchmarking  
- Designed as a learning and practice tool, not a hiring decision system  

---

## 🔮 Future Improvements

- More detailed semantic feedback on answers  
- Resume-aware interview questioning  
- Performance tracking over multiple sessions  
- Expanded domain coverage  

---

## 👨‍💻 Author

**Aditya Singh**  
GitHub: [AdityAiiitl03](https://github.com/AdityAiiitl03)

---

## 📄 License

This project is released under the **MIT License**.
