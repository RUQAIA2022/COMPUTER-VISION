# Task 03: ORB Feature Detection and Matching

This task demonstrates a core computer vision workflow for detecting and matching local image features using ORB (Oriented FAST and Rotated BRIEF). The notebook loads a reference image, creates a transformed query image with shrinkage and rotation, and evaluates whether the same object can still be recognized under altered viewing conditions.

## Overview

The goal of this task is to highlight how local feature-based methods can establish correspondences between images despite geometric changes. This is a foundational technique used in object recognition, image registration, tracking, stereo matching, and panoramic stitching.

## Core Methods

- OpenCV image loading and preprocessing
- Color conversion between BGR and RGB formats
- Grayscale conversion for efficient feature extraction
- Scale transformation using `cv2.pyrDown`
- Rotation using `cv2.getRotationMatrix2D` and `cv2.warpAffine`
- ORB keypoint detection and descriptor extraction using `cv2.ORB_create()` and `detectAndCompute()`
- Brute-force descriptor matching with `cv2.BFMatcher`
- Hamming-distance comparison for binary ORB descriptors
- Match visualization through `cv2.drawMatches`
- Robustness testing with varying rotation angles and scale changes

## Workflow

1. Load the source image from the local dataset.
2. Convert it to RGB for correct visualization and to grayscale for ORB processing.
3. Generate a query image that is smaller and rotated to simulate a different viewpoint.
4. Detect ORB keypoints and compute descriptors for the reference and transformed images.
5. Match corresponding descriptors between the two images.
6. Visualize the strongest matches to confirm alignment between the same object regions.
7. Adjust transformation settings to evaluate the stability of the feature-matching pipeline.

## Why ORB

ORB is widely used because it is fast, efficient, and well suited to real-time computer vision tasks. It handles rotation and partial scale variation effectively, making it suitable for robust local feature matching in practical applications.

## Folder Structure

```text
task_03_orb_features/
├── orb.ipynb              # Main notebook containing the full ORB workflow
├── data/
│   └── face1.jpeg         # Reference image used for feature matching
├── venv/                  # Local virtual environment
├── .gitignore             # Git ignore rules
├── README.md              # Task documentation
└── .ipynb_checkpoints/    # Notebook checkpoints (if created)
```

## Tech Stack

- Python
- OpenCV
- NumPy
- Matplotlib

## Requirements

Install the required dependencies:

```bash
pip install opencv-python numpy matplotlib
```

## Run Instructions

1. Open the task folder.
2. Activate the Python environment if one is configured.
3. Launch Jupyter Notebook or VS Code with Jupyter support.
4. Open `orb.ipynb` and run the cells sequentially.

Alternatively, run:

```bash
jupyter notebook
```

## Applications

This task reflects core techniques used in:

- object recognition
- image registration
- panorama stitching
- visual tracking
- 3D reconstruction
- feature-based localization

## Summary

This task provides a concise and practical introduction to feature-based matching in computer vision. It demonstrates how ORB detects stable local features, compares descriptors across transformed images, and validates the reliability of a matching pipeline under real-world viewing changes.
