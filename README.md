# EEG Signal Analysis for SSVEP-Based Brain-Computer Interfaces (BCI)

This repository contains a practical analysis of EEG signals collected from users exposed to visual stimuli for Steady-State Visually Evoked Potential (SSVEP)-based Brain-Computer Interfaces (BCIs). The project was developed for the course **IA006 - Introduction to Brain-Computer Interfaces** at Unicamp, using a benchmark dataset and signal processing techniques in Python.

---

## 🎯 Objectives

- Explore a public benchmark EEG dataset for SSVEP-based BCI systems.
- Analyze EEG signals in both time and frequency domains.
- Investigate signal characteristics across users, sessions, frequencies, and electrodes.
- Identify visual stimulus focus through spectral analysis.
- Evaluate BCI signal quality using tools like DFT, PSD, and spectrograms.

---

## 🧠 Scenario: SSVEP and Brain Synchronization

When a person focuses on a flickering visual stimulus, the brain tends to synchronize with the stimulus frequency—especially in the occipital region, where visual processing occurs. This synchronization leads to increased EEG energy at the stimulus frequency and its harmonics. This property is exploited in SSVEP-based BCI systems.

---

## 📂 Dataset Overview

- **Name**: Benchmark Dataset for SSVEP-Based BCI  
- **Source**: Tsinghua University  
- **Access**: [https://bci.med.tsinghua.edu.cn/download.html](https://bci.med.tsinghua.edu.cn/download.html)  
- **Format**: `.mat` files (per subject)  
- **Channels**: 64 electrodes, 10-10 international system  
- **Users**: S01–S35  
  - S01–S08: Experienced with BCI  
  - S09–S35: Inexperienced  
- **Electrode Locations**: Defined in `64-channels.loc`

---

## 🔬 Analysis Activities

### ✅ (a) Dataset Description

- Described the structure, number of users, and sessions.
- Confirmed the organization of the `.mat` files and electrode positioning.

### ✅ (b) Signal Analysis – One User, One Frequency

Using one subject, one session, and one stimulation frequency, signals from 3 electrodes were analyzed:
- **Pz**, **Oz**, and **PO4** (Oz is in the occipital region).

Generated visualizations for each electrode:
- ✅ Time-domain plots
- ✅ Fourier Transform (DFT)
- ✅ Power Spectral Density (PSD) via Welch’s method
- ✅ Spectrogram

📌 **Findings**:
- Clear peaks near the stimulation frequency and its harmonics were observed, especially in **Oz**.
- Evoked potentials were more pronounced in occipital electrodes.

### ✅ (c) Frequency Comparison for One Electrode

- Same subject and session.
- Focused on **Oz** electrode across different stimulus frequencies.

📌 **Findings**:
- Spectral peaks shifted according to the stimulus frequency.
- Strong SSVEP responses aligned with stimulation frequency and harmonics.

### ✅ (d) Session Variability

- Compared two different sessions for **subject**, **Oz** electrode, and the same stimulus.

📌 **Findings**:
- Response shape and intensity slightly varied between sessions.
- SSVEP peaks remained identifiable, indicating consistent evoked response.

### ✅ (e) User Comparison

- Compared EEG from:
  - **S07** (experienced)
  - **S21** (inexperienced)
- Same frequency, electrode: **Oz**

---

## ⚙️ Tools & Libraries

- Python 3.x
- Google Colab
- `scipy.io` – Load `.mat` files  
- `scipy.signal` – Filtering, DFT, PSD (Welch), spectrogram  
- `numpy` – Numerical computations  
- `matplotlib.pyplot` – Visualizations

---

## 🧹 Preprocessing

- Applied **high-pass filter (cutoff = 3 Hz)** to remove low-frequency artifacts.
- Focused on frequencies **above 3 Hz**, as recommended.
- Data filtered and visualized for better frequency clarity.

---

## 🧾 References

- Wang, Y., Chen, X., Gao, X., & Gao, S. (2017).  
  *A Benchmark Dataset for SSVEP-Based Brain–Computer Interfaces*.  
  IEEE Trans. on Neural Systems and Rehabilitation Engineering, 25(10), 1746–1752.

- Wolpaw, J. R., Birbaumer, N., McFarland, D. J., Pfurtscheller, G., & Vaughan, T. M. (2002).  
  *Brain-computer interfaces for communication and control*.  
  Clinical Neurophysiology, 113(6), 767–791.

---

## 👨‍🏫 Course Info

- **Course**: IA006 – Introduction to Brain-Computer Interfaces  
- **University**: Universidade Estadual de Campinas (UNICAMP)  
- **Instructors**:
  - Prof. Denis G. Fantinato – `denisf@unicamp.br`
  - Prof. Levy Boccato – `lboccato@unicamp.br`
  - Prof. Rafael Ferrari – `rafaelf@unicamp.br`
  - Prof. Romis Attux – `attux@unicamp.br`

---
