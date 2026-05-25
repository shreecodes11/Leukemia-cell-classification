# Leukemia Cell Classification using Deep Learning (ResNet50 + Grad-CAM)

## Overview

This project presents a deep learning-based system for classifying blood cell images into:

- **ALL (Acute Lymphoblastic Leukemia)**
- **HEM (Healthy cells)**

The model is built using **transfer learning (ResNet50)** and enhanced with **Grad-CAM** for explainability, making it suitable for medical image interpretation tasks.

---

## Objective

- Develop a binary classifier for leukemia detection
- Apply transfer learning for improved performance on medical images
- Use Grad-CAM to visualize model decision regions
- Build an end-to-end medical AI pipeline

---

## Dataset

- Source: Kaggle (C-NMC Leukemia Dataset)
- Classes:
  - ALL (Leukemia cells)
  - HEM (Healthy cells)

### Dataset Distribution:
- ALL: 2397 images  
- HEM: 1130 images  

---

## Model Architecture

- Base Model: **ResNet50 (ImageNet pretrained)**
- Approach: Transfer Learning (Frozen backbone + custom head)

### Custom Head:
- Global Average Pooling
- Dense layer (256 neurons, ReLU)
- Dropout (0.6)
- Output layer (1 neuron, Sigmoid)

---

## Training Setup

- Image size: 224 × 224
- Batch size: 32
- Optimizer: Adam
- Loss function: Binary Crossentropy
- Data augmentation:
  - Rotation
  - Zoom
  - Shift
  - Shear
  - Horizontal flip
- Train/Validation split: 80/20

---

## Model Performance

### Training Results (3 Epochs):

- Training Accuracy: **80.05%**
- Validation Accuracy: **71.91%**

### Observation:
The model shows steady learning across epochs with a small gap between training and validation accuracy, indicating mild overfitting but acceptable generalization for a baseline medical AI model.

---

## Training Curves

The model’s accuracy and loss were monitored across epochs to evaluate learning behavior.

---

## Explainability (Grad-CAM)

Grad-CAM is used to visualize which regions of the image influence the model's predictions.

### Example Output:
![Grad-CAM Output](gradcam_outputs/sample_gradcam.png)

---

## How to Run

### 1. Clone Repository
```bash
git clone https://github.com/your-username/leukemia-classification.git
cd leukemia-classification
