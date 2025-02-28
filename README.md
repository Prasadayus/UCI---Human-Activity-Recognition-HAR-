# UCI---Human-Activity-Recognition-HAR

# **Human Activity Recognition using Machine Learning and Deep Learning**

## **Overview**
This project utilizes the UCI HAR dataset to classify various human activities using both traditional machine learning (ML) models and deep learning (DL) approaches. The study includes:

- **ML models (Random Forest, SVM, Logistic Regression)** trained on features generated using the **TSFEL library**.
- **Deep learning models (LSTM + 1D CNN)** trained directly on raw sensor data (accelerometer readings).
- **Comparative analysis** between models trained on TSFEL-generated features, PCA-transformed features, and predefined features provided by the dataset authors.

## **Dataset**
- The [UCI HAR Dataset](https://archive.ics.uci.edu/ml/datasets/human+activity+recognition+using+smartphones) consists of accelerometer and gyroscope readings from smartphones to classify activities such as walking, sitting, and lying down.
- The dataset includes both raw inertial sensor data and pre-extracted features.

## **Feature Extraction Approaches**
- **TSFEL Feature Extraction**: Extracted statistical and frequency-based features from raw sensor data.
- **TSFEL + PCA**: Applied **Principal Component Analysis (PCA)** to reduce dimensionality.
- **Predefined Features**: Used features provided by the dataset authors.

## What is TSFEL?  
**TSFEL (Time Series Feature Extraction Library)** automates feature extraction from time-series data, including:  
- **Statistical Features** (mean, variance, skewness)  
- **Temporal Features** (autocorrelation, entropy)  
- **Frequency Features** (FFT coefficients, spectral entropy)  

This helps traditional ML models learn meaningful patterns from raw sensor data.  


## **Models & Performance Comparison**

### **1. Machine Learning Models**
| Model                | Accuracy (TSFEL) | Accuracy (TSFEL + PCA) | Accuracy (Predefined) |
|----------------------|-----------------|------------------------|------------------------|
| SVM                 | 92.34%          | 90.12%                 | 94.78%                 |
| Random Forest       | 88.75%          | 86.42%                 | 91.56%                 |
| Logistic Regression | 85.23%          | 83.79%                 | 89.34%                 |

### **2. Deep Learning Model (LSTM + 1D CNN)**
| Feature Set         | Accuracy |
|---------------------|----------|
| Raw Sensor Data    | 94.12%   |
| PCA Transformed    | 91.85%   |
| Predefined Features| 96.78%   |

## **Key Observations**
- **SVM with predefined features** performed the best among ML models.
- **LSTM + CNN outperformed traditional ML models**, especially when trained on predefined features.
- **TSFEL-generated features provided strong results**, but PCA slightly reduced accuracy.
- **Predefined features consistently yielded the best performance** across both ML and DL approaches.

## **Conclusion**
- **If using ML models**, **SVM with predefined features** is the best choice.
- **If using deep learning**, **LSTM + CNN trained on predefined features** achieves the highest accuracy.
- **Feature engineering plays a crucial role in performance**—predefined features outperform TSFEL-generated ones, but TSFEL is still a strong alternative when raw sensor data is available.


---
📌 **Note:** The results may vary depending on hyperparameter tuning and dataset preprocessing.
