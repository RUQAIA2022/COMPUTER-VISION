# 🚗 Automatic Number Plate Recognition (ANPR) with YOLOv8

<p align="center">
  <img src="https://img.shields.io/badge/AI-YOLOv8-00D1B2?style=for-the-badge" alt="YOLOv8" />
  <img src="https://img.shields.io/badge/Project-ANPR-FF6B6B?style=for-the-badge" alt="ANPR" />
  <img src="https://img.shields.io/badge/Framework-Gradio-5865F2?style=for-the-badge" alt="Gradio" />
</p>

A portfolio-ready computer vision project focused on Automatic Number Plate Recognition (ANPR) using YOLOv8 for accurate and fast license plate detection. The system is designed to detect number plates from vehicle images, enabling real-world applications in traffic monitoring, security, toll systems, and smart city infrastructure.

---

## 1. 📌 Project Overview & Objective

This project implements an end-to-end ANPR pipeline based on the YOLOv8 object detection model. The primary objective is to detect vehicle number plates with high precision and reliability under real-world conditions.

Key highlights:
- Uses YOLOv8 for object detection
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

The training pipeline uses Ultralytics YOLOv8 with transfer learning from the pre-trained weights file:

- Model: YOLOv8 nano
- Pretrained weights: `yolov8n.pt`
- Transfer learning: Yes
- Epochs: 25
- Batch size: 16

### Training setup
The model was initialized with the pretrained YOLOv8 nano checkpoint and fine-tuned on the annotated ANPR dataset. This approach helps reduce training time while improving convergence and detection quality.

### Training summary
- Base architecture: YOLOv8n
- Fine-tuning strategy: transfer learning
- Training epochs: 25
- Batch size: 16
- Objective: maximize detection accuracy for number plates

---

## 4. 📊 Evaluation & Results

The model was evaluated on the unseen test set to measure its detection performance. The results are:

- Precision: 0.999
- Recall: 1.0
- mAP50: 0.995
- mAP50-95: 0.893

These metrics indicate excellent detection quality, especially in terms of precision and recall, with a very high mean average precision at IoU threshold 0.5. The results demonstrate that the model is highly reliable for number plate detection in the evaluated dataset.

### Interpretation
- Precision of 0.999 means the model rarely produces false positives
- Recall of 1.0 means it successfully detects almost all ground truth plates
- mAP50 of 0.995 confirms strong localization performance
- mAP50-95 of 0.893 reflects robust detection across stricter overlap thresholds

---

## 5. ⚠️ Error Analysis

Although the model performs strongly overall, certain edge cases still pose challenges:

### Illumination issues
- Overexposure or low-light conditions can reduce contrast between the plate and the surroundings
- Strong shadows may distort the plate boundaries and affect detection confidence

### Extreme viewing angles
- Side-facing or highly tilted vehicles may cause partial plate visibility
- Extreme perspective distortion can make bounding boxes less precise

### Background confusion
- Complex scenes with reflective surfaces, decorative frames, or other text-like objects may confuse the detector
- Dense urban backgrounds or vehicle parts resembling plate edges can increase false positives in difficult scenes

These failure modes provide valuable direction for future improvements such as:
- Data augmentation for illumination variation
- Additional angle-variant training samples
- Better class balancing and background filtering

---

## 6. 🎛️ Interactive Demo

A Gradio-based interface was built to make the model easy to use and visually inspect. The app supports:
- Image upload for inference
- Automatic bounding box detection
- Instant visualization of results
- User-friendly interaction for testing without writing code

### Important implementation detail
The app handles image channel conversion correctly:
- Converts from RGB to BGR before processing when required
- Displays detections with bounding boxes in real time
- Makes the output immediately understandable for non-technical users

This makes the project ideal for demonstration in a portfolio, hackathon, or prototype presentation.

---

## 7. ⚙️ Installation & Usage

Follow the steps below to set up the project locally and run the interactive ANPR demo.

### 1) Clone the repository

```bash
git clone https://github.com/your-username/automatic-number-plate-recognition.git
cd automatic-number-plate-recognition
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

### 4) Run the application

```bash
python app.py
```

If the project uses a notebook-driven demo or a Gradio launcher file, run the corresponding script as indicated in the repository.

### 5) Open the Gradio interface

After the app starts, the terminal will provide a local URL such as:

```bash
http://127.0.0.1:7860
```

Open this in your browser to upload an image and view the detections in real time.

---

## 8. 🧰 Project Structure

```text
automatic-number-plate-recognition/
├── data/
│   ├── train/
│   ├── valid/
│   └── test/
├── annotations/
│   └── YOLO format .txt files
├── model/
│   └── trained weights
├── notebooks/
│   └── automatic_number_plate_recognition.ipynb
├── app.py
├── requirements.txt
├── README.md
└── inference/
    └── demo scripts
```

---

## 9. ✅ Summary

This project demonstrates a high-performing ANPR system based on YOLOv8, trained with transfer learning and evaluated on an unseen test set. It combines strong technical performance, a clear dataset pipeline, and an interactive Gradio demo suitable for professional showcasing.

Key project outcomes:
- YOLOv8-based number plate detection
- High-accuracy model training
- Clean preprocessing pipeline in YOLO format
- Robust evaluation metrics
- Portfolio-ready demo application

If you are looking for a production-style computer vision project for a GitHub portfolio, this repository is a strong example of practical AI implementation with measurable results.

---

## 10. 📎 Tech Stack

- Python
- Ultralytics YOLOv8
- OpenCV
- NumPy
- Gradio
- Kaggle dataset
- Jupyter Notebook

---

## 11. 💡 Future Enhancements

- Extend detection to full ANPR with OCR for reading plate text
- Add multi-country plate support
- Improve robustness under low light and motion blur
- Deploy as a web app or REST API
- Optimize for edge devices and real-time CCTV pipelines

