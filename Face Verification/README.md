# Face Verification System (Same Person or Not)

## Overview
This project implements a face verification system that determines whether two input images belong to the same person.

It uses a pre-trained FaceNet model to extract facial embeddings and compares them using distance metrics.

## Approach

The pipeline follows these steps:

1. Load input images  
2. Detect faces using MTCNN  
3. Crop detected faces  
4. Resize faces to the required input size  
5. Generate embeddings using FaceNet  
6. Compute similarity (Euclidean distance)  
7. Compare against a threshold to decide if faces match  

## Model & Techniques

- **Face Detection:** MTCNN  
- **Feature Extraction:** FaceNet (pre-trained)  
- **Similarity Metric:** Euclidean Distance  

## Key Features

- Detects faces automatically from images  
- Converts faces into embeddings (numerical representations)  
- Compares faces using distance threshold  
- Simple and interpretable decision logic  

## Example Logic

- If distance < threshold → Same person  
- If distance ≥ threshold → Different persons  

## Tools & Libraries

- Python  
- NumPy  
- OpenCV  
- Matplotlib  
- keras-facenet  
- MTCNN  

## Project Structure

- Single Jupyter Notebook:
  - Face detection
  - Preprocessing
  - Embedding generation
  - Face comparison

## Conclusion

This project demonstrates a simple yet effective face verification pipeline using deep learning embeddings.

It highlights how pre-trained models can be leveraged to build real-world computer vision applications with minimal training effort.