# Applied Computer Vision Portfolio

A professional portfolio featuring five foundational computer vision technical tasks and one end-to-end capstone project. The technical tasks cover core image processing and machine learning methods; the capstone applies object detection to automatic number plate recognition, with comparative evaluation and an interactive demonstration.

## Core Technical Tasks

The following folders contain focused technical exercises rather than standalone portfolio projects. Each explores a specific computer vision method through a notebook and its accompanying documentation.

| Task | Focus | Notebook and details |
| --- | --- | --- |
| [Task 01 — OpenCV Basics](./task_01_opencv_basics/) | Image loading and inspection, color spaces, channels, and fundamental transformations | [Notebook](./task_01_opencv_basics/computer%20_vision_1.ipynb) · [Task README](./task_01_opencv_basics/README.md) |
| [Task 02 — Image Processing](./task_02_image_processing/) | Dataset validation, filtering, thresholding, normalization, and image transformations | [Notebook](./task_02_image_processing/image_processing.ipynb) · [Task README](./task_02_image_processing/README.md) |
| [Task 03 — ORB Features](./task_03_orb_features/) | Keypoint and descriptor extraction, feature matching, and robustness to image transformations | [Notebook](./task_03_orb_features/orb.ipynb) · [Task README](./task_03_orb_features/README.md) |
| [Task 04 — CNN Classification](./task_04_cnn_classification/) | Custom PyTorch CNN for cat-versus-dog classification, training, and evaluation | [Notebook](./task_04_cnn_classification/cnn_cat_and_dog_classification.ipynb) · [Task README](./task_04_cnn_classification/README.md) |
| [Task 05 — YOLO Detection](./task_05_yolo_detection/) | Object detection inference, prediction interpretation, and confidence-threshold experimentation | [Notebook](./task_05_yolo_detection/yolo_object_detection.ipynb) · [Task README](./task_05_yolo_detection/README.md) |

## Featured Capstone Project: ANPR System

[ANPR-System](./ANPR-System/) is the repository's sole main capstone project. It fine-tunes lightweight YOLOv8 and YOLOv11 models to localize vehicle number plates and includes an end-to-end training and evaluation workflow, held-out unseen-test evaluation, comparative analysis, and a Gradio interface for image inference.

### Reported unseen-test results

The following results are reported in the [ANPR capstone documentation](./ANPR-System/README.md):

| Model | Precision | Recall | mAP@50 | mAP@50–95 |
| --- | ---: | ---: | ---: | ---: |
| YOLOv8n | 0.991 | 0.992 | 0.993 | 0.871 |
| YOLOv11n | 0.992 | 0.984 | 0.995 | 0.878 |

These are capstone-reported metrics; consult the notebooks and README for the dataset split, methodology, and evaluation context.

- [Read the ANPR capstone README](./ANPR-System/README.md)
- [Review the YOLOv8 workflow](./ANPR-System/automatic_number_plate_recognition.ipynb)
- [Review the YOLOv11 comparison](./ANPR-System/anpr_yolov11_comparison.ipynb)
- [Watch the recorded demo](./ANPR-System/anpr_demo.mp4.mp4)

The implemented system detects and localizes plates. Automatic transcription of plate characters (OCR) is not described as part of the current pipeline.

## Technical coverage

- **Image fundamentals:** image I/O, channel and pixel inspection, color conversion, resizing, cropping, and grayscale conversion.
- **Image processing:** dataset validation, normalization, thresholding, Gaussian filtering, edge detection, and geometric manipulation.
- **Feature-based vision:** ORB keypoint detection and binary descriptor matching with Hamming distance.
- **Deep learning:** custom CNN construction, data preparation and augmentation, model training, validation, and classification diagnostics.
- **Object detection:** YOLO inference, bounding-box interpretation and visualization, confidence filtering, and task-specific fine-tuning.
- **Evaluation and delivery:** held-out testing, comparative metrics, error analysis, and an interactive Gradio demonstration.

## Technology

The technical tasks and capstone use Python and Jupyter notebooks with tools including OpenCV, NumPy, Matplotlib, PyTorch, Torchvision, Pillow, Ultralytics YOLO, and Gradio. Dependencies differ by folder; see its README and dependency files before setting up an environment.

## Getting started

1. Clone or download this repository.
2. Open a technical task or the capstone directory in VS Code or another Jupyter-compatible environment.
3. Follow that folder's README for its Python dependencies, dataset requirements, and execution details.
4. Open its linked notebook and run cells in order.

For the ANPR capstone environment, install the dependencies listed in [`ANPR-System/requirements.txt`](./ANPR-System/requirements.txt). For the technical tasks, refer to their individual READMEs for package-install instructions.

```bash
git clone https://github.com/RUQAIA2022/COMPUTER-VISION.git
cd COMPUTER-VISION
```

There is no single root-level dependency file: each task and the capstone have their own requirements and may rely on folder-specific datasets or model weights. Dataset files and large model artifacts may need to be obtained or prepared separately as described in the relevant documentation.

## Repository structure

```text
.
├── ANPR-System/
│   ├── automatic_number_plate_recognition.ipynb
│   ├── anpr_yolov11_comparison.ipynb
│   ├── data.yaml
│   └── requirements.txt
├── task_01_opencv_basics/
├── task_02_image_processing/
├── task_03_orb_features/
├── task_04_cnn_classification/
└── task_05_yolo_detection/
```

Each technical task folder and the capstone folder contain a dedicated README and notebook(s). Follow those documents for detailed implementation notes, setup instructions, and task- or capstone-specific results.
