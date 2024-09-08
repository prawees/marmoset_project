# Marmoset Detection with YOLOv8 and SAM

## Introduction

This project demonstrates the process of detecting marmosets in images using YOLOv8 for bounding box detection and Segment Anything Model (SAM) for segmentation. The project follows a structured pipeline to detect and segment objects effectively.

### Authors:
- 6402001: Gunn Kittichaidamrong
- 6402006: Natchanon Traetulakarn
- 6402009: Prawee Sinweeruthai
- 6402016: Withinat Teewiriya

## How to Use

Follow the steps below to set up and run the marmoset detection and segmentation pipeline:

### 1. Import Dataset

Prepare a dataset containing images of marmosets. The dataset should be organized with images in `datasets/marmoset-train/images/train` and corresponding labels in YOLO format in `datasets/marmoset-train/labels/train`.

### 2. Convert Data into YOLO-Compatible Form

Convert the dataset annotations into YOLO format (`x_center, y_center, width, height` in normalized coordinates). Ensure the images and labels match correctly for the YOLOv8 model to train on.

### 3. Create YAML File

Create a `output.yml` file that defines the dataset structure for YOLOv8 training. The file should include paths to the training and validation datasets and specify the number of classes and their names. 

### 4. Import and Train YOLO Model

Use the YOLOv8 model from the Ultralytics library for training

### 5. Import Test Dataset

Prepare a test dataset to evaluate the YOLOv8 model's performance. Ensure the test images are correctly formatted and placed in the appropriate directory, such as datasets/marmoset-train/images/test

### 6. Import SAM Model

Import the Segment Anything Model (SAM) to perform segmentation based on bounding box detections from YOLOv8. 
We used sam_b.pt.

### 7. Use SAM Model to Segment Data

Use bounding boxes obtained from YOLOv8 to prompt the SAM model for segmentation.
The for loop in the script loops through all the images in the training dataset, detects marmosets with YOLOv8, uses the bounding boxes to generate masks with SAM, and saves the output images with segmentation.

### Requirements
To run this project, you need the following:

Python 3.8+
PyTorch
OpenCV
Ultralytics YOLOv8
Segment Anything Model (SAM)
Jupyter Notebook or Google Colab

### Results
The results will include both bounding box detections from YOLOv8 and precise segmentation masks generated by SAM, which can be visualized to evaluate the models' performance on the marmoset dataset.

### Acknowledgments
- Ultralytics for providing the YOLOv8 model.
- Sira for illustrating the use of deepcut2yolo.
- P'Swiss for illustrating how to download and unzip files using Linux wget commands.
- Aj.Titipat for the instructions and lectures.

Gunn, Natchanon, Prawee, Withinat
EGBE/M 2024
