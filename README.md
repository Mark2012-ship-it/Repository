# Real-Time Age Estimation from Camera Feed

## Project Overview

This project uses a trained deep learning model to estimate a person's **age range** in real time using a live camera feed. The system processes frames from a webcam, detects faces, and classifies each face into an age group such as **0–9, 10–19, 20–29**, and so on.

The model was trained on a dataset of **over 20,000 facial images** and achieves an average classification accuracy of approximately **63%**.

---

# What the Project Looks Like

When the project is running, a real-time camera window opens displaying the live video feed from the connected camera.

As faces appear in the frame, the system:

- Detects each face and draws a bounding box around it.
- Predicts the person's age range (0–9, 10–19, 20–29, etc.).
- Displays the predicted age group above the detected face.
- Shows a confidence score indicating how certain the model is about its prediction.
- Displays probability bars for every age category, allowing users to see how likely each age group is before the final prediction is made.

### Screenshot

![Project Screenshot](https://cdn.phototourl.com/free/2026-07-02-23d0030b-48f8-493a-8251-809ac2da7c64.png)

---

# The Algorithm

This project uses a **Convolutional Neural Network (CNN)** to classify facial images into predefined age ranges.

## 1. Dataset Preparation

The training dataset contained over **20,000 facial images**.

Before training, the dataset was organized into age groups including:

- 0–9
- 10–19
- 20–29
- 30–39
- 40–49
- 50+

A significant portion of the project involved sorting every image into the correct age group. AI-assisted tools were used to speed up the labeling process before the data was reviewed for consistency.

## 2. Frame Capture

The application continuously captures frames from a live webcam using **OpenCV**.

## 3. Face Detection

Each frame is analyzed to detect faces. Once a face is found, it is cropped from the image for processing.

## 4. Image Preprocessing

Each detected face is:

- Resized to the required input dimensions
- Normalized for consistent model performance

## 5. Age Group Prediction

The processed image is passed through the trained CNN.

The model predicts which age range the face belongs to based on features learned during training.

## 6. Output

The predicted age group is displayed directly on the live video feed along with confidence information and probability bars for every age category.

---

# Technologies Used

- Python
- OpenCV
- TensorFlow
- NumPy
- NVIDIA Jetson Inference

---

# Model Performance

- **Training Dataset:** 20,000+ facial images
- **Prediction Type:** Age Range Classification
- **Average Accuracy:** ~63%

---

# Running This Project

## 1. Download the Dataset

Download the dataset from Kaggle.

Example:

```bash
curl -L -o dataset.zip <dataset-url>
```

Extract the dataset:

```bash
unzip dataset.zip
```

---

## 2. Organize the Dataset

Sort all images into their respective age-group folders (0–9, 10–19, 20–29, etc.) before training.

---

## 3. Train the Model

Run the training script:

```bash
python train.py
```

This trains and validates the CNN and produces the model used for inference.

---

## 4. Connect the Camera

Connect a USB or CSI camera to the NVIDIA Jetson device and ensure it is recognized by the system.

---

## 5. Run Real-Time Age Estimation

Launch the application:

```bash
python main.py
```

The application will:

- Open the live camera feed
- Detect faces
- Predict the age range for each detected face
- Display the results in real time

---

# Video Demonstration

Watch the project in action:

https://www.image2url.com/r2/default/videos/1783018431920-f0a3e7c9-52bc-4adf-9cf4-b91e5442d2e1.mp4