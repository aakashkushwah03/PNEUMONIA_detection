# Pneumonia Detection

Pneumonia continues to be a serious worldwide health concern, causing considerable morbidity and mortality across all age categories, especially in young children and the elderly. Conventional diagnostic procedures mostly rely on chest radiographs which, although readily available and reasonably priced, require expert interpretation and suffer from inter-observer variability and delays.

In this research, we develop and implement a CNN-based framework designed to differentiate between **Normal** and **Pneumonia** cases using chest X-ray images. The goal is to build an automated, scalable, and reliable system that supports radiologists by serving as a screening tool—speeding up diagnosis, reducing workload, and improving access in resource-limited environments.

---

## 1. Workflow Overview

The entire procedure is divided into several methodical stages:

---

## 1.1 Data Collection

The dataset used in this study consists of publicly available chest X-ray images from **Kaggle’s Chest X-Ray (Pneumonia) dataset**.

### Dataset Categories
- **Normal (Healthy Lungs)**
- **Pneumonia (Infected Lungs)**

### Dataset Split
The dataset is divided into three subsets:
- **Training Set** – Used for model learning  
- **Validation Set** – Used to tune model parameters and prevent overfitting  
- **Testing Set** – Used for final performance evaluation  

Before feeding the data into the CNN model, preprocessing is essential because images vary in brightness, contrast, and resolution.

---

## 1.2 Data Preprocessing

Several preprocessing steps were applied to improve training efficiency and ensure uniformity across images:

### ✔ Image Resizing
All chest X-ray images were resized to **150 × 150 × 3** pixels to maintain a consistent input shape for the CNN.

### ✔ Normalization
Pixel values were scaled to the range **0–1** by dividing each pixel by 255.  
This helps stabilize training and speeds up convergence.

### ✔ Dataset Splitting
The dataset was split as follows:
- **70% Training**
- **15% Validation**
- **15% Testing**

### ✔ Image Augmentation
To improve model generalization, the following augmentations were applied:
- Random rotation  
- Horizontal flipping  
- Brightness adjustment  
- Scaling  

This enables the model to identify pneumonia under different orientations and lighting conditions.

---

## 1.3 Model Training

The CNN model was trained using labeled images from the training set. The primary training parameters include:

- **Loss Function:** Binary Cross-Entropy (ideal for two-class classification)  
- **Optimizer:** Adam (for efficient adaptive learning)  
- **Batch Size & Epochs:** Tuned to minimize loss and maximize accuracy  
- **Regularization:** Dropout layers were used to reduce overfitting and improve generalization  

---

## 1.4 Evaluation Metrics

The model's performance is evaluated using the following metrics:

- **Accuracy:** Percentage of correctly classified images  
- **Precision:** Correctly identified positive cases out of all predicted positives  
- **Recall (Sensitivity):** Ability to detect actual positive cases  
- **F1-Score:** Harmonic mean of precision and recall, providing balanced evaluation  

---
