
# 🚗 Automatic Number Plate Recognition (ANPR) with YOLOv8

<p align="center">
  <img src="https://img.shields.io/badge/AI-YOLOv8-00D1B2?style=for-the-badge" alt="YOLOv8" />
  <img src="https://img.shields.io/badge/Project-ANPR-FF6B6B?style=for-the-badge" alt="ANPR" />
  <img src="https://img.shields.io/badge/Framework-Gradio-5865F2?style=for-the-badge" alt="Gradio" />
</p>

A portfolio-ready computer vision project focused on Automatic Number Plate Recognition (ANPR) using YOLOv8 for accurate and fast license plate detection, along with a comparative performance study using YOLOv11. The system is designed to detect number plates from vehicle images, enabling real-world applications in traffic monitoring, security, toll systems, and smart city infrastructure.

---

## 1. 📌 Project Overview & Objective

This project implements an end-to-end ANPR pipeline based on the YOLOv8 object detection model, with an additional comparative implementation using YOLOv11. The primary objective is to detect vehicle number plates with high precision and reliability under real-world conditions.

Key highlights:
- Uses YOLOv8 for object detection and YOLOv11 for comparison
- Optimized for number plate localization
- Fine-tuned using transfer learning
- Includes a real-time interactive demo with Gradio
- Designed for practical deployment and portfolio demonstration

The solution focuses on:
- Accurate bounding box detection of plates
- Fast inference suitable for real-time applications
- A clean, user-friendly interface for demonstration
- Model evaluation on an unseen test set to validate generalization

---

## 2. 🧠 Dataset & Preprocessing

The dataset used for this project was sourced from Kaggle and contains labeled vehicle images for number plate detection. The annotations were prepared in the standard YOLO detection format using `.txt` files, where each image has a corresponding text file containing class IDs and normalized bounding box coordinates.

### Dataset characteristics
- Source: Kaggle vehicle/number plate dataset
- Annotation format: YOLO format (`.txt`)
- Object class: Number plate
- Image and annotation files organized for training, validation, and testing

### Preprocessing workflow
- Loaded images and corresponding YOLO labels
- Verified annotation consistency with image dimensions
- Ensured correct bounding box normalization
- Prepared dataset for model training in Ultralytics YOLO format

### Train / Validation / Test split strategy
The dataset was split programmatically from the original validation set to create an unseen test subset, following this exact strategy:

- 1,526 training images
- 84 validation images
- 84 unseen test images

This split ensures the model is evaluated on truly unseen data, providing a more reliable estimate of real-world performance.

---

## 3. 🏋️ Model Training

The training pipeline uses Ultralytics YOLOv8 (and YOLOv11 for comparison) with transfer learning from pre-trained weights:

- Models: YOLOv8 nano (`yolov8n.pt`) & YOLOv11 nano (`yolo11n.pt`)
- Transfer learning: Yes
- Epochs: 25
- Batch size: 16

### Training setup
The models were initialized with pretrained checkpoints and fine-tuned on the annotated ANPR dataset. This approach helps reduce training time while improving convergence and detection quality.

---

## 4. 📊 Evaluation & Results (YOLOv8 & YOLOv11 Comparison)

The models were evaluated on the unseen test set to measure detection performance. 

### YOLOv8 Results:
- Precision: 0.991
- Recall: 0.992
- mAP50: 0.993
- mAP50-95: 0.871

### YOLOv11 Results (Comparison):
- Precision: 0.992
- Recall: 0.984
- mAP50: 0.995
- mAP50-95: 0.878

These metrics indicate excellent detection quality. Both models demonstrate high reliability for number plate detection, with YOLOv11 providing a competitive lightweight alternative architecture.

---

## 5. ⚠️ Error Analysis

Although the models perform strongly overall, certain edge cases still pose challenges:

### Illumination issues
- Overexposure or low-light conditions can reduce contrast between the plate and the surroundings
- Strong shadows may distort the plate boundaries and affect detection confidence

### Extreme viewing angles
- Side-facing or highly tilted vehicles may cause partial plate visibility
- Extreme perspective distortion can make bounding boxes less precise

### Background confusion
- Complex scenes with reflective surfaces, decorative frames, or other text-like objects may confuse the detector
- Dense urban backgrounds or vehicle parts resembling plate edges can increase false positives in difficult scenes

---

## 6. 🎛️ Interactive Demo & Video Walkthrough

A Gradio-based interface was built to make the model easy to use and visually inspect. The app supports:
- Image upload for inference
- Automatic bounding box detection
- Instant visualization of results

- **System Demo Video:** You can watch a recorded walkthrough of the live Gradio interface detecting license plates in real-time:  
  [▶️ Click here to watch the ANPR System Demo Video](./anpr_demo.mp4)

---

## 7. ⚙️ Installation & Usage

Follow the steps below to set up the project locally and run the interactive ANPR demo.

### 1) Clone the repository

```bash
git clone https://github.com/RUQAIA2022/ANPR-System.git
cd ANPR-System

```

### 2) Create a virtual environment (optional but recommended)

```bash
python -m venv venv
venv\Scripts\activate

```

### 3) Install dependencies

```bash
pip install -r requirements.txt

```

### 4) Run the notebooks

Open `automatic_number_plate_recognition.ipynb` or `anpr_yolov11_comparison.ipynb` in your environment to execute training, evaluation, and launch the Gradio web interface.

---

## 8. 🧰 Project Structure

```text
ANPR-System/
├── data/
│   ├── images/
│   └── labels/
├── runs/
│   ├── detect/
│   └── yolov11_anpr_comparison/
├── automatic_number_plate_recognition.ipynb
├── anpr_yolov11_comparison.ipynb
├── data.yaml
├── requirements.txt
├── anpr_demo.mp4
└── README.md

```

---

## 9. ✅ Summary

This project demonstrates a high-performing ANPR system based on YOLOv8 alongside a YOLOv11 performance comparison, trained with transfer learning and evaluated on an unseen test set. It combines strong technical performance, a clear dataset pipeline, and an interactive Gradio demo suitable for professional showcasing.

---

## 10. 📎 Tech Stack

* Python
* Ultralytics YOLOv8 / YOLOv11
* OpenCV
* NumPy
* Gradio
* Kaggle dataset
* Jupyter Notebook

---

## 11. 💡 Future Enhancements

* Extend detection to full ANPR with OCR for reading plate text
* Add multi-country plate support
* Improve robustness under low light and motion blur
* Deploy as a web app or REST API

```

```