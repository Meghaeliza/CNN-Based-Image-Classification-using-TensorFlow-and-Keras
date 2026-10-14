# CNN-Based Image Classification using TensorFlow and Keras

## Project Overview

This project implements a **Convolutional Neural Network (CNN)** to classify natural scene images into six categories using the Intel Image Classification dataset.

The model was built using TensorFlow and Keras. It learns visual patterns from images to predict whether a scene belongs to one of the following classes:

- Buildings
- Forest
- Glacier
- Mountain
- Sea
- Street

The goal is to develop, train, and evaluate a CNN model and assess its performance using classification metrics and visualizations.

## Dataset

**Dataset:** Intel Image Classification  
**Source:** [Kaggle – Intel Image Classification](https://www.kaggle.com/datasets/puneet6060/intel-image-classification)

The dataset contains natural scene images organized into six classes.

| Dataset detail | Value |
|---|---|
| Training images | 14,034 |
| Testing images | 3,000 |
| Number of classes | 6 |
| Image dimensions | 150 × 150 pixels |
| Image channels | 3 (RGB) |

The training dataset was divided into training and validation subsets using an 80:20 split.

## Technologies Used

- Python
- TensorFlow
- Keras
- NumPy
- Matplotlib
- Scikit-learn
- KaggleHub
- Google Colab

## Data Preprocessing

The following preprocessing steps were performed:

1. Explored the dataset directory structure and class distribution.
2. Visualized sample images from the dataset.
3. Resized images to 150 × 150 pixels.
4. Normalized pixel values from the range 0–255 to 0–1.
5. Split the training data into training and validation subsets.
6. Applied data augmentation using horizontal flipping, random rotation, and random zoom.
7. Used dataset prefetching to improve input-processing efficiency.

## CNN Model Architecture

The CNN was developed from scratch using TensorFlow and Keras.

The architecture consists of:

1. Input layer for 150 × 150 RGB images.
2. Data augmentation layers.
3. Three convolutional layers with 32, 64, and 128 filters, respectively.
4. ReLU activation functions.
5. Max-pooling layers to reduce spatial dimensions.
6. Global average pooling layer.
7. Dense layer with 64 neurons and ReLU activation.
8. Dropout layer with a rate of 0.3 to help reduce overfitting.
9. Output layer with six neurons and softmax activation.

### Model Training

- **Optimizer:** Adam
- **Loss function:** Sparse categorical cross-entropy
- **Evaluation metric during training:** Accuracy
- **Maximum epochs:** 15
- **Early stopping:** Used to stop training when validation loss stopped improving.
- **Model checkpointing:** Used to save the best-performing model based on validation loss.

## Model Evaluation

The model was evaluated on the separate test dataset containing 3,000 images.

### Overall Results

| Metric | Score |
|---|---:|
| Test accuracy | 76.03% |
| Macro F1-score | 76.14% |
| Weighted F1-score | 75.86% |

### Class-wise Performance

| Class | Precision | Recall | F1-score |
|---|---:|---:|---:|
| Buildings | 65.79% | 80.09% | 72.24% |
| Forest | 97.53% | 91.56% | 94.45% |
| Glacier | 85.84% | 53.71% | 66.07% |
| Mountain | 73.84% | 72.57% | 73.20% |
| Sea | 66.62% | 85.69% | 74.96% |
| Street | 75.64% | 76.25% | 75.94% |

The forest class achieved the highest F1-score, while the glacier class had the lowest recall. This indicates that the model performs well on some scene categories but has difficulty correctly identifying certain glacier images.

## Visualizations

The project includes visualizations to understand the model's behavior:

- Sample images from the dataset.
- Training and validation accuracy curves.
- Training and validation loss curves.
- Confusion matrix for the test dataset.
- Ten randomly selected test images showing actual labels, predicted labels, and prediction confidence.

## Results and Conclusion

The CNN achieved **76.03% test accuracy** on the Intel Image Classification dataset. The results demonstrate that a CNN trained from scratch can learn useful visual features for natural scene classification.

Performance varied across classes, with particularly strong results for forest images and lower recall for glacier images. Potential improvements include experimenting with deeper architectures, tuning hyperparameters, refining data augmentation, and using transfer learning with pretrained CNN models.

## How to Run the Project

1. Open the Jupyter Notebook in Google Colab.
2. Install or import the required libraries.
3. Download the dataset using KaggleHub or configure the dataset path.
4. Run the notebook cells sequentially to preprocess the data, build the model, train it, and evaluate its performance.
5. Review the evaluation metrics and visualizations.



This project was completed as part of a Deep Learning assignment.

