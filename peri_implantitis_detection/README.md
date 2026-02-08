# Peri-Implantitis Detection

This folder contains the project files for a medical computer vision system
designed to detect and grade peri-implant bone loss from panoramic dental radiographs.

# Peri-Implantitis Detection Using Deep Learning

## Overview
This project applies YOLO-based deep learning models to detect and grade peri-implant bone loss from panoramic dental radiographs.

It is designed as a **clinical decision-support prototype**, prioritizing early disease sensitivity, interpretability, and real-world deployment considerations.

## Clinical Motivation
Peri-implantitis is frequently underdiagnosed in its early stages due to subtle radiographic changes and inter-observer variability.
As a practicing dentist, I observed these diagnostic challenges firsthand, which motivated the development of this AI-based approach.

## Dataset
- 1,020 anonymized panoramic dental radiographs
- 3,000+ labeled dental implants
- Four clinical severity classes
- Only anonymized sample images are included in this repository for demonstration purposes

## Model & Methods
- YOLO-based object detection (YOLOv8 / YOLOv12)
- Transfer learning
- Class-weighted loss to address class imbalance
- Data augmentation
- Implemented in Python using PyTorch and OpenCV

## Evaluation
- 80/20 stratified train–test split  
- Metrics prioritized for clinical relevance  

The following figure shows training and validation losses alongside key detection metrics across epochs.

![Training and Validation Metrics](results/training_metrics.jpeg)

The model demonstrates stable convergence with improving precision, recall, and mAP scores, while validation losses remain controlled, suggesting limited overfitting.

### Model Comparison (YOLOv8 vs YOLOv12)

The following figure compares class-wise mAP@0.5 scores between YOLOv8 and YOLOv12 models across clinical severity classes.

![YOLOv8 vs YOLOv12 mAP@0.5 Comparison](results/yolov8_vs_yolov12_map50.jpeg)

YOLOv12 demonstrated improved performance for the dominant and early-stage classes (Healthy and Grade S), while YOLOv8 showed relatively stronger performance in the advanced disease class. This highlights the importance of class-wise evaluation in clinically imbalanced datasets.


**Results:**
- mAP@0.5: 0.81  
- mAP@0.5:0.95: 0.63  
- Recall (early-stage disease): 0.87

## Key Takeaways
- High sensitivity is achievable without sacrificing interpretability
- Many failure cases reflect genuine clinical ambiguity rather than model error
- Dataset quality and labeling consistency had a larger impact than model architecture choice

## Limitations & Future Work
- Retrospective data only
- Single imaging modality
- Prospective clinical validation required before clinical use

## Disclaimer
This project is for research and educational purposes only and is not intended for clinical use.
