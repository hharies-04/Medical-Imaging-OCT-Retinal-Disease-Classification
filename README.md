# 🏥 Medical Imaging using OCT Images — Retinal Disease Classification

A deep learning project to classify retinal diseases from OCT (Optical Coherence Tomography) images using a Convolutional Neural Network (CNN).

---

## 📌 Project Overview

Optical Coherence Tomography (OCT) is a non-invasive imaging technique widely used in ophthalmology to diagnose retinal diseases. Early and accurate detection of retinal conditions is critical for preventing vision loss and blindness.

This project builds a CNN-based image classification model that can automatically classify OCT images into four categories:

| Class | Disease |
|---|---|
| **CNV** | Choroidal Neovascularization |
| **DME** | Diabetic Macular Edema |
| **DRUSEN** | Drusen deposits in retina |
| **NORMAL** | Healthy retina |

---

## 📂 Dataset

- **Name:** Kermany OCT Dataset
- **Source:** [Kaggle — Kermany2018](https://www.kaggle.com/datasets/paultimothymooney/kermany2018)
- **Total Images:** ~84,000 OCT images
- **Format:** JPEG grayscale images
- **Split:** Train / Validation / Test

### Dataset Structure
```
dataset/
    train/
        CNV/
        DME/
        DRUSEN/
        NORMAL/
    test/
        CNV/
        DME/
        DRUSEN/
        NORMAL/
```

---

## 🛠️ Technologies Used

- **Language:** Python 3
- **Libraries:**
  - `TensorFlow` / `Keras` — Deep learning framework
  - `NumPy` — Numerical computing
  - `OpenCV` — Image processing
  - `Matplotlib` & `Seaborn` — Visualization
  - `Scikit-learn` — Evaluation metrics

---

## 🤖 CNN Model Architecture

| Layer | Details |
|---|---|
| **Conv Block 1** | Conv2D(32) → BatchNorm → Conv2D(32) → MaxPool → Dropout |
| **Conv Block 2** | Conv2D(64) → BatchNorm → Conv2D(64) → MaxPool → Dropout |
| **Conv Block 3** | Conv2D(128) → BatchNorm → Conv2D(128) → MaxPool → Dropout |
| **Dense Layer 1** | Dense(256) → BatchNorm → Dropout |
| **Dense Layer 2** | Dense(128) → Dropout |
| **Output Layer** | Dense(4) → Softmax |

---

## 🔄 Workflow

1. **Data Loading** — Load OCT images from dataset directory
2. **Data Augmentation** — Rotation, flipping, zoom, shift for training data
3. **Preprocessing** — Resize to 128×128, normalize pixel values
4. **Model Building** — 3-block CNN with batch normalization and dropout
5. **Training** — Train with EarlyStopping, ModelCheckpoint, ReduceLROnPlateau callbacks
6. **Evaluation** — Accuracy, Loss, Classification Report, Confusion Matrix
7. **Prediction** — Predict disease class from a single OCT image

---

## 📊 Results

- The CNN model classifies retinal OCT images into 4 disease categories
- Training uses **data augmentation** to improve generalization
- **EarlyStopping** prevents overfitting
- Model performance evaluated using **confusion matrix** and **classification report**

---

## 🚀 How to Run

1. Clone the repository:
   ```bash
   git clone https://github.com/hharies-04/Medical-Imaging-OCT-Retinal-Disease-Classification.git
   cd Medical-Imaging-OCT-Retinal-Disease-Classification
   ```

2. Install required libraries:
   ```bash
   pip install tensorflow numpy opencv-python matplotlib seaborn scikit-learn
   ```

3. Download the dataset from Kaggle:
   > [https://www.kaggle.com/datasets/paultimothymooney/kermany2018](https://www.kaggle.com/datasets/paultimothymooney/kermany2018)

4. Place dataset in the following structure:
   ```
   dataset/train/  and  dataset/test/
   ```

5. Open and run the notebook:
   ```bash
   jupyter notebook medical_imaging_oct_cnn.ipynb
   ```

---

## 📁 Project Structure

```
Medical-Imaging-OCT-Retinal-Disease-Classification/
│
├── medical_imaging_oct_cnn.ipynb    # Main Jupyter Notebook
├── README.md                        # Project documentation
├── best_oct_model.h5                # Best saved model (after training)
├── oct_retinal_disease_cnn_model.h5 # Final saved model (after training)
└── dataset/                         # Dataset folder
    ├── train/
    └── test/
```

---

## 👨‍💻 Author

**Haries H**
B.E. Computer Science & Engineering
Sathyabama University, Chennai — 2026

**Hariharan N**
B.E. Computer Science & Engineering
Sathyabama University, Chennai — 2026

- 🐙 GitHub: [github.com/hharies-04](https://github.com/hharies-04)
- 💼 LinkedIn: [linkedin.com/in/haries-h-331223373](https://www.linkedin.com/in/haries-h-331223373)
- 📧 Email: hharies135@gmail.com

---

## 📜 License

This project is open-source and available under the [MIT License](LICENSE).

