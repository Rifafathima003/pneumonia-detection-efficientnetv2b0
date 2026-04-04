# pneumonia-detection-efficientnetv2b0
Lung-region focused deep learning framework for multi-class pneumonia detection using EfficientNetV2 with confidence-aware decision support

# 🩺 Lung-Region Focused Pneumonia Detection using EfficientNetV2

## 📌 Overview

This project presents a **deep learning framework for multi-class pneumonia detection** from chest X-ray images. The system is designed not only for high accuracy but also for **clinical reliability, interpretability, and decision support**.

The model integrates:

* **U-Net** for lung segmentation
* **EfficientNetV2-B0** for classification
* **Confidence calibration** for reliable predictions
* **Explainability techniques** for transparency

This project was developed as part of a Master's dissertation.

---

## 🎯 Objectives

* Detect and classify:

  * Normal
  * Bacterial Pneumonia
  * Viral Pneumonia
  * COVID-19 Pneumonia
* Focus only on **lung regions** to avoid background noise
* Improve **model trustworthiness** using confidence-based predictions

---

## 🧠 Key Features

* ✅ Lung-region focused learning using U-Net
* ✅ Transfer learning with EfficientNetV2-B0
* ✅ Image enhancement for better feature visibility
* ✅ Confidence calibration (temperature scaling)
* ✅ Explainability using occlusion sensitivity
* ✅ Decision support system based on prediction confidence

---

## ⚙️ System Architecture

```
Chest X-ray Input
        ↓
Preprocessing & Cleaning
        ↓
U-Net Lung Segmentation
        ↓
Lung Mask Application
        ↓
Image Enhancement
        ↓
EfficientNetV2-B0 Classification
        ↓
Probability Output
        ↓
Confidence Calibration
        ↓
Decision Support System
```

---

## 📊 Results

* **Accuracy:** 82%
* **F1 Score:** 0.82
* **Best Performance:** Bacterial Pneumonia
* Strong class separability (ROC-AUC up to 1.00)

### Key Insights:

* Model performs best for bacterial pneumonia
* Viral and COVID cases show overlap (expected clinically)
* Confidence calibration improves prediction reliability

---

## 📂 Project Structure

```
pneumonia-detection-efficientnetv2/
│
├── notebook/
│   └── pneumonia_model.ipynb
│
├── reports/
│   └── pneumonia_report.pdf
│
├── requirements.txt
├── README.md
└── .gitignore
```

---

## 📦 Dataset

This project uses the **COVID-19 Radiography Dataset** from Kaggle:

🔗 https://www.kaggle.com/datasets/tawsifurrahman/covid19-radiography-database

### 📥 How to Download Dataset

1. Install Kaggle API:

```
pip install kaggle
```

2. Download your Kaggle API key:

* Go to: https://www.kaggle.com/account
* Click **"Create New API Token"**
* Place `kaggle.json` in:

```
C:\Users\<your-username>\.kaggle\
```

3. Run the following command:

```
kaggle datasets download -d tawsifurrahman/covid19-radiography-database
```

4. Extract dataset and place it inside:

```
data/
```

### 📁 Expected Dataset Structure

```
data/
├── Normal/
├── COVID/
├── Viral Pneumonia/
└── Lung_Opacity/   (Bacterial Pneumonia)
```

---

## ⚙️ Installation

Clone the repository:

```
git clone https://github.com/your-username/pneumonia-detection-efficientnetv2.git
cd pneumonia-detection-efficientnetv2
```

Install dependencies:

```
pip install -r requirements.txt
```

---

## ▶️ How to Run

```
jupyter notebook
```

Open:

```
notebook/pneumonia_model.ipynb
```

---

## 🧪 Model Details

### 🔹 Preprocessing

* Image resizing (224 × 224)
* Normalization
* Dataset balancing

### 🔹 Segmentation

* U-Net for lung extraction
* Removes irrelevant background noise

### 🔹 Classification

* EfficientNetV2-B0 (Transfer Learning)
* Three-stage training:

  * Feature extraction
  * Partial fine-tuning
  * Full fine-tuning

### 🔹 Loss & Optimization

* Categorical Cross-Entropy
* Adam optimizer

---

## 📈 Evaluation Metrics

* Accuracy
* Precision
* Recall
* F1-score
* Confusion Matrix
* ROC Curve
* Precision-Recall Curve

---

## 🔍 Explainability

* Occlusion Sensitivity Maps
* Feature visualization
* t-SNE clustering

These help ensure the model focuses on **clinically relevant lung regions**.

---

## 📉 Confidence Calibration

Temperature scaling is applied to reduce overconfidence:

* ≥ 0.85 → Accept prediction
* 0.60 – 0.85 → Expert review
* < 0.60 → Further investigation

---

## ⚠️ Limitations

* Confusion between viral and COVID pneumonia
* Sensitive to image quality
* Requires GPU for training
* No clinical metadata used

---

## 🚀 Future Improvements

* Lesion localization
* Attention mechanisms
* Multi-modal data integration
* Model deployment (web app / edge devices)

---

## 📄 Report

Detailed project report available in:

```
reports/pneumonia_report.pdf
```

---

## 👩‍💻 Author

**Rifa Fathima**
MSc Data Science
University of Kerala

---

## ⭐ If you found this useful

Give this repo a ⭐ and share!
