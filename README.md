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

```bash
git clone https://github.com/mestakindo/YOLOP-Ghostnet-Thesis.git
cd YOLOP-Ghostnet-Thesis
pip install -r requirements.txt

# 🚗 YOLOP-GhostNet: Joint Perception for Autonomous Driving

This repository presents an improved multi-task perception model based on the original YOLOP framework for autonomous driving scene understanding.

The work focuses on improving lightweight perception performance and multi-task optimization for real-time deployment scenarios.

---

## 📄 Conference Paper

**Implementation of Joint Segmentation Semantic Understanding Method to Develop Autonomous Vehicle Driving Perception**

Conference: 2025 9th International Conference on Instrumentation, Control, and Automation (ICA)  
Date: August 2025  
DOI: 10.1109/ICA65945.2025.11252505  

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

The proposed architecture follows a shared backbone multi-task perception design:


Input Image
↓
GhostNet Backbone
↓
Shared Feature Representation
↓
┌──────────────┬──────────────┬──────────────┐
│ Detection │ Drivable Area│ Lane Line │
│ Head │ Segmentation │ Segmentation │
└──────────────┴──────────────┴──────────────┘


---

## ⚙️ Installation

git clone https://github.com/mestakindo/YOLOP-Ghostnet-Thesis.git
cd YOLOP-Ghostnet-Thesis
pip install -r requirements.txt

## 🚀 Training

To train the model using default configuration:

python tools/train.py --cfg lib/config/default.py

You may modify configuration parameters depending on dataset path, batch size, or training strategy.

---

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
