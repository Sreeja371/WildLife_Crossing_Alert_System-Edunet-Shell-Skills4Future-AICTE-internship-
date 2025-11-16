# 🦌 Wildlife Crossing Alert System using YOLOv8

> Real-time animal detection system for road safety and wildlife conservation

[![Python](https://img.shields.io/badge/Python-3.10-blue)](https://python.org)
[![YOLOv8](https://img.shields.io/badge/YOLOv8-Ultralytics-green)](https://github.com/ultralytics/ultralytics)
[![License](https://img.shields.io/badge/License-MIT-yellow)](LICENSE)

---

## 📋 Project Overview

This project implements an AI-powered wildlife detection system using **YOLOv8** to prevent animal-vehicle collisions and support conservation efforts. The system detects 12 different animal species in real-time from road/railway surveillance footage and triggers alerts.

### 🌍 Green Skills Integration
- **Biodiversity Protection:** Prevents wildlife casualties on roads
- **Sustainable Infrastructure:** Enables smart eco-friendly transportation
- **Conservation Data:** Tracks animal movement patterns for research
- **Climate Adaptation:** Helps species navigate changing habitats

---

## 🎯 Features

✅ Real-time detection of 12 animal species  
✅ 89% accuracy (mAP50)  
✅ Automated alert system  
✅ Detection logging with timestamps  
✅ Fast inference (~15ms per image)  
✅ Deployable on edge devices  

---

## 🛠️ Tech Stack

- **YOLOv8n** - Object detection model
- **Python 3.10** - Programming language
- **PyTorch** - Deep learning framework
- **OpenCV** - Video processing
- **Google Colab** - Cloud training (Tesla T4 GPU)
- **Roboflow** - Dataset management

---

## 📊 Model Performance

| Metric | Value |
|--------|-------|
| **mAP50** | 89.0% |
| **Precision** | 90.3% |
| **Recall** | 82.1% |
| **Inference Speed** | ~15ms/image |
| **Training Time** | 1.4 hours |

### Class-wise Performance
- Leopard: 98.5%
- Cat: 98.7%
- Tiger: 98.0%
- Elephant: 96.8%

---

## 📁 Project Structure
```
wildlife_detection_project/
├── data/
│   ├── animal_detection/      # Dataset (5,726 images)
│   └── DATASET_INFO.md
├── model/
│   └── wildlife_detection_v12/
│       └── weights/
│           ├── best.pt        # Best model weights
│           └── last.pt
├── results/
│   ├── test_images/           # Detection outputs
│   └── final_tests/
├── scripts/                   # Python scripts
├── utils/
│   └── alert_system.py       # Alert functions
├── notebooks/                # Colab notebooks
├── RESULTS_SUMMARY.md
└── README.md
```

---

## 🚀 Installation & Setup

### 1. Clone Repository
```bash
git clone https://github.com/YOUR_USERNAME/wildlife-crossing-alert-system.git
cd wildlife-crossing-alert-system
```

### 2. Install Dependencies
```bash
pip install ultralytics opencv-python roboflow
```

### 3. Download Dataset
- Go to [Roboflow Dataset](https://universe.roboflow.com)
- Download in YOLOv8 format
- Place in `data/animal_detection/`

### 4. Train Model
```python
from ultralytics import YOLO

model = YOLO('yolov8n.pt')
model.train(
    data='data/animal_detection/data.yaml',
    epochs=50,
    imgsz=640,
    batch=16
)
```

### 5. Run Inference
```python
model = YOLO('model/wildlife_detection_v12/weights/best.pt')
results = model.predict(source='path/to/image.jpg', save=True)
```

---

## 📸 Sample Results

### Detection Examples
![Sample Detection 1](results/sample1.jpg)
![Sample Detection 2](results/sample2.jpg)

### Training Metrics
![Training Results](model/wildlife_detection_v12/results.png)

---

## 🎯 Use Cases

1. **Highway Monitoring** - Detect animals approaching roads
2. **Railway Safety** - Alert train operators of wildlife on tracks
3. **Conservation Research** - Track animal movement patterns
4. **Smart Infrastructure** - Integrate with automated warning systems

---

## 🌱 Environmental Impact

- **Prevents roadkill** of endangered species
- **Reduces vehicle accidents** caused by wildlife
- **Supports biodiversity** conservation efforts
- **Enables data-driven** wildlife management

---

## 🔮 Future Enhancements

- [ ] Night-vision support with infrared cameras
- [ ] Mobile app for driver alerts
- [ ] Web dashboard for monitoring
- [ ] Deployment on Raspberry Pi
- [ ] Multi-camera integration
- [ ] Distance estimation using depth sensors

---

## 📊 Dataset

**Source:** Roboflow Universe  
**Total Images:** 5,726  
**Classes:** Bear, Buffalo, Camel, Cat, Cow, Deer, Dog, Donkey, Elephant, Leopard, Lion, Tiger  
**Split:** 87% train, 6% validation, 6% test  

---


## 🙏 Acknowledgments

- Ultralytics for YOLOv8
- Roboflow for dataset platform
- Google Colab for free GPU access

---

**⭐ If this project helped you, please give it a star!**
