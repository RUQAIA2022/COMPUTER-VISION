# OpenCV Basics for Computer Vision

This project introduces the foundational concepts of computer vision using OpenCV in Python. The notebook demonstrates how to read, inspect, transform, and visualize images, helping build a strong base for more advanced vision tasks such as object detection, feature extraction, and image classification.

## Overview

The exercises in this repository cover essential image processing operations, including:

- Loading images from disk
- Understanding image shapes and color channels
- Converting between BGR and RGB formats
- Extracting color channels
- Accessing and inspecting pixel values
- Resizing and cropping images
- Converting images to grayscale
- Displaying and comparing visual outputs with Matplotlib

This project is a hands-on introduction to the core building blocks used in modern computer vision pipelines.

## Project Structure

```text
task_01_opencv_basics/
├── computer _vision_1.ipynb   # Main notebook with OpenCV exercises
├── data/                      # Image dataset used in the notebook
├── venv/                      # Local virtual environment
├── .gitignore                 # Git ignore rules
└── README.md                  # Project documentation
```

## Objectives

By completing this notebook, the learner will be able to:

- Understand how OpenCV represents images internally
- Work with NumPy arrays that represent image data
- Interpret image dimensions and channel structure
- Visualize images in both OpenCV and Matplotlib workflows
- Perform basic preprocessing tasks commonly required in computer vision

## Topics Covered

### 1. Image Reading and Display

The notebook loads an image with OpenCV and displays it using `cv2.imshow()`. This introduces the basic pipeline of image acquisition and visualization.

### 2. Color Space Conversion

The project highlights the difference between OpenCV's BGR ordering and Matplotlib's RGB convention. A conversion using `cv2.cvtColor(image, cv2.COLOR_BGR2RGB)` is demonstrated to ensure correct color rendering.

### 3. Image Properties

The notebook prints image shape, height, width, and number of channels. This teaches how to interpret matrix-based image data and compute pixel counts.

### 4. Color Channel Extraction

The red, green, and blue channels are extracted and displayed separately, giving insight into the intensity contribution of each channel.

### 5. Pixel-Level Analysis

The project inspects individual pixels and small image regions, which is useful for understanding how image data is structured in arrays.

### 6. Image Transformations

The notebook includes resizing and cropping examples, both of which are common preprocessing steps in real-world vision systems.

### 7. Grayscale Conversion

A grayscale representation is created and compared to the original image, showing how color information is simplified for analysis and processing.

## Requirements

To run the notebook, install the following dependencies:

```bash
pip install opencv-python matplotlib numpy
```

If you are using a virtual environment, ensure it is activated before running the notebook.

## Setup

1. Open the project folder.
2. Activate the virtual environment if available.
3. Launch Jupyter Notebook or VS Code with Jupyter support.
4. Open the notebook and run the cells in order.

## Usage

```bash
jupyter notebook
```

Then open the notebook named `computer _vision_1.ipynb` and execute the cells to observe the image processing steps.

## Example Workflow

The notebook follows a typical image-processing sequence:

1. Read an image
2. Inspect its properties
3. Convert color channels
4. Transform the image
5. Display the results
6. Interpret the output visually

## Learning Outcomes

After working through this notebook, you should be comfortable with:

- OpenCV image loading and visualization
- Basic image array handling in NumPy
- Color channel manipulation
- Simple geometric image transformations
- Essential preprocessing techniques used in computer vision

## Future Extensions

This project can be extended into more advanced computer vision topics such as:

- Edge detection
- Image filtering
- Morphological operations
- Object detection using YOLO
- Face and license plate recognition

## License

This project is intended for educational purposes and is suitable for learning and experimentation.

## Author

Educational computer vision project built for learning OpenCV fundamentals.
