# 🦠 Malaria Cell Classification  
Deep Learning | Transfer Learning | ResNet50 | Medical AI

This project builds an AI-powered system for **automated malaria detection** by classifying microscopic blood smear images as **Parasitized (Infected)** or **Uninfected**.  
The model uses **Transfer Learning with ResNet50**, achieving high accuracy and offering a reliable, fast, and scalable alternative to manual diagnosis.

The project was developed and trained entirely in **Google Colab**.

---

## 📌 Problem Statement

Malaria continues to pose a major global health threat, especially in tropical and subtropical regions.  
Traditional detection requires expert examination of blood smear images, which is:

- Time-consuming  
- Labor-intensive  
- Error-prone  

This project aims to automate malaria detection using **deep learning**, improving speed, consistency, and accessibility of early diagnosis.  

---

## 📂 Dataset

**Source:** NIH Malaria Cell Images Dataset  
**Total Images:** 38,000+  
**Classes:**  
- **Parasitized (Infected)**  
- **Uninfected**

**Train/Validation/Test Split:**

- 70% Training  
- 15% Validation  
- 15% Testing  

All images were:

- Resized  
- Normalized  
- Augmented using rotation, zoom, flipping, shifting  

Dataset link:  
https://lhncbc.nlm.nih.gov/LHC-downloads/malaria-dataset

⚠️ *Dataset is NOT included in this repository due to size and licensing.*

---

## 🧠 Model Architecture

This project uses **ResNet50** (pretrained on ImageNet) as a feature extractor.

### ✔ Model Pipeline:
- **Base Model:** ResNet50 (`include_top=False`)
- **Custom Classification Head:**
  - GlobalAveragePooling2D  
  - Dense(128, activation='relu')  
  - Dropout(0.3)  
  - Dense(1, activation='sigmoid')

### ✔ Training Details:
- **Optimizer:** Adam  
- **Loss Function:** Binary Crossentropy  
- **Metrics:** Accuracy  
- **Regularization:** Early Stopping, Model Checkpoints  

---

## 📊 Results

The model achieved strong performance:

| Metric | Score |
|--------|--------|
| **Training Accuracy** | ~98% |
| **Validation Accuracy** | ~96% |
| **Test Accuracy** | ~95% |

Loss and accuracy curves show stable learning with minimal overfitting.
Single-image predictions correctly classify infected vs uninfected cells.  

---

## 🧪 Sample Output
- Confusion matrix 
- Accuracy & loss graphs  
- Correct predictions on random sample images 

---

## 📁 Repository Structure

Malaria/
│── Malaria_Cell_Classification.ipynb 
│── README.md
│── requirements.txt 
│── .gitignore 
│── sample_images (few demo images)

---

## 🛠 Installation & Setup

Install dependencies:

```bash
pip install -r requirements.txt

---

## ▶️ Running the Notebook

1. Open **Malaria_Cell_Classification.ipynb** in VS Code (Jupyter) or Google Colab.
2. Set the correct dataset path in the notebook.

```python
# For Google Colab:
from google.colab import drive
drive.mount('/content/drive')
dataset_path = "/content/drive/MyDrive/Malaria_dataset"

# For local VS Code:
dataset_path = "path/to/Malaria_dataset"

3.Run all cells to load data, train the model, and test predictions.

---

## 🏁 Conclusion
This project shows how transfer learning with ResNet50 can accurately classify malaria-infected cells with over 95% accuracy. While not a replacement for medical experts, it can support faster and more reliable early detection.

---

## 🙌 Acknowledgements

Dataset by National Institutes of Health (NIH)

Transfer learning using ResNet50 

Execution environment: Google Colab GPU

---

## 📬 Author

Medha Ramanathan
GitHub: Medha-tech

---
