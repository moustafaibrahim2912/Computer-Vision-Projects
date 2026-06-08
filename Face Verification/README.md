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

## Benchmark Evaluation (LFW Dataset)

To objectively evaluate the system beyond manually selected images, the pipeline was tested on the official **Labeled Faces in the Wild (LFW)** benchmark — a standard dataset for face verification containing 1,000 pairs (500 matched, 500 mismatched).

| Metric | Value |
|--------|-------|
| Pairs Evaluated | 1,000 |
| Threshold | 0.85 |
| Accuracy | 90.70% |
| FAR (False Accept Rate) | 0.00% |
| FRR (False Reject Rate) | 18.60% |

**FAR = 0%** means the system never falsely matched two different people — a critical property for identity verification use cases.  
The conservative threshold (0.85) prioritizes security over recall, which explains the higher FRR.

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
  - LFW benchmark evaluation
## Conclusion

This project demonstrates a simple yet effective face verification pipeline using deep learning embeddings.

It highlights how pre-trained models can be leveraged to build real-world computer vision applications with minimal training effort.