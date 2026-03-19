# EatFresh — Food Freshness Detection using Deep Learning

A deep learning system that classifies food freshness and identifies spoiled regions using computer vision.

![cut1-ezgif com-optimize](https://github.com/user-attachments/assets/6d1b06ae-08b5-48ee-8cce-636f44646378)

---

## Overview

EatFresh is a computer vision application designed to determine whether fruits and vegetables are fresh or rotten using image input.

The system combines:

* Multi-task image classification (type + freshness)
* Image segmentation to detect spoiled regions

The goal is to reduce food waste and improve food safety through automated decision-making.

---

## Problem

Consumers and businesses struggle to accurately assess food freshness using visual inspection.

* Early spoilage is difficult to detect
* Misjudgements lead to food waste or health risks
* Manual inspection is inconsistent

This project provides an automated, scalable solution using deep learning.

---

## Solution

The system processes an image and outputs:

* Produce type (apple, banana, carrot, potato)
* Freshness level (fresh, slightly rotten, rotten)
* Segmentation mask highlighting spoiled regions

---

## Model Architecture

### Multi-Task CNN (Classification)

![MultiTask](INSERT_MULTITASK_MODEL_IMAGE)

* ResNet-18 backbone (pretrained)
* Shared feature extractor
* Two prediction heads:

  * Freshness classification
  * Produce classification

---

### U-Net (Segmentation)

![UNet](INSERT_UNET_IMAGE)

* Encoder-decoder architecture
* Skip connections for spatial accuracy
* Outputs pixel-level spoilage mask

---

## Model Output

![Output](INSERT_MODEL_OUTPUT_IMAGE)

The system provides:

* Original image
* Freshness prediction
* Produce classification
* Visual segmentation of spoiled areas

---

## Results

### Classification Performance

* Produce classification accuracy: **97.31% (test)**
* Freshness classification accuracy: **79.95% (test)**

### Training Performance

![Training](INSERT_ACCURACY_LOSS_GRAPH)

* Stable learning curves
* Minimal overfitting
* Good generalisation across datasets

---

### Segmentation Results

![Segmentation](INSERT_SEGMENTATION_RESULTS)

* IoU Score: **~51% (test)**
* Successfully identifies major spoiled regions
* Struggles with fine-grained defects

---

## Key Insights

* Multi-task learning improves efficiency by combining two tasks into one model
* Classification is easier than freshness detection due to subtle visual differences
* Segmentation adds explainability to model predictions

---

## Limitations
![Failure](<img width="1078" height="394" alt="image" src="https://github.com/user-attachments/assets/68774cf4-6671-488f-b67f-7c4dbd6a6ddb" />)





* Limited to 4 produce types
* Freshness classification less accurate than type classification
* Segmentation struggles with subtle or small defects
* Model may misclassify unseen produce (e.g., orange → apple)

---

## Tools and Technologies

* Python
* PyTorch
* ResNet-18
* U-Net
* CVAT (annotation)
* OpenCV
* Django (web app integration)

---

## Dataset

Dataset sourced from Roboflow:
https://universe.roboflow.com/college-74jj5/freshness-fruits-and-vegetables/browse?queryText=&pageSize=50&startingIndex=0&browseQuery=true

---

## Acknowledgements

* Contributors: Mark Fernandez, Solvin Kang, Emil Avanesov
* Scaffold web application by Gitarth Vaishnav

---

## Future Improvements

* Expand dataset to more produce types
* Improve segmentation accuracy with advanced architectures
* Enable real-time video-based detection
* Optimise for mobile deployment

---

## Repository Structure

```
/models  
/data  
/app  
/images  
```

---

## Author

Solvin Kang
Machine Learning | Computer Vision | Data Science
