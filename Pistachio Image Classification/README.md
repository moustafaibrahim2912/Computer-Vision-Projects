# Pistachio Image Classification System

## Overview
This project implements an end-to-end computer vision pipeline to classify pistachio images into their respective varieties. 

It builds and trains a custom Convolutional Neural Network (CNN) using TensorFlow and Keras to accurately automate variety identification, handling the challenges of high visual similarity between classes.

## Dataset
The dataset contains images of pistachio nuts divided into two distinct species classes.

### Data Challenges & Processing
- High structural similarity between classes
- Variation in lighting, orientation, and zoom levels
- Risks of deep-learning overfitting on limited image variants

To address these challenges, the dataset is loaded programmatically using dynamic directory sequencing, sizing images to **128x128 pixels** with a batch size of 32. A **20% validation split** is maintained to track performance reliably.

## Pipeline

1. Data loading and automated directory parsing
2. Real-time target-image resizing and optimization
3. On-the-fly pixel scaling and data augmentation
4. CNN compilation and regulated model training with Early Stopping
5. Post-training evaluation via confusion matrix and precision metrics

## Modeling & Evaluation

A custom sequential deep-learning architecture was developed using the following structural layers:
- **Data Augmentation:** Integrated layers for `RandomFlip("horizontal")`, `RandomRotation(0.1)`, and `RandomZoom(0.1)` to boost generalization capacity.
- **Normalization:** `Rescaling(1.0 / 255)` layer to standardize input feature spaces.
- **Feature Extraction:** Three sequential Convolutional blocks (`Conv2D` with 32, 64, and 128 filters utilizing `relu` activations) coupled with `MaxPooling2D` layers.
- **Classification Head:** A `Flatten` layer leading to a 128-unit `Dense` hidden layer with `Dropout(0.5)` for regularization, ending with a 2-unit `softmax` output layer.

### Performance & Metrics
- The network was compiled using the `adam` optimizer and `sparse_categorical_crossentropy` loss.
- Regulated via `EarlyStopping` monitoring validation loss with a patience of 8 epochs.
- Achieved a highly robust final **Validation Accuracy of 95.10%**.

**Classification Breakdown:**
- **Kirmizi_Pistachio:** Precision: 0.95 | Recall: 0.96 | F1-Score: 0.96
- **Siirt_Pistachio:** Precision: 0.95 | Recall: 0.94 | F1-Score: 0.95

## Model Capabilities

- Binary image classification across highly similar biological structures
- Real-time internal data augmentation to mitigate overfitting
- Regularized dropout layers protecting performance validity on unseen files
- Comprehensive matrix-based classification reporting for evaluation tracking

## Tools & Technologies

- Python
- TensorFlow / Keras
- NumPy
- Scikit-learn (Metrics)
- Seaborn / Matplotlib
- Jupyter Notebook

## Conclusion

This project demonstrates the effective building of a customized Convolutional Neural Network capable of robust image verification without relying on heavy external checkpoints. 

It highlights the critical impact of:
- Strategic image augmentation inside the data pipeline
- Gradual feature-map expansion (32 ➔ 64 ➔ 128)
- Using early stopping parameters to capture optimized weight allocations

The system yields a clean, high-performance solution ready for integration into automated sorting and quality control agricultural applications.