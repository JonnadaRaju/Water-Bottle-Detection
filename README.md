# 🍶 Water Bottle Detection using YOLOv8


## 📸 Demo

| Input Image | Prediction Output |
|---|---|
| ![Input](images/images%20(6).jpeg) | ![Output](images/prediction-1.jpeg) |

> Model detected `plastic_bottle` with **0.90 confidence** ✅

---

## 📌 Project Overview

This project builds a **custom YOLOv8 object detection model** trained to detect water bottles and classify them into two categories:

- 🧴 `plastic_bottle`
- 🥤 `steel_bottle`

The model draws **bounding boxes with confidence scores** around detected bottles in any image.

---

## 🎯 Classes

| Class | Description |
|---|---|
| `plastic_bottle` | Transparent or colored plastic water bottles |
| `steel_bottle` | Metal / stainless steel water bottles |

---

## 🛠️ Tech Stack

| Tool | Purpose |
|---|---|
| **Python** | Programming language |
| **YOLOv8 (Ultralytics)** | Object detection model |
| **Google Colab** | Cloud GPU training (Tesla T4) |
| **Roboflow** | Dataset preparation and annotation |
| **OpenCV** | Image processing |
| **PyTorch** | Deep learning framework |

---

## 📊 Dataset

| Detail | Info |
|---|---|
| Source | Roboflow Universe |
| Total Images | 315 |
| Training Set | 250 images |
| Validation Set | 26 images |
| Test Set | 39 images |
| Annotation Format | Bounding Boxes (YOLOv8) |
| Input Size | 512×512 (preprocessed) |

📎 Dataset link: See [`dataset/dataset_link.txt`](dataset\dataset_link.txt)

---

## 🚀 How to Run

### 1. Clone the Repository
```bash
git clone https://github.com/JonnadaRaju/Water-Bottle-Detection.git
cd Water-Bottle-Detection
```

### 2. Run Detection on an Image
```python
from ultralytics import YOLO

model = YOLO("models/best.pt")
model.predict(source="images/input.jpg", save=True)
```

---

## 🏋️ Model Training

Training was performed on **Google Colab** using a **Tesla T4 GPU**.

```python
from ultralytics import YOLO

model = YOLO("yolov8n.pt")

model.train(
    data="data.yaml",
    epochs=50,
    imgsz=640
)
```

| Parameter | Value |
|---|---|
| Model | YOLOv8 Nano (`yolov8n`) |
| Epochs | 50 |
| Image Size | 640×640 |
| GPU | Tesla T4 |

---

## ⚡ Performance

| Stage | Time |
|---|---|
| Preprocess | 2.0 ms |
| Inference | 43.8 ms |
| Postprocess | 1.6 ms |
| **Total** | **~47 ms/image** |

> Capable of near **real-time detection** 🚀

---

## 📁 Repository Structure

```
Water-Bottle-Detection/
│
├── dataset/
│   └── dataset_link.txt        # Link to Roboflow dataset
│
├── models/
│   └── best.pt                 # Trained YOLOv8 model
│
├── notebooks/
│   └── training_notebook.ipynb # Google Colab training notebook
│
├── images/
│   ├── images (6).jpeg               # Sample input image
│   └── prediction-1.jpeg          # Sample prediction output
│
├── README.md                   # Project documentation
```

---

## 🔮 Future Improvements

- [ ] Add more bottle types (glass, aluminium can)
- [ ] Train with larger dataset for better accuracy
- [ ] Deploy as a web application using Streamlit
- [ ] Real-time webcam detection
- [ ] Bottle counting system for inventory management

---

## 🧠 Skills Demonstrated

`Computer Vision` `Object Detection` `YOLOv8` `Deep Learning` `Dataset Annotation` `Model Training` `Model Inference` `Python` `Google Colab` `Roboflow`

---