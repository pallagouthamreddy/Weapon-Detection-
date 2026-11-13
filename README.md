# Weapon Detection System

A deep learning application that detects weapons (**knives** and **guns**) in images and videos using a Convolutional Neural Network (CNN). When a weapon is detected, the application raises an audible beep alert.

## Features

- Trains a CNN on a labelled weapon image dataset
- Detects weapons in a single uploaded image
- Analyses an uploaded video frame by frame and alerts when a weapon appears
- Plays a beep sound on detection
- Plots training accuracy and loss curves
- Simple desktop GUI, with one button per step

## Tech Stack

- Python
- TensorFlow / Keras
- OpenCV
- CNN

## Dataset

- **Classes:** 2 (`KNIVES`, `GUNS`)
- **Size:** 3,535 images
- **Location:** the `Dataset/` folder, with one sub-folder per class

All images are resized to a fixed size and their pixel values are normalised before training.

## How It Works

| Module | What it does |
|---|---|
| **Upload Weapon Dataset** | Reads all images from the dataset folder, resizes them to equal size, normalises pixel values and prepares them for training. |
| **Generate & Load Weapon Detection Model** | Builds and trains the CNN on the processed images (or loads a saved model). |
| **Upload Image** | Lets you choose a test image. |
| **Detect Weapon from Image** | Runs the CNN on the uploaded image, predicts whether it contains a weapon and beeps if one is found. |
| **Detect Weapon from Video** | Lets you choose a video, runs the CNN on every frame and beeps when a weapon is detected. |
| **Weapon Detection Training Accuracy-Loss Graph** | Plots training accuracy and loss against epochs. |

## Project Structure

```
.
├── Dataset/          # KNIVES and GUNS images
├── run.bat           # Launches the application
├── ...               # Source code, saved model, test images/videos
└── README.md
```

> Update this tree to match your repository.

## Getting Started

### Requirements

- Python 3.x
- TensorFlow, Keras, OpenCV, NumPy, Matplotlib

```bash
pip install tensorflow opencv-python numpy matplotlib
```

> Replace this with a `requirements.txt` listing the exact versions you used.

### Run

On Windows, double-click **`run.bat`**, or run it from a terminal:

```bash
run.bat
```

## Usage

1. Click **Upload Weapon Dataset** and select the `Dataset` folder. The app loads and processes the images, reports the number of images and classes (3,535 images, 2 classes) and shows one processed image as a check. Close the preview window to continue.
2. Click **Generate & Load Weapon Detection Model**. The CNN is built and loaded, and a confirmation appears in red text.
3. Click **Upload Image**, choose a test image (for example `3.jpg`) and click **Open**.
4. Click **Detect Weapon from Image**. If a weapon is found, it is marked in the output and a beep plays.
5. Click **Detect Weapon from Video**, choose a video and click **Open**. Each frame is analysed, and a beep plays when a weapon is detected.
6. Click **Weapon Detection Training Accuracy-Loss Graph** to view the training curves. Accuracy rises and loss falls as the epochs increase.

## Screenshots

<!-- Add your screenshots to a /screenshots folder and link them here -->

| Step | Screenshot |
|---|---|
| Dataset loaded | `![Dataset loaded](screenshots/dataset.png)` |
| Model generated | `![Model generated](screenshots/model.png)` |
| Weapon detected in image | `![Image detection](screenshots/image_detection.png)` |
| Weapon detected in video | `![Video detection](screenshots/video_detection.png)` |
| Accuracy-loss graph | `![Training graph](screenshots/graph.png)` |

## Results

- Training accuracy increases and loss decreases with each epoch (see the graph from screens).
 

## Limitations and Future Work

- The model recognises only two classes (knives and guns) and its performance depends on the dataset's coverage of angles, lighting and backgrounds.
- Possible improvements: a larger and more varied dataset, data augmentation, more weapon classes, object localisation (bounding boxes) and cross-platform alerts.

 
