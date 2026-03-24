# 🚗 YOLOP-GhostNet: Joint Perception for Autonomous Driving

This repository presents an improved multi-task perception model based on YOLOP for autonomous vehicle scene understanding.

---

## 📄 Conference Paper

**Implementation of Joint Segmentation Semantic Understanding Method to Develop Autonomous Vehicle Driving Perception**

📍 2025 9th International Conference on Instrumentation, Control, and Automation (ICA)  
📅 August 2025  
🔗 DOI: 10.1109/ICA65945.2025.11252505  

---

## ⭐ Contributions

- Integration of **GhostNet backbone** for lightweight perception  
- Replacement of activation with **SiLU activation function**  
- Implementation of **SIoU Loss** for better localization performance  
- Optimization of joint multi-task training for:
  - Object Detection  
  - Drivable Area Segmentation  
  - Lane Line Segmentation  

---

## ⚙️ Installation


git clone https://github.com/mestakindo/YOLOP-Ghostnet-Thesis.git

cd YOLOP-Ghostnet-Thesis

pip install -r requirements.txt

---

## ⭐ Key Contributions

- Integration of **GhostNet backbone** for lightweight feature extraction  
- Replacement of activation function with **SiLU activation**  
- Implementation of **SIoU Loss** for improved bounding box regression  
- Optimization of joint multi-task learning configuration for:

  - Object Detection  
  - Drivable Area Segmentation  
  - Lane Line Segmentation  

---

## 🧠 Model Overview

```
Input Image
   ↓
GhostNet Backbone
   ↓
Shared Feature Representation
   ↓
 ┌──────────────┬──────────────┬──────────────┐
 │ Detection    │ Drivable Area│ Lane Line    │
 │ Head         │ Segmentation │ Segmentation │
 └──────────────┴──────────────┴──────────────┘
```

---
---

## 📈 Performance Comparison

---

## 📈 Experimental Results

### 🚗 Object Detection Performance

| Model | Precision | Recall | mAP@0.5 |
|------|-----------|--------|---------|
| YOLOP | 0.110 | 0.88 | 0.44 |
| YOLOP-GhostNet (Ours) | 0.093 | 0.71 | **0.60** |

---

### 🛣 Lane Line Segmentation Performance

| Model | Accuracy | IoU | mIoU |
|------|----------|-----|------|
| YOLOP | 0.699 | 0.266 | 0.625 |
| YOLOP-GhostNet (Ours) | 0.699 | **0.305** | **0.642** |

---

### 🟩 Drivable Area Segmentation Performance

| Model | Accuracy | IoU | mIoU |
|------|----------|-----|------|
| YOLOP | 0.974 | **0.859** | **0.914** |
| YOLOP-GhostNet (Ours) | 0.971 | 0.849 | 0.907 |

---

### ⚡ Inference Speed

| Model | Inference Time | NMS Time |
|------|----------------|----------|
| YOLOP | 0.0030 s/frame | 0.0007 s/frame |
| YOLOP-GhostNet (Ours) | **0.0017 s/frame** | 0.0009 s/frame |

---

## ⚙️ Model Complexity Analysis

| Model | Parameters (Million) | Reduction |
|------|----------------------|-----------|
| Original YOLOP (Paper) | 48.0 | — |
| YOLOP Baseline (Reproduced) | 7.96 | 83.4% ↓ vs Paper |
| YOLOP-GhostNet (Ours) | **7.94** | **0.26% ↓ vs Baseline** |


## 🎯 Qualitative Results

### Daytime Driving Scene

![Day Result](pictures/result_day.jpg)

---

### Night Driving Scene

![Night Result](pictures/result_night.jpg)


## ⚙️ Installation

git clone https://github.com/mestakindo/YOLOP-Ghostnet-Thesis.git
cd YOLOP-Ghostnet-Thesis
pip install -r requirements.txt

## 🚀 Training

To train the model using default configuration:

python tools/train.py --cfg lib/config/default.py

You may modify configuration parameters depending on dataset path, batch size, or training strategy.

---
### 🔬 Training Setup

Two training configurations were evaluated:

- **YOLOP(A)**: Baseline model using CSPDarknet-Tiny backbone across the shared feature extraction pipeline.
- **YOLOP(B)**: Proposed model replacing segmentation branch backbone with **GhostNet**, while keeping other components identical to isolate backbone impact.

---

### 🧠 Implementation Details

- Python Version: ≥ 3.9  
- Framework: PyTorch 2.4.1 + TorchVision  
- GPU: NVIDIA GeForce RTX 4080  
- Configuration Management: YAML-based experiment settings  
- Reproducibility: fixed random seed, version locking, checkpoint saving per experiment  

---

### 📂 Dataset Preparation

- Dataset: BDD100K  
- Split Ratio: **Train / Val / Test = 70 / 20 / 10**
- Detection annotations converted from **COCO JSON → YOLO TXT format**
- Segmentation masks generated as **PNG maps** for:
  - Drivable Area  
  - Lane Line  

---

### 🖼 Image Preprocessing & Augmentation

- Input Resolution: **640 × 640 (Letterbox resize)**
- Pixel Normalization applied  
- Training augmentations:
  - Horizontal Flip  
  - Brightness / Contrast adjustment  
  - Blur  
  - Perspective Transform  
- Optional detection enrichments:
  - Mosaic  
  - MixUp  

---

### ⚙️ DataLoader Configuration

- Batch size adjusted according to GPU VRAM capacity  
- Num workers optimized for throughput  
- Pin memory enabled for faster GPU transfer  

## 🧪 Evaluation

To evaluate trained model:

python tools/test.py
📊 Experimental Environment
GPU: NVIDIA RTX 4080
Framework: PyTorch
Dataset: BDD100K
Training Strategy: Multi-task joint optimization

---

## 🙏 Acknowledgement

This repository is based on the original YOLOP implementation:

https://github.com/hustvl/YOLOP

We sincerely thank the original authors for their contribution.

---

## 📚 Citation

If you use this repository, please cite:

@inproceedings{mestakindo2025joint,
  title={Implementation of Joint Segmentation Semantic Understanding Method to Develop Autonomous Vehicle Driving Perception},
  author={Mestakindo, Fauzand},
  booktitle={International Conference on Instrumentation, Control, and Automation},
  year={2025}
}

## 📜 License

This project follows the MIT License inherited from the original YOLOP repository.
