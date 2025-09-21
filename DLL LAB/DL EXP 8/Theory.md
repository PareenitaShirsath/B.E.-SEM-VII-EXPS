# Aim  
Design and implement a Convolutional Neural Network (CNN) model for handwritten digit recognition using the MNIST dataset.

---

# Theory  

## Introduction  
Handwritten digit recognition is one of the fundamental problems in computer vision and pattern recognition. It involves classifying grayscale images of handwritten digits (0–9) into their respective categories. The **MNIST dataset** is a standard benchmark dataset for this task, consisting of 60,000 training images and 10,000 testing images, each of size **28×28 pixels**.

## Convolutional Neural Networks (CNNs)  
CNNs are a class of deep neural networks specifically designed to process and learn features from image data. They reduce the need for manual feature extraction by automatically learning hierarchical feature representations.  

A typical CNN architecture includes:

1. **Convolutional Layer**  
   - Applies convolution operations to extract local features using filters (kernels).  
   - Captures spatial information such as edges, textures, and shapes.  

2. **Pooling (Subsampling) Layer**  
   - Reduces the spatial dimensions of feature maps.  
   - Provides translation invariance and reduces computational complexity.  
   - Common methods: Max Pooling, Average Pooling.  

3. **Flatten Layer**  
   - Converts 2D feature maps into a 1D vector, preparing them for fully connected layers.  

4. **Fully Connected Layers (Dense Layers)**  
   - Perform high-level reasoning and combine extracted features.  
   - Typically end with an output layer using **softmax activation** for classification.  

## LeNet-5 Architecture  
The model implemented here is inspired by **LeNet-5**, one of the earliest CNN architectures proposed by Yann LeCun. It was originally designed for handwritten digit recognition. Its structure includes:  

- Convolutional + Average Pooling layers  
- Another Convolutional + Average Pooling block  
- Fully Connected layers (120 → 84 → 10)  
- Softmax output for digit classification  

## Workflow of the Experiment  
1. **Data Preprocessing**  
   - Load MNIST dataset.  
   - Normalize pixel values (0–255 → 0–1).  
   - Reshape images to fit the CNN input requirements.  
   - Convert labels into one-hot encoding.  

2. **Model Building**  
   - Define CNN using TensorFlow/Keras.  
   - Use **tanh** activation for hidden layers and **softmax** for output.  

3. **Model Training**  
   - Compile with **Adam optimizer** and **categorical cross-entropy loss**.  
   - Train for multiple epochs with a batch size of 128.  

4. **Model Evaluation**  
   - Evaluate on the test dataset.  
   - Display accuracy and visualize sample predictions.  

## Applications  
- Optical Character Recognition (OCR).  
- Bank check digit verification.  
- Automatic number plate recognition.  
- Postal code sorting.  
