# 🍶 Water Bottle Detection using YOLOv8

<div align="center">

![Python](https://img.shields.io/badge/Python-3.8+-3776AB?style=for-the-badge&logo=python&logoColor=white)
![YOLOv8](https://img.shields.io/badge/YOLOv8-Ultralytics-FF6B6B?style=for-the-badge)
![PyTorch](https://img.shields.io/badge/PyTorch-EE4C2C?style=for-the-badge&logo=pytorch&logoColor=white)
![Colab](https://img.shields.io/badge/Google_Colab-F9AB00?style=for-the-badge&logo=googlecolab&logoColor=white)
![Roboflow](https://img.shields.io/badge/Roboflow-6706CE?style=for-the-badge)

**A custom YOLOv8 object detection model trained to detect
and classify water bottles in real-time**

[Demo](#-demo) • [Dataset](#-dataset) •
[Training](#-training) • [Results](#-results) •
[Quick Start](#-quick-start)

</div>

---

## 📌 Overview

This project builds a **custom YOLOv8 object detection model**
trained to detect water bottles and classify them into
two categories:

| Class | Icon | Description |
|-------|------|-------------|
| `plastic_bottle` | 🧴 | Transparent or colored plastic water bottles |
| `steel_bottle` | 🥤 | Metal or stainless steel water bottles |

The model draws **bounding boxes with confidence scores**
around detected bottles in any image or video feed.

---

## 📸 Demo

### After Detection

<div align="center">

![Output](images/output.png) 

> ✅ Model detected `plastic_bottle` and `steel_bottle`
> with **0.89 confidence**

</div>

---

## 🛠️ Tech Stack

| Tool | Purpose |
|------|---------|
| **Python 3.8+** | Programming language |
| **YOLOv8 (Ultralytics)** | Object detection model |
| **Google Colab** | Cloud GPU training (Tesla T4) |
| **Roboflow** | Dataset preparation and annotation |
| **OpenCV** | Image processing |
| **PyTorch** | Deep learning framework |
| **Matplotlib** | Visualization and charts |

---

<!-- ## 📊 Dataset

<div align="center">
<img src="images/dataset/sample_annotated.jpg"
     width="700"
     alt="Sample Annotated Dataset"/>

*Sample images with ground truth bounding box annotations*
</div> -->

| Detail | Info |
|--------|------|
| **Source** | Roboflow Universe |
| **Total Images** | 315 |
| **Training Set** | 250 images (79%) |
| **Validation Set** | 26 images (8%) |
| **Test Set** | 39 images (13%) |
| **Annotation Format** | Bounding Boxes (YOLOv8) |
| **Input Size** | 512×512 (preprocessed) |
| **Classes** | 2 (plastic_bottle, steel_bottle) |

📎 Dataset:
[View on Roboflow](dataset/dataset_link.txt)

---

## 🏋️ Training

Training was performed on **Google Colab**
using a **Tesla T4 GPU**.

### Configuration
```python
from ultralytics import YOLO

model = YOLO("yolov8n.pt")

model.train(
    data="data.yaml",
    epochs=50,
    imgsz=640
)
```

### Parameters

| Parameter | Value |
|-----------|-------|
| **Model** | YOLOv8 Nano (yolov8n) |
| **Epochs** | 53 |
| **Image Size** | 640×640 |
| **GPU** | Tesla T4 (Google Colab) |
| **Framework** | Ultralytics |

---

## 📈 Results

### Performance Metrics

<div align="center">

| Metric | Best Score | Meaning |
|--------|-----------|---------|
| 🎯 **mAP@50** | **0.806** | 80.6% main accuracy |
| 🎯 **mAP@50-95** | **0.618** | 61.8% strict accuracy |
| ✅ **Precision** | **0.913** | 91.3% detections correct |
| 🔍 **Recall** | **0.804** | 80.4% bottles found |
| ⏱️ **Inference** | **43.8ms** | Near real-time speed |

</div>

### 📊 Training Charts

<div align="center">
<img src="images/overall.png"
     width="900"
     alt="Training Charts — mAP, Precision, Recall,
          Box Loss, Class Loss"/>

*Training metrics over 53 epochs*
</div>

### What the Charts Show

| Chart | Result | Status |
|-------|--------|--------|
| mAP@50 | Jumped 0.25 → 0.80 in first 10 epochs | ✅ |
| mAP@50-95 | Steadily improved 0.10 → 0.62 | ✅ |
| Precision | Reached peak 0.913 | ✅ |
| Recall | Stabilized at 0.80 | ✅ |
| Box Loss | Consistently decreasing | ✅ |
| Class Loss | Consistently decreasing | ✅ |

> ✅ Both losses going **DOWN** confirms the model
> learned successfully without overfitting


### Inference Speed

| Stage | Time |
|-------|------|
| Preprocess | 2.0 ms |
| Inference | 43.8 ms |
| Postprocess | 1.6 ms |
| **Total** | **~47 ms/image** |

> ⚡ Capable of near **real-time detection**

---

## 🚀 Quick Start

### 1. Clone Repository
```bash
git clone https://github.com/JonnadaRaju/Water-Bottle-Detection.git
cd Water-Bottle-Detection
```

### 2. Install Dependencies
```bash
pip install ultralytics opencv-python matplotlib
```

### 3. Run Detection on Image
```python
from ultralytics import YOLO

model = YOLO("models/best.pt")

results = model.predict(
    source="images/demo/input_plastic.jpg",
    save=True,
    conf=0.5
)

print(f"Detected: {len(results[0].boxes)} bottles")
```

### 4. Run on Webcam
```python
from ultralytics import YOLO

model = YOLO("models/best.pt")

# 0 = default webcam
model.predict(
    source=0,
    show=True,
    conf=0.5
)
```

### 5. Run on Video
```python
from ultralytics import YOLO

model = YOLO("models/best.pt")

model.predict(
    source="your_video.mp4",
    save=True,
    conf=0.5
)
```

---


## 🧠 Skills Demonstrated

`Computer Vision` `Object Detection` `YOLOv8`
`Deep Learning` `Dataset Annotation` `Model Training`
`Model Inference` `Python` `Google Colab` `Roboflow`
`PyTorch` `OpenCV` `Transfer Learning`

---

<div align="center">

Made with ❤️ using YOLOv8 + Google Colab

⭐ Star this repo if you found it helpful!

</div>
```

---
