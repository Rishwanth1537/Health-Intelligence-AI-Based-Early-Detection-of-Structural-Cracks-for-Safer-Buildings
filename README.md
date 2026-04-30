# 🧱 YOLO Crack Detection using Ultralytics Dataset

An end-to-end deep learning project to **detect structural cracks** in concrete surfaces using **YOLO (Ultralytics)**. The model is trained on a curated dataset and deployed as an interactive **Gradio web application**.

---

## 🚀 Live Demo

🔗 https://huggingface.co/spaces/Akash1hf/yolo-crack-detection  

Upload an image of a wall, road, or structure and get instant crack detection results.

---

## 📌 Project Overview

Structural cracks are early indicators of infrastructure damage. Manual inspection is slow, inconsistent, and not scalable.

This project focuses on:
- Automating crack detection using deep learning  
- Building a fast and lightweight detection pipeline  
- Deploying a usable web interface for real-world interaction  

---

## 📂 Dataset

The model is trained on the **Ultralytics Crack Segmentation Dataset (crack-seg)**.

Source:  
https://github.com/ultralytics/assets/releases/download/v0.0.0/crack-seg.zip  

### Key Details

- Annotation format: YOLO (`.txt`)
- Single class: `crack`
- Originally a segmentation dataset, adapted for detection

---

## ⚙️ Data Preprocessing & Validation

steps that actually matter:

- Verified that every image has a corresponding label file  
- Ensured zero missing or mismatched annotations  
- Removed invalid or corrupted samples (if any)  
- Used a proper dataset configuration file for YOLO training  

YOLO internally handles:
- Image resizing  
- Normalization  
- Data augmentation (flip, scale, etc.)  

---

## 🧠 Model Training

The model is trained using a lightweight YOLO architecture for efficient performance.

### Training Setup

- Model: YOLO (nano variant)  
- Epochs: 50  
- Image size: 640  
- Batch size: 16  
- Early stopping enabled  

### Why This Setup?

- Faster training  
- Lower compute usage  
- Suitable for deployment environments  

---

## 📊 Model Performance

| Metric | Score |
|------|------|
| Precision | ~0.88 |
| Recall | ~0.74 |
| mAP@0.5 | ~0.81 |
| mAP@0.5:0.95 | ~0.64 |

### Honest Take

- Strong precision → fewer false detections  
- Moderate recall → some cracks are still missed  

This is a **good baseline**, not production-grade safety assurance.

---

## 🔍 Inference Pipeline

- Input image is passed to the trained YOLO model  
- Model detects crack regions  
- Output is an annotated image with bounding boxes  

---

## 🌐 Web Application

The project is deployed using **Gradio** on Hugging Face Spaces.

### Features

- Upload custom images  
- Real-time crack detection  
- Visual output with highlighted crack regions  

---

## 🧪 How to Use

1. Open the live demo link  
2. Upload an image of a structure  
3. View detected crack regions instantly  

---

## ⚠️ Limitations

- Limited dataset → affects generalization  
- Detection only → does not provide pixel-level crack shapes  
- Recall is not high → small cracks may be missed  
- Works best on clear, visible cracks  

---

## 🔧 Future Improvements

- Move to segmentation models for precise crack boundaries  
- Train on multiple datasets for better robustness  
- Improve recall through tuning and augmentation  
- Use larger YOLO variants for higher accuracy  
- Extend to video-based detection  

---

## 📜 License

MIT License (or Apache 2.0 depending on usage)
