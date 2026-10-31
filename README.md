# UrbanEye – AI-Powered Road Anomaly Detection

<p align="center">
  <strong>Intelligent Road Monitoring • Computer Vision • Deep Learning</strong>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Model-YOLOv8n-blue" alt="YOLOv8n">
  <img src="https://img.shields.io/badge/Version-Model%205%20V3-green" alt="Model Version">
  <img src="https://img.shields.io/badge/Training-100%20Epochs-orange" alt="Training">
  <img src="https://img.shields.io/badge/Framework-Ultralytics-red" alt="Ultralytics">
  <img src="https://img.shields.io/badge/Status-Active%20Development-brightgreen" alt="Status">
</p>

## 1. Project Overview

**UrbanEye** is an AI-powered road monitoring project designed to detect road-related objects and anomalies using computer vision and deep learning.

The project aims to identify road conditions and potentially hazardous situations through image-based object detection. The trained model is intended to support future integration with a Raspberry Pi 4-based intelligent road monitoring system.

The AI model is being developed independently to allow training, testing, optimization, and evaluation before integration into the complete UrbanEye system.

## 2. Project Objectives

- Detect road-related objects and road anomalies using deep learning.
- Identify damaged road surfaces and other important road objects.
- Train and fine-tune YOLOv8 models using road image datasets.
- Evaluate model performance using precision, recall, and mAP.
- Improve detection performance using additional datasets.
- Prepare the trained model for edge deployment.
- Explore real-time road monitoring using Raspberry Pi 4.

## 3. Technology Stack

| Technology | Purpose |
|---|---|
| Python | Programming language |
| YOLOv8n | Object detection model |
| Ultralytics | Model training and inference |
| PyTorch | Deep learning framework |
| OpenCV | Image processing and visualization |
| CUDA | GPU acceleration |
| Kaggle | Dataset sourcing |
| Raspberry Pi 4 | Planned edge deployment |

## 4. Model Information – Model 5 V3

The current repository contains the trained **UrbanEye Model 5 V3**, developed through multiple fine-tuning stages with approximately 100 cumulative training epochs.

| Parameter | Details |
|---|---|
| Model | YOLOv8 Nano |
| Model Version | Model 5 V3 |
| Total Training | 100 cumulative epochs |
| Input Dataset | UrbanEye V3 Road Damage Dataset |
| Number of Classes | 6 |
| Training Framework | Ultralytics + PyTorch |
| Training Hardware | NVIDIA RTX 3050 6GB Laptop GPU |
| Deployment Target | Raspberry Pi 4 |

*Note: The 100 epochs represent cumulative training across multiple fine-tuning stages, not one uninterrupted training session.*

## 5. Detection Classes

The model is trained to detect six classes:

| Class ID | Class Name | Description |
|---|---|---|
| 0 | HMV | Heavy Motor Vehicle |
| 1 | LMV | Light Motor Vehicle |
| 2 | Pedestrian | Pedestrians on the road |
| 3 | RoadDamages | Road damage and pothole-related anomalies |
| 4 | SpeedBump | Speed breakers and road humps |
| 5 | UnsurfacedRoad | Unsurfaced road conditions |

## 6. Dataset Information

The UrbanEye V3 dataset combines the project's existing road dataset with selected additional road-damage examples.

The dataset is organized into three subsets:

```text
UrbanEye_V3_RoadDamage/
│
├── train/
│   ├── images/
│   └── labels/
│
├── val/
│   ├── images/
│   └── labels/
│
├── test/
│   ├── images/
│   └── labels/
│
└── data.yaml
```

Dataset configuration:

```yaml
path: D:/UrbanEye-AI/merged_datasets/UrbanEye_V3_RoadDamage

train: train/images
val: val/images
test: test/images

nc: 6

names:
  - HMV
  - LMV
  - Pedestrian
  - RoadDamages
  - SpeedBump
  - UnsurfacedRoad
```

The dataset is used for model training, validation, and independent testing.

## 7. Model Performance – Model 5 V3

The following results are from the Model 5 V3 evaluation on the test dataset.

### Overall Evaluation

| Metric | Result |
|---|---:|
| Precision | 82.3% |
| Recall | 75.8% |
| mAP@0.5 | 80.5% |
| mAP@0.5:0.95 | 44.7% |

### Class-wise Evaluation

| Class | Precision | Recall | mAP@0.5 |
|---|---:|---:|---:|
| HMV | 93.5% | 96.0% | 97.1% |
| LMV | 91.3% | 92.9% | 95.5% |
| Pedestrian | 85.7% | 77.8% | 85.1% |
| RoadDamages | 65.9% | 41.9% | 48.4% |
| SpeedBump | 73.1% | 84.9% | 85.0% |
| UnsurfacedRoad | 84.1% | 61.1% | 72.1% |

### Performance Analysis

The current model demonstrates promising detection performance for vehicles, pedestrians, and speed breakers.

Road damage detection remains an area for improvement, particularly for water-filled potholes, challenging lighting conditions, and visually complex road surfaces.

Further dataset refinement, annotation review, and targeted model optimization are planned.

## 8. Repository Structure

```text
UrbanEye-Road-Anomaly-AI/
│
└── Model5_V3_100epochs/
    │
    ├── UrbanEye_V3_Model5_100epochs_best.pt
    ├── UrbanEye_V3_Model5_100epochs_last.pt
    ├── Model5_V3_100epochs_metrics.txt
    ├── data.yaml
    └── results.csv
```

### Model Files

| File | Description |
|---|---|
| `UrbanEye_V3_Model5_100epochs_best.pt` | Best-performing trained checkpoint |
| `UrbanEye_V3_Model5_100epochs_last.pt` | Final training checkpoint |
| `Model5_V3_100epochs
