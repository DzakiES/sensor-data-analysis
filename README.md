# 📡 Sensor Data Analysis — Walking & Running Activity Detection

![Python](https://img.shields.io/badge/Python-3.8+-blue?logo=python&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-Data%20Analysis-150458?logo=pandas)
![Scipy](https://img.shields.io/badge/SciPy-Signal%20Processing-8CAAE6?logo=scipy)
![Matplotlib](https://img.shields.io/badge/Matplotlib-Visualization-orange)
![Status](https://img.shields.io/badge/Status-Complete-brightgreen)

---

## 📌 Project Overview

This project analyzes **accelerometer and gyroscope sensor data** collected during two physical activities — **walking** and **running** — using a mobile device. The goal is to process raw sensor signals, apply digital filters, evaluate signal quality, and detect step counts with distance estimation.

This project demonstrates a full signal processing pipeline from **raw data → filtering → analysis → insight**, which is applicable in IoT, health tech, and motion analytics domains.

---

## 🗂️ Project Structure

```
sensor-data-analysis/
│
├── data/
│   ├── (Walking) 2025-11-04 16-11-45.csv        # Accelerometer - Walking
│   ├── (Running) 2025-11-04 16-15-33.csv        # Accelerometer - Running
│   ├── walk_Gyroscope rotation rate (...).xls   # Gyroscope - Walking
│   └── run_Gyroscope rotation rate (...).xls    # Gyroscope - Running
│
├── Tugas_no_1.ipynb   # Signal Visualization
├── tugas_no_2.ipynb   # Digital Filtering (LPF & HPF)
├── tugas_no_3.ipynb   # SNR Analysis
├── tugas_no_4.ipynb   # Step Detection & Distance Estimation
│
└── README.md
```

---

## 🔬 Notebooks Description

### 📓 Notebook 1 — Signal Visualization
- Loads accelerometer and gyroscope data for both walking and running
- Resamples data to target frequencies (50 Hz and 100 Hz)
- Plots raw signals across time for visual comparison between activities

### 📓 Notebook 2 — Digital Filtering
- Applies **Low Pass Filter (LPF)** to accelerometer data
  - Cutoff frequency: **1.2 Hz** (range: 0.8–1.5 Hz)
  - Purpose: Remove high-frequency noise, retain basic movement
- Applies **High Pass Filter (HPF)** to gyroscope data
  - Cutoff frequency: **17.5 Hz** (range: 15–20 Hz)
  - Purpose: Remove low-frequency drift, retain rapid movements
- Compares filtered vs. raw signals at 50 Hz and 100 Hz sampling rates

### 📓 Notebook 3 — SNR Analysis (Signal-to-Noise Ratio)
- Calculates SNR in decibels (dB) for both accelerometer and gyroscope signals
- Formula used:

$$SNR_{dB} = 10 \log_{10}\left(\frac{P_{signal}}{P_{noise}}\right)$$

- Compares SNR across sampling rates (50 Hz vs 100 Hz) for walking and running scenarios
- **Key finding**: 50 Hz provides better SNR for accelerometer (LPF), while 100 Hz performs better for gyroscope (HPF)

### 📓 Notebook 4 — Step Detection & Distance Estimation
- Selects optimal sampling rate based on SNR results from Notebook 3
- Uses **peak detection** (`scipy.signal.find_peaks`) to count steps
- Estimates total distance traveled for a **20-meter walk/run** scenario
- Compares accelerometer-based vs. gyroscope-based step detection

---

## 🛠️ Tech Stack

| Tool | Purpose |
|------|---------|
| **Python 3** | Core programming language |
| **Pandas** | Data loading and manipulation |
| **NumPy** | Numerical computation |
| **SciPy** | Signal filtering & peak detection |
| **Matplotlib** | Data visualization |

---

## 🚀 How to Run

1. **Clone this repository**
```bash
git clone https://github.com/DzakiES/sensor-data-analysis.git
cd sensor-data-analysis
```

2. **Install dependencies**
```bash
pip install pandas numpy scipy matplotlib openpyxl
```

3. **Open notebooks in order**
```bash
jupyter notebook
```
Run notebooks in sequence: `Tugas_no_1` → `tugas_no_2` → `tugas_no_3` → `tugas_no_4`

---

## 📊 Key Results

- ✅ Successfully visualized and compared sensor signals for walking vs. running
- ✅ Applied LPF and HPF filters to reduce noise while preserving meaningful signal
- ✅ Determined optimal sampling rates based on SNR analysis
- ✅ Detected step counts and estimated distance with accelerometer & gyroscope data

---

## 👤 Author

**Dzaki Endraghani Sunarko**  
📧 dzakies2003@gmail.com  
🔗 [LinkedIn](https://www.linkedin.com/in/dzakisunarko/)  
🎓 Informatics — Telkom University, Bandung

---

> *This project was developed as part of academic coursework in Signal Processing and Data Analysis at Telkom University.*
