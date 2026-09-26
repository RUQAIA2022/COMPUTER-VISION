# Task 04: Cat vs Dog CNN Classification

This task implements a compact convolutional neural network for binary image classification using PyTorch. The notebook builds a CNN to distinguish between cat and dog images, covering dataset preparation, preprocessing, training, evaluation, and diagnostic analysis of model behavior.

## Overview

The task focuses on a real-world computer vision workflow: taking raw image files, turning them into tensors, feeding them into a CNN, and evaluating classification performance on unseen data. The notebook is structured to teach both the practical pipeline and the reasoning behind each design choice.

## Core Methods

- Dataset preparation and balanced train/validation/test splitting
- Image preprocessing with resizing and normalization
- Data loading with `ImageFolder` and `DataLoader`
- Augmentation using random horizontal flip and small rotation
- CNN architecture built from repeated convolution, ReLU, and pooling blocks
- Binary classification head with a single output logit
- Loss function using binary cross-entropy with logits
- Optimization with Adam
- Training and validation loops with accuracy tracking
- Performance analysis through loss curves, confusion matrix, and prediction inspection

## Workflow

1. Load the raw cat and dog image folders.
2. Filter out unreadable files and create a clean dataset split.
3. Resize images to a consistent shape and normalize pixel values.
4. Build PyTorch datasets and batches for training and evaluation.
5. Train a small CNN with convolutional feature extraction followed by a classifier.
6. Evaluate the model on validation and test data.
7. Inspect predictions, failure cases, and confidence scores to understand model behavior.

## Model Architecture

The CNN in this notebook follows a typical pattern for image classification:

- input image tensor with RGB channels
- several convolution blocks with ReLU activation and max pooling
- feature map extraction
- flattening into a feature vector
- fully connected layers for class decision-making
- final single output representing the probability of the dog class

This architecture is intentionally lightweight so it can be trained quickly in a teaching environment while still demonstrating the core ideas behind modern CNNs.

## Folder Structure

```text
task_04_cnn_classification/
├── cnn_cat_and_dog_classification.ipynb   # Main training and evaluation notebook
├── cnn_cat_dog.pt                         # Saved trained model weights
├── data/                                  # Raw dataset folder
│   ├── Cat/
│   └── Dog/
├── dataset/                               # Prepared train/val/test split
│   ├── train/
│   ├── val/
│   └── test/
├── venv/                                  # Local virtual environment
├── .gitignore                             # Git ignore rules
└── README.md                              # Task documentation
```

## Tech Stack

- Python
- PyTorch
- Torchvision
- PIL (Python Imaging Library)
- NumPy
- Matplotlib

## Requirements

Install the required dependencies with:

```bash
pip install torch torchvision matplotlib pillow numpy
```

## Run Instructions

1. Open the task folder.
2. Activate the Python environment if one is set up.
3. Launch Jupyter Notebook or VS Code with notebook support.
4. Open `cnn_cat_and_dog_classification.ipynb`.
5. Run the notebook cells in order.

Alternatively, start Jupyter from the terminal:

```bash
jupyter notebook
```

## Evaluation and Interpretation

The notebook evaluates the model using standard classification metrics and diagnostics:

- training and validation loss curves
- training and validation accuracy
- confusion matrix for class-level errors
- probability histograms for confidence analysis
- sample predictions showing correct and incorrect classifications

This makes the task suitable both as a learning exercise and as a portfolio example demonstrating practical model evaluation.

## Summary

This task provides a clear and practical introduction to CNN-based image classification. It covers the pipeline from raw images to model training and analysis, making it a strong example of applied computer vision and deep learning in a compact, educational format.
