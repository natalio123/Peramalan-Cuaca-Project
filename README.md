<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    
</head>
<body>

<header>
   <h1 align="center">🌤️ UNSRAT Climate AI</h1>
<p align="center"><b>Hyper-local Campus Weather Forecasting System</b></p>
<p align="center">End-to-End Machine Learning Project | ETL – Modeling – Deployment</p>

<p align="center">
  <img src="https://img.shields.io/badge/Python-3.10-blue?style=flat-square&logo=python"/>
  <img src="https://img.shields.io/badge/Streamlit-App-ff4b4b?style=flat-square&logo=streamlit"/>
  <img src="https://img.shields.io/badge/Model-XGBoost-orange?style=flat-square"/>
  <img src="https://img.shields.io/badge/Pipeline-n8n-FF6B6B?style=flat-square"/>
</p>

---

## 🧩 Project Summary

UNSRAT Climate AI is a Machine Learning based **micro-campus weather forecasting** system for the UNSRAT Bahu campus area.   

This project is designed to:
- Predict temperature and rainfall up to **6 hours in advance**,  
- Monitor conditions in **real-time**,  
- Provide **action recommendations** that are easy for users to understand.

---

## 🏗 System Architecture

The system consists of three main components:

1. **Automated ETL Pipeline (n8n)**  
   Retrieve real-time data from the BMKG API every hour and save it to Google Sheets

2. **Machine Learning Engine (Python – Jupyter – XGBoost)**  
   Used for preprocessing, EDA, feature engineering, training, and evaluation.

3. **Deployment Layer (Streamlit App)**  
   Providing predictions and recommendations for action to users.

### 📌 *Architecture Workflow Diagram (ETL n8n)*  
<img src="assets/gambar/Etl.png" width="800"/>

### 📌 *Streamlit UI Image*  
<img src="assets/gambar/UI Streamlit.png" width="800"/>

---

## 🧠 Technical Methodology

### 1. **Forecasting Approach**
- Used **Direct Multi-Step Model**
- Separate models T+1, T+3, T+6 jam
- Low and stable error even as the time horizon increases.

### 2. **Hybrid Strategy (Regressor + Classification)**
- Temperature → `XGBRegressor`
- Rain → `XGBClassifier` with custom threshold (>5mm)

### 3. **Evaluation**
Evaluation data using hold out January 2025 - Present.

| Horizon | MAE Suhu (°C) | Rainfall Accuracy | Status |
|--------|---------------|---------------|--------|
| T+1    | 0.36          | 83%           | ✔ Very Precision |
| T+3    | 0.59          | 74%           | ✔ Reliable |
| T+6    | 0.71          | 72%           | ✔ Enough |

---

## 🧪 Main Feature

- 🔁 **ETL otomatis** via n8n  
- 📊 **Prediksi cuaca** (suhu & hujan)  
- 📱 **Dashboard interaktif Streamlit**  
- 🎯 **Rekomendasi aksi otomatis**  
- 🌙 **Mode gelap**

---

## 👤 **Kontribusi Saya (Applicant Section)**

Kontribusi saya pada proyek ini meliputi:

### 🔹 **1. ETL & Data Engineering**
- Mendesain dan membangun pipeline **n8n** untuk fetching data BMKG setiap jam  
- Membersihkan data, memperbaiki anomali, menyiapkan dataset final

### 🔹 **2. Machine Learning (End-to-End Notebook)**
Saya membuat notebook lengkap mulai dari:

- **Business Understanding**  
- **Data Understanding (EDA, analisis cuaca Manado)**  
- **Data Preparation (handling missing, feature engineering, time features)**  
- **Modeling (XGBRegressor & XGBClassifier multi-step)**  
- **Hyperparameter Tuning**  
- **Evaluasi**  
- **Export model untuk deployment**

### 🔹 **3. Deployment & UI Improvement**
- Membantu merapikan tampilan Streamlit  
- Menambah mode gelap & UX improvements  
- Membuat fitur notifikasi rekomendasi tindakan  

---

## 🔧 Instalasi & Menjalankan Proyek

```bash
git clone https://github.com/natalio123/Peramalan-Cuaca-Project.git
cd Peramalan-Cuaca-Project

pip install -r requirements.txt
streamlit run app.py

```
---

## 📂 Struktur Folder <br>
📦 ML_PROJECT <br>
 ┣ 📂 app/ <br>
 ┣ 📂 assets/ <br>
 ┣ 📂 dataset/ <br>
 ┣ 📂 source/ <br>
 ┣ 📂src
 ┣ README.md
 ┗ requirements.txt

## 📜 Disclaimer Akademis

Sumber Data Latih:  Model dilatih menggunakan data historis cuaca dari Open-Meteo Historical Weather API dengan koordinat Latitude: 1.48218 dan Longitude: 124.84892 (wilayah Kota Manado). 
Rentang data historis diambil mulai 13 November 2020 sampai 7 Desember 2025.
Sistem menerima input real-time dari kampus lokasi (Bahu), sehingga tetap relevan untuk mikroklimat

Mikro-klimat Kampus:</b> Meskipun sumber data berasal dari koordinat kota Manado secara umum, sistem dirancang untuk menerima input kondisi cuaca aktual dari lingkungan Kampus UNSRAT saat inference, sehingga hasil prediksi tetap relevan dengan mikro-klimat lokal kampus.

Keterbatasan Sistem n8n: Pengambilan data cuaca real-time dilakukan menggunakan n8n Cloud Free Tier
yang memiliki batas pemakaian selama 14 hari dan batas jumlah eksekusi harian. 
Keterbatasan ini dapat memengaruhi kontinuitas otomatisasi pipeline data apabila masa percobaan telah habis.

## 📬 Kontak
Jika ingin berdiskusi atau merekrut saya, hubungi:
nataliotumuahi@gmail.com

</body>
</html>
