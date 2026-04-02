# CNN-defect-classification-on-Wafer-Maps
This project focuses on automatic classification of wafer defect patterns using deep learning techniques. The goal is to identify different types of defects from wafer map images to support yield analysis in semiconductor manufacturing.  The project explores both a custom Convolutional Neural Net and a transfer learning approach using MobileNetV2.
# Wafer Defect Classification using Deep Learning

## Overview

This project focuses on automatic classification of wafer defect patterns using deep learning techniques. The goal is to identify different types of defects from wafer map images to support yield analysis in semiconductor manufacturing.

The project explores both a custom Convolutional Neural Network (CNN) and a transfer learning approach using MobileNetV2.

---

## Dataset

* Wafer map images organized into multiple defect classes:

  * Center
  * Donut
  * Edge Local
  * Edge Ring
  * Local
  * Scratch
  * Near Full
  * None
  * Random

* Images are loaded using TensorFlow's `image_dataset_from_directory`.

---

## Methodology

### 1. Data Preprocessing

* Image resizing to 256×256
* Normalization (pixel values scaled to [0,1])
* Data augmentation:

  * Random flipping
  * Random rotation

---

### 2. Custom CNN Model

A simple CNN architecture was implemented:

* Multiple Conv2D + MaxPooling layers
* Fully connected layers
* Dropout for regularization

This model was trained from scratch on wafer data.

---

### 3. Transfer Learning (MobileNetV2)

* Pretrained MobileNetV2 used as feature extractor
* Base model frozen
* Custom classification head added

---

## Results

### Custom CNN

* Accuracy: ~94%
* Strong performance across most defect classes
* Minor confusion between visually similar classes (Local vs Scratch)

### Transfer Learning (MobileNetV2)

* Accuracy: ~84%
* Lower performance due to domain mismatch between natural images and wafer patterns

---

## Evaluation

### Confusion Matrix

* Most predictions lie along the diagonal
* Indicates strong classification performance
* Errors mainly occur between similar defect patterns

### Classification Report

* High precision and recall for most classes
* Lower recall observed for:

  * Center defects
* Confusion between:

  * Local and Scratch defects

---

## Key Insights

* Custom CNN outperformed transfer learning due to domain-specific feature learning
* Transfer learning is not always effective when source and target domains differ significantly
* Model errors are interpretable and aligned with visual similarity between defect types

---

## Technologies Used

* Python
* TensorFlow / Keras
* NumPy
* Matplotlib
* Scikit-learn

---

## Future Work

* Fine-tuning pretrained models instead of freezing completely
* Increasing dataset size for underperforming classes
* Applying advanced augmentation techniques
* Exploring anomaly detection approaches for rare defects

---

## Conclusion

The project demonstrates that deep learning can effectively classify wafer defects with high accuracy. A custom CNN model proved more suitable than transfer learning due to the specialized nature of wafer data.

---

## Author

Vaibhav Sharma
MTech, IIT Hyderabad
Semiconductor Materials and Devices
