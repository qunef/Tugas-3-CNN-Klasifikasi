# 🏠 CNN Image Classification — Indonesian Traditional Houses

<img width="2861" height="1344" alt="141" src="https://github.com/user-attachments/assets/1cfbef9f-efd7-4a93-aa98-57dc13b2cf79" />

This project implements a **Convolutional Neural Network (CNN)** to classify images of Indonesian traditional houses, specifically distinguishing between:

- Rumah Gadang (Minangkabau)
- Rumah Joglo (Javanese)

The main objective is to compare different deep learning approaches to determine the most effective method for a small image dataset.

---

## 🎯 Objective

- Classify traditional house images
- Compare 3 CNN approaches
- Measure performance improvement using augmentation and transfer learning

---

## 📂 Dataset

The dataset was manually collected from:

- Google Images  
- Google Street View  
- Pinterest  
- TikTok  
- YouTube screenshots

### Dataset Characteristics

- 2 classes: Gadang vs Joglo
- ~2200 total images
- Balanced class distribution (~50:50)
- Manually labeled
- Dataset health check performed (no corrupt files)

Dataset split:

- 70% Training
- 15% Validation
- 15% Testing

---

## 🧪 Experiment Scenarios

This project compares 3 methods:

### 1️⃣ Baseline CNN

A simple CNN built from scratch without augmentation.

Expected accuracy: **60–70%**

---

### 2️⃣ CNN + Data Augmentation

Uses augmentation techniques:

- Rotation
- Flip
- Zoom
- Shift
- Brightness
- Shear

+ 50% Dropout

Expected accuracy: **75–85%**

---

### 3️⃣ Transfer Learning (MobileNetV2)

Uses a pretrained ImageNet model.

- Base model frozen
- Only classifier layers are trained
- ~130K trainable parameters

Expected accuracy: **85–95%**

---

## 📊 Results

| Method | Accuracy |
|--------|----------|
| Baseline CNN | ~54% |
| CNN + Augmentation | ~92% |
| Transfer Learning | **~99%** |

Conclusion:

> Transfer learning combined with augmentation delivers the best performance with faster training and highest accuracy.

---

## 🧠 Model Architecture

### Baseline CNN

```
Input → Conv → Pool → Conv → Pool → Conv → Pool → Dense → Output
```

### Transfer Learning

```
MobileNetV2 (Frozen)
→ Global Average Pooling
→ Dense + Dropout
→ Softmax
```

---

## 📁 Project Structure

```
project/
├── dataset/
│   ├── train/
│   ├── validation/
│   └── test/
├── models/
├── results/
├── notebook.ipynb
├── requirements.txt
└── README.md
```

---

## 🛠 Tech Stack

- Python
- TensorFlow / Keras
- NumPy
- Matplotlib
- Scikit-learn
- Jupyter Notebook

---

## 📈 Key Learnings

- Simple CNN tends to overfit on small datasets
- Data augmentation improves generalization
- Transfer learning is highly effective for small datasets
- Pretrained models reduce training time significantly

---

## 📜 License

This project was created for academic and educational purposes.
