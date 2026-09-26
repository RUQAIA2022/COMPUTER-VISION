
# Task 02: Image Processing with OpenCV & PyTorch

This task is a hands-on computer vision exercise focused on image preprocessing, dataset cleaning, and basic visual analysis using OpenCV, NumPy, Matplotlib, and PyTorch utilities. The notebook demonstrates how to load image data, inspect properties, normalize values, and prepare images for downstream machine learning pipelines.

## Overview

The workflow in this task includes:
- Downloading and setting up a public image dataset via KaggleHub.
- Collecting and validating image paths and class labels from directories.
- Filtering out empty, corrupted, or unreadable files.
- Inspecting image dimensions, channels, and pixel intensity ranges.
- Resizing, scaling, and applying normalization techniques used in deep learning.
- Converting images to grayscale and applying thresholding methods.
- Applying Gaussian blur and Canny edge detection.

## Task Objectives

By completing this task, you will learn how to:
- Read and manipulate image arrays correctly in OpenCV.
- Work with BGR and RGB color spaces.
- Clean and validate a dataset before model ingestion.
- Resize images and normalize pixel intensities.
- Convert images to grayscale and binary representations.
- Extract edges and understand the effects of image filtering operations.

## Folder Structure

```text
task_02_image_processing/
├── image_processing.ipynb    # Main notebook containing the task code
├── data/                     # Dataset folder used for the exercises
├── venv/                     # Python virtual environment
├── .gitignore                # Git ignore file
└── README.md                 # Task documentation

```

## Dataset & Preparation

The task utilizes an image dataset obtained via KaggleHub, organized into class folders.

* The script automatically maps directory names to integer labels.
* Implements validation checks to remove zero-byte or corrupted files that OpenCV cannot decode.

## Key Task Workflow

1. **Dataset Preparation:** Setting up paths, labels, and filtering invalid files.
2. **Image Inspection:** Checking data types, shapes, dimensions, and pixel ranges using NumPy arrays.
3. **Image Transformations:** Performing scaling, float normalization, and converting inputs into PyTorch tensors.
4. **Thresholding:** Exploring binary segmentation and intensity adjustments.
5. **Filtering & Edge Detection:** Applying Gaussian smoothing and Canny edge detection for boundary extraction.

## Technologies Used

* Python 3
* OpenCV (`cv2`)
* NumPy
* Matplotlib
* PyTorch
* Torchvision
* KaggleHub

## Requirements

Install the required packages using pip:

```bash
pip install opencv-python numpy matplotlib torch torchvision kagglehub

```

## How to Run

1. Open the task folder in Visual Studio Code.
2. Ensure your Python virtual environment is activated.
3. Open `image_processing.ipynb`.
4. Run the cells sequentially to execute the image processing pipeline.

## Learning Outcomes

After completing this task, you will be comfortable with basic image preprocessing, dataset validation, and foundational computer vision operations required for deep learning models.

## License

This task is intended for educational and portfolio-building purposes.
