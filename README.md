# UCI---Human-Activity-Recognition-HAR

# **Human Activity Recognition using Machine Learning and Deep Learning**

## **Project Title**
### Solution for AI/ML for Sustainability at IITGN - Selection Task 1  

## **Overview**
This project is a solution for **Task 1** under the **AI/ML for Sustainability** initiative at **IIT Gandhinagar (IITGN)**. It utilizes the **UCI HAR dataset** to classify various human activities using both traditional **machine learning (ML) models** and **deep learning (DL) approaches**.  

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
| Model                | Accuracy (TSFEL) | Time (TSFEL) | Accuracy (TSFEL + PCA) | Time (TSFEL + PCA) | Accuracy (Predefined) |
|----------------------|-----------------|-------------|------------------------|--------------------|------------------------|
| SVM                 | 95.25%          | 2.72s       | 94.98%                 | 2.27s              | 96.47%                 |
| Random Forest       | 93.45%          | 31.32s        | 91.89%                 | 22.36s               | 92.87%                 |
| Logistic Regression | 95.55%          | 16.01s        | 94.67%                 | 0.39s               | 96.13%                 |

### **2. Deep Learning Model (LSTM + 1D CNN)**
| Feature Set         | Accuracy | Time |
|---------------------|----------|------|
| TSFEL Feature    | 87.24%   | 264.05s |
| PCA Transformed + TSFEL   | 88.16%   | 61.97s |
| Predefined Features| 87.92%   | - |

---

## **Key Observations**
1. **SVM with predefined features achieved the highest accuracy (96.47%)**, making it the best-performing ML model.
2. **Logistic Regression provided competitive results (95.55% with TSFEL, 96.13% with predefined features) while being the most efficient model.**
3. **Random Forest had longer training times and showed slightly lower accuracy than SVM and Logistic Regression.**
4. **PCA transformation reduced accuracy slightly but significantly reduced training time.**
5. **Deep learning models underperformed compared to ML models** and had much higher training times.

---

## **Conclusion**
- **Best Accuracy:** **SVM with predefined features**.
- **Best Speed-Accuracy Tradeoff:** **Logistic Regression with PCA-transformed TSFEL features**.
- **Deep learning is computationally expensive** and did not outperform ML models.
- **PCA helps in reducing computation time but slightly impacts accuracy.**
- **Feature engineering plays a crucial role in model performance**—predefined features outperform TSFEL-generated ones, but **TSFEL remains a strong alternative** when raw sensor data is used.  

---

📌 **Note:** The results may vary depending on **hyperparameter tuning, dataset preprocessing, and computational resources**.
