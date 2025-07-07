# 📄 Document Classification Using Deep Learning

This project focuses on building a deep learning-based system to classify scanned document images into three categories: **ID Card**, **Passport**, and **Driving License**. The goal is to automate document type detection, which is a critical step in many real-world applications such as KYC (Know Your Customer), onboarding systems, and digital document verification.

---

## 📖 Theoretical Overview

### Problem Statement

Document verification is a fundamental process in industries like banking, travel, and government services. Manual verification is time-consuming and error-prone. This project aims to design an automated classifier that can quickly and accurately determine the type of a scanned document image.

The classification task involves predicting whether a given document image belongs to one of the following classes:
-  **ID Card**
-  **Passport**
-  **Driving License**

---

### Proposed Approach

The project uses a **Convolutional Neural Network (CNN)** architecture with **transfer learning** for image classification.

#### 🔹 Why Transfer Learning?
Instead of training a CNN from scratch (which requires large datasets), we use a **pre-trained model** (MobileNetV2) as the base. MobileNetV2 is lightweight and performs well on image classification tasks, making it suitable for this application.

#### 📦 Steps:
1. **Dataset Preparation**  
   - Images are organized into three classes.
   - Data augmentation techniques (rotation, flipping, zooming) are applied to improve generalization.
2. **Feature Extraction**  
   - Use MobileNetV2 pretrained on ImageNet to extract deep features from document images.
3. **Fine-Tuning**  
   - Fine-tune the top layers of MobileNetV2 to adapt it to the specific task of document classification.
4. **Classification**  
   - Add a fully connected layer with softmax activation to classify into three categories.

---

###  Why This is Important

This project simulates a real-world scenario where document images may vary in:
- Layout and design (different countries issue different formats)
- Resolution and quality (blurred or scanned images)
- Background noise (cropped or with surrounding objects)

By addressing these challenges, the model demonstrates the capability of deep learning for practical document processing tasks.

---

## 📦 Technologies Used

- **Python**
- **TensorFlow / Keras**
- **OpenCV**
- **Matplotlib**
- **MobileNetV2 (Pre-trained CNN)**

---

## 📈 Results

The model was trained for 20 epochs on the document classification dataset containing **ID Cards**, **Passports**, and **Driving Licenses**. Below are the key performance metrics:  

| Metric             | Value        |
|---------------------|--------------|
|  Training Accuracy | **97.77%** (highest at Epoch 18) |
|  Validation Accuracy | **90.91%** (highest at Epoch 18) |
|  Training Loss     | **0.2357** (lowest at Epoch 18)    |
|  Validation Loss   | **0.3683** (lowest at Epoch 18)    |

---

### 📌 Observations

- The model achieved **high training accuracy (~98%)** indicating good learning of the dataset features.
- **Validation accuracy peaked at 90.91%**, showing strong generalization.
- Slight fluctuations in validation accuracy and loss suggest:
  - Possible dataset imbalance (especially in Driving License class).
  - Some overfitting after Epoch 18.

---

### 📊 Training Progress

| Epoch | Training Accuracy | Validation Accuracy | Training Loss | Validation Loss |
|-------|--------------------|----------------------|---------------|-----------------|
| 10    | 86.64%            | 86.36%               | 0.4198        | 0.4660          |
| 15    | 92.80%            | 86.36%               | 0.2999        | 0.3784          |
| 18    | **97.77%**        | **90.91%**           | **0.2357**    | **0.3683**      |
| 20    | 90.05%            | 81.82%               | 0.2954        | 0.4001          |

---

###  Class-wise Performance (Approximate)

| Class             | Accuracy (%) |
|--------------------|--------------|
|  ID Card         | 94%          |
|  Passport        | 91%          |
|  Driving License | 70%          |

---

### 🔥 Next Steps

- Augment dataset for underperforming classes.
- Apply regularization or dropout to reduce slight overfitting.
- Integrate OCR features for improved accuracy on text-rich documents.

---

## 🚀 Future Enhancements

- 📄 **Integrate OCR** to combine text features with visual features for hybrid classification.
- 📈 **Expand Dataset** with more high-quality images, especially for under-represented classes.
- 🌐 **Deploy as API** using FastAPI or Flask for integration into web or mobile apps.
- 📱 Build a user-friendly interface using Streamlit.

---

## Screenshots

![Screenshot 2025-07-04 at 1 37 09 PM](https://github.com/user-attachments/assets/443e7d70-e265-4952-b880-15b98a930c16)

![Screenshot 2025-07-04 at 1 33 59 PM](https://github.com/user-attachments/assets/f5b24584-e5a6-43ca-b601-156b0bae0bba)

![Screenshot 2025-07-04 at 1 25 34 PM](https://github.com/user-attachments/assets/ed5be775-37b4-427c-acbd-a503198ce9fb)

---

## 📌 Summary

The document classifier is able to accurately identify document types with **up to 91% validation accuracy**. With further dataset improvements and model tuning, the system can achieve production-level performance.

---
