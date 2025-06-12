# 🧠 Brain Tumor Classification

This repository contains a deep learning project for classifying brain tumors using custom CNN and transfer learning (VGG16) models.

## 📊 Project Report

The project focuses on the classification of brain tumors into four categories:
- Glioma
- Meningioma
- Pituitary
- No Tumor

### 📁 Dataset
- **Source**: [Kaggle - Brain Tumor MRI Dataset](https://www.kaggle.com/datasets/masoudnickparvar/brain-tumor-mri-dataset)
- **Image Size**: Resized to `150x150x3`
- **Train/Test Split**:

| Tumor Type | Train Samples | Test Samples |
|------------|---------------|--------------|
| Glioma     | 1321          | 300          |
| Meningioma | 1339          | 306          |
| Pituitary  | 1595          | 405          |
| No Tumor   | 1457          | 300          |

---

## 🧪 Custom CNN Model

### 🔧 Architecture
Conv → Pool → Conv → Pool → Conv → Pool → Flatten → Dense → Dropout → Dense (Output)


- **Total Parameters**: 4,829,764

### ⚙️ Training Parameters
- Input Shape: 150x150x3 (RGB)
- Optimizer: Adam
- Loss: Categorical Crossentropy
- Batch Size: 32
- Epochs: 15 (with EarlyStopping, `patience=3`)

### 📈 Performance
- **Accuracy**: ~93%
- **Loss**: Training loss decreased steadily to **~0.18**
- Validation accuracy and loss showed some fluctuations but ultimately converged with training metrics, indicating a good balance between generalization and fit.

---

## 🔁 Transfer Learning with VGG16

### ⚙️ Training Strategy

**Phase 1: Initial Training**
- Optimizer: Adam  
- Loss: Categorical Crossentropy  
- Epochs: 15  
- Batch Size: 32  
- EarlyStopping (patience=3)

**Phase 2: Fine-Tuning**
- Last 4 VGG16 layers unfrozen  
- Learning Rate: `1e-5`  
- Optimizer: Adam  
- Epochs: 4  
- Batch Size: 32  

### 📈 Performance
- **Accuracy**: ~96.7%
- **Loss**: Training loss dropped below **0.05**, validation loss reached **~0.08**
- Fine-tuning helped align the model with high-level features, leading to strong generalization.

---

## 📌 Confusion Matrices & Test Predictions

Confusion matrices and sample prediction results from the test set are included in the full report.

---

## 👥 Authors

- **Betül Gül** - B211202053  
- **Şüheda Almina Dadak** - B211202049

---

## 📄 Full Report

The detailed PDF report includes architectural visualizations, confusion matrices, and test image predictions.  
[📄 View the full report here](PROJECTREPORT.pdf)
