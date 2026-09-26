# Task 05: YOLO Object Detection

This task demonstrates a practical object detection workflow using a pretrained YOLO model. The notebook loads an image, runs inference with Ultralytics YOLO, inspects prediction outputs, and visualizes detected bounding boxes, class labels, and confidence scores.

## Overview

The goal of this task is to show how modern object detection models can identify and localize multiple objects in a single image. Instead of predicting only a class for the whole image, YOLO predicts the class and location of each object instance through bounding boxes.

## Core Methods

- Pretrained YOLO model loading with Ultralytics
- Image reading and display using OpenCV and Matplotlib
- Inference with `model(image)`
- Extraction of detection attributes such as bounding boxes, confidence, and class IDs
- Conversion of YOLO outputs into interpretable object information
- Manual drawing of boxes and labels with OpenCV
- Confidence-threshold experimentation to study detection sensitivity

## Workflow

1. Load a pretrained YOLO model.
2. Inspect the dataset of classes known to the model.
3. Read an input image and confirm its size and format.
4. Run inference to detect objects present in the scene.
5. Extract coordinates, class IDs, and confidence scores from `result.boxes`.
6. Convert model outputs into readable labels and bounding boxes.
7. Visualize the final annotated image using OpenCV drawing functions or `result.plot()`.
8. Adjust confidence thresholds to understand how detections change as stricter filtering is applied.

## Why YOLO

YOLO is a widely used real-time object detection framework because it is both fast and accurate for many common classes. It is especially effective for tasks where multiple objects must be identified and localized in a single frame, such as surveillance, traffic monitoring, robotics, and industrial inspection.

## Folder Structure

```text
task_05_yolo_detection/
├── yolo_object_detection.ipynb   # Main YOLO inference notebook
├── data/
│   └── dog.jpg                   # Sample image used for detection
├── yolo26n.pt                    # Pretrained YOLO weights
├── venv/                         # Local virtual environment
├── .gitignore                    # Git ignore rules
├── README.md                     # Task documentation
└── .ipynb_checkpoints/           # Jupyter checkpoints (if generated)
```

## Tech Stack

- Python
- Ultralytics YOLO
- OpenCV
- NumPy
- Matplotlib
- PyTorch (managed by Ultralytics)

## Requirements

Install the required packages:

```bash
pip install ultralytics opencv-python matplotlib
```

## Run Instructions

1. Open the task folder.
2. Activate the Python environment if one is available.
3. Launch Jupyter Notebook or VS Code with Jupyter support.
4. Open `yolo_object_detection.ipynb`.
5. Run the cells in order.

Alternatively, start Jupyter from the terminal:

```bash
jupyter notebook
```

## Interpretation of Detection Output

Each detection produced by YOLO contains:

- bounding box coordinates in pixel space
- a confidence score indicating certainty
- a class ID mapped to a known object class name

This makes YOLO useful for downstream tasks such as automated annotation, scene understanding, and object tracking.

## Summary

This task provides a concise and practical demonstration of object detection in computer vision. It highlights the role of pretrained deep learning models in identifying objects, drawing bounding boxes, and filtering detections based on confidence thresholds.
