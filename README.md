# 🎯 API Implementation for Random Forest Model - Fetal Health Prediction

<!-- Introduction section to explain the purpose of the API -->
## 📘 Introduction
To make the fetal health prediction model more accessible and practical, an API has been developed that serves the trained Random Forest model.  
This API enables real-time predictions by allowing external applications, websites, or users to submit fetal data and instantly receive health status predictions.  
By exposing the model through an API, integration into healthcare systems becomes seamless, aiding in timely decision-making and improving prenatal care.

<!-- Overview section to summarize the API tech stack and usage -->
## 🚀 API Overview

- **Framework Used:** Flask (Python Web Framework)  
- **Endpoint:** `/predict`  
- **HTTP Method:** `POST`  
- **Input Format:** `JSON` containing fetal health features  
- **Output Format:** `JSON` containing the predicted class and confidence score  

<!-- Workflow section to explain how the API operates -->
## ⚙️ How It Works

Clients send a `POST` request to the `/predict` endpoint with a JSON payload containing fetal health parameters such as:

- Baseline fetal heart rate
- Accelerations and decelerations
- Uterine contractions
- Variability measures
- Histogram metrics

The API processes this input, applies the trained **Random Forest** model, and returns:

- A **prediction class**: `Normal`, `Suspect`, or `Pathological`
- A **confidence score** representing the model’s certainty

<!-- Example input to help users understand how to use the API -->
## 📥 Sample Request


```json
{
  "baseline_value": 140,
  "accelerations": 2,
  "fetal_movement": 3,
  "uterine_contractions": 0,
  "light_decelerations": 1,
  "severe_decelerations": 0,
  "prolongued_decelerations": 0,
  "abnormal_short_term_variability": 25,
  "mean_value_of_short_term_variability": 8,
  "percentage_of_time_with_abnormal_long_term_variability": 20,
  "mean_value_of_long_term_variability": 10,
  "histogram_width": 50,
  "histogram_min": 100,
  "histogram_max": 160,
  "histogram_number_of_peaks": 4,
  "histogram_number_of_zeroes": 0,
  "histogram_mode": 140,
  "histogram_mean": 140,
  "histogram_median": 140,
  "histogram_variance": 200,
  "histogram_tendency": 0.5
}
