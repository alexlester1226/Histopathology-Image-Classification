# Histopathology-Image-Classification
A machine learning and deep learning project focused on classifying histopathology cell images from the CRCHistoPhenotypes dataset using classical ML algorithms, Convolutional Neural Networks (CNNs), and ensemble learning techniques.

## Overview

This project develops an end-to-end computational pathology pipeline for automated colon cell classification using 27×27 RGB histopathology image patches. The goal is to assist medical image analysis by identifying:

* **Cancerous vs Non-Cancerous cells** (Binary Classification)
* **Cell Type Classification** among:

  * Fibroblast
  * Inflammatory
  * Epithelial
  * Others

The project combines exploratory data analysis, dimensionality reduction, classical machine learning, deep learning, and advanced ensemble methods to evaluate model performance on unseen patients.

---

## How To Run 


### 1. Download Repo
```bash
# Clone into this repo on local device
git clone https://github.com/alexlester1226/Histopathology-Image-Classification
cd Histopathology-Image-Classification
```
OR

Simply download the repo from web browser

### 2. Environment Setup

```bash
# Create a virtual environment (recommended)
python3 -m venv venv
source venv/bin/activate

# Install dependencies
pip install -r requirements.txt
```

### 3. Run the Notebook

You can run the notebook through Jupyter's interactive interface or from the terminal:

```bash
# Option A: Open in Jupyter Notebook
jupyter notebook notebook.ipynb
# (Kernel -> Restart & Run All)

# Option B: Execute from command line
jupyter nbconvert --to notebook --execute notebook.ipynb --output notebook_executed.ipynb
```

---

## Repository Structure

```bash
├── data/
│   ├── data_labels_mainData.csv
│   ├── data_labels_extraData.csv
│   └── images/             # 20,280 cell images (27×27 RGB PNG)
├── figures/                # Generated figures (created by notebook)
├── notebook.ipynb          # Main Jupyter notebook (code + analysis)
├── notebook.pdf            # PDF of Main Jupyter notebook 
├── models/                 # Saved versions of trained Models 
├── report.pdf              # Detailed academic report
├── requirements.txt        # Python dependencies
└── README.md               # This file
```

---

## Dataset

Dataset used:

* **CRCHistoPhenotypes Dataset**
* Histopathology image patches extracted from colon tissue samples
* 20,280 total images across 98 patients
* Image size: **27×27 RGB**

### Tasks

### Task 1 — Binary Classification

Predict whether a cell is:

* Cancerous
* Non-Cancerous

### Task 2 — Multiclass Classification

Predict the cell type:

* Fibroblast
* Inflammatory
* Epithelial
* Others

---

## Features & Workflow

### Exploratory Data Analysis

* Class distribution analysis
* Patient-level data inspection
* Pixel intensity statistics
* Mean image visualization
* Histopathology image analysis

### Unsupervised Learning

* Principal Component Analysis (PCA)
* t-SNE visualization

### Data Preprocessing

* Patient-wise train/validation/test splitting
* Standardization using `StandardScaler`
* Flattened vector pipeline for classical ML
* Tensor pipeline for CNN models

### Machine Learning Models

* Logistic Regression
* Support Vector Machine (RBF Kernel)
* Random Forest
* Custom CNN Architecture

### Advanced Techniques

* Data augmentation
* Weighted loss functions
* Weighted random sampling
* Ensemble soft voting

---

## CNN Architecture

Custom LeNet-style CNN:

Conv2D(3→32) → BatchNorm → ReLU → MaxPool
Conv2D(32→64) → BatchNorm → ReLU → MaxPool
Conv2D(64→128) → BatchNorm → ReLU → MaxPool
Flatten → Fully Connected → Dropout → Output Layer

---

## Results

| Model                   | Task 1 Macro F1 | Task 2 Macro F1                   |
| ----------------------- | --------------- | --------------------------------- |
| Logistic Regression     | 0.7644          | 0.4875                            |
| SVM (RBF)               | 0.8323          | 0.5396                            |
| Random Forest           | 0.8068          | 0.4861                            |
| CNN + Data Augmentation | 0.8586          | 0.4282                            |
| Ensemble Model          | **0.8628**      | Best overall combined performance |

---

## Technologies Used

* Python
* PyTorch
* scikit-learn
* NumPy
* Pandas
* Matplotlib
* Seaborn
* PIL
* torchvision

---

## Key Learnings

* Importance of patient-wise splitting to prevent data leakage
* Challenges of low-resolution histopathology classification
* Tradeoffs between classical ML and CNN architectures
* Impact of class imbalance on Macro F1-score
* Ensemble learning for performance improvement

---

## Future Improvements

* Transfer learning with pretrained medical imaging models
* Attention-based CNN architectures
* Vision Transformers (ViTs)
* Higher resolution pathology patches
* Explainability using Grad-CAM visualizations

---

## Author

Alexander Lester
Computer Engineering Student — Queen’s University
