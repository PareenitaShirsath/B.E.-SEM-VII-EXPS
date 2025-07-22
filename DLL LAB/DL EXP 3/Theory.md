# Deep Neural Network (DNN) Training with Backpropagation

## Aim
Implement a backpropagation algorithm to train a Deep Neural Network (DNN) with at least 2 hidden layers for handwritten digit classification using the MNIST dataset.

## Theory

### Deep Neural Network (DNN)
A Deep Neural Network is an artificial neural network with multiple layers between the input and output layers. It consists of:
- **Input layer:** Receives the input features.
- **Hidden layers:** Intermediate layers where neurons learn complex representations.
- **Output layer:** Produces the final prediction or classification.

In this implementation, the DNN has:
- Two hidden layers (with 128 and 64 neurons respectively).
- An output layer with 10 neurons corresponding to the 10 digit classes (0-9).

### Activation Functions
- **ReLU (Rectified Linear Unit):** Used in hidden layers to introduce non-linearity by outputting zero if input is negative, otherwise outputting input directly.
- **Softmax:** Used in the output layer for multi-class classification; it converts raw output scores into probabilities summing to 1.

### Backpropagation Algorithm
Backpropagation is a supervised learning algorithm used to train neural networks by minimizing the error between predicted output and true output (labels). It involves:

1. **Forward pass:**  
   The input data passes through the network, layer by layer, to produce an output.

2. **Loss calculation:**  
   Compute the error between the predicted output and actual target using a loss function (e.g., cross-entropy loss for classification).

3. **Backward pass:**  
   Using the chain rule of calculus, gradients of the loss with respect to weights are calculated from the output layer back to the input layer.

4. **Weight update:**  
   Weights are updated using gradient descent or its variants (like Adam optimizer), adjusting them to reduce the loss.

### Training Process
- The model is trained using the **Adam optimizer**, an adaptive learning rate optimization algorithm.
- **Sparse categorical cross-entropy loss** is used for multi-class classification.
- The dataset used is **MNIST**, a widely used dataset of 28x28 grayscale images of handwritten digits.
- The images are flattened into 784-length vectors and normalized to improve training efficiency.

### Summary
Training the DNN involves iteratively performing forward and backward passes, adjusting weights through backpropagation, allowing the network to learn features that map input images to digit labels with high accuracy.

---

## References
- [Deep Learning Book by Ian Goodfellow](https://www.deeplearningbook.org/)
- [TensorFlow Documentation](https://www.tensorflow.org/)
- [MNIST Dataset](http://yann.lecun.com/exdb/mnist/)


