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

## 👤 **My Contribution (Applicant Section)**

My contributions to this project include:

### 🔹 **1. ETL & Data Engineering**
- Designing and building an **n8n** pipeline to fetch BMKG data every hour.
- Cleaning data, fixing anomalies, preparing the final dataset.

### 🔹 **2. Machine Learning (End-to-End Notebook)**
I created a complete notebook starting from:

- **Business Understanding**  
- **Data Understanding (EDA, analisis cuaca Manado)**  
- **Data Preparation (handling missing, feature engineering, time features)**  
- **Modeling (XGBRegressor & XGBClassifier multi-step)**  
- **Hyperparameter Tuning**  
- **Evaluasi**  
- **Export model untuk deployment**

### 🔹 **3. Deployment & UI Improvement**
- Helping to tidy up the Streamlit display.  
- Added dark mode & UX improvements. 
- Creating a recommended action notification feature.  

---

## 🔧 Instalasi & Menjalankan Proyek

```bash
git clone https://github.com/natalio123/Peramalan-Cuaca-Project.git
cd Peramalan-Cuaca-Project

pip install -r requirements.txt
streamlit run app.py

```
---

## 📂 Folder Structure <br>
📦 ML_PROJECT <br>
 ┣ 📂 app/ <br>
 ┣ 📂 assets/ <br>
 ┣ 📂 dataset/ <br>
 ┣ 📂 source/ <br>
 ┣ 📂src
 ┣ README.md
 ┗ requirements.txt

## 📜 Academic Disclaimer

Training Data Source: The model was trained using historical weather data from the Open-Meteo Historical Weather API with coordinates Latitude: 1.48218 and Longitude: 124.84892 (Manado City area). The historical data range is taken from November 13, 2020 to December 7, 2025. The system receives real-time input from the campus location (Bahu), ensuring it remains relevant to the microclimate.

Kampus Microclimate: </b> Although the data source comes from the general coordinates of the city of Manado, the system is designed to receive input on actual weather conditions from the UNSRAT campus environment during inference, so that the prediction results remain relevant to the local microclimate of the campus.

Limitations of the n8n System: Real-time weather data retrieval is performed using n8n Cloud Free Tier, which has a 14-day usage limit and a daily execution limit. These limitations may affect the continuity of data pipeline automation once the trial period has expired.

## 📬 Contact
If you would like to discuss or hire me, please contact me:
nataliotumuahi@gmail.com

</body>
</html>
