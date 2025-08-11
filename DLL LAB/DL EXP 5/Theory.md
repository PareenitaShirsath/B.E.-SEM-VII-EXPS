# Deep Neural Network (DNN) Theory

A **Deep Neural Network (DNN)** is an artificial neural network with multiple hidden layers between the input and output layers.  
It can model complex, non-linear relationships between inputs and outputs, making it suitable for classification, regression, and other prediction tasks.

---

## 1. Structure of a DNN

A DNN typically consists of:

- **Input Layer**:  
  Receives the feature vectors from the dataset.

- **Hidden Layers**:  
  Perform transformations and extract complex patterns using activation functions  
  (e.g., ReLU, tanh, sigmoid).

- **Output Layer**:  
  Produces classification probabilities or predicted labels.

---

## 2. Key Concepts

### **Fully Connected Layer (Dense Layer)**
- Every neuron in the layer is connected to every neuron in the previous layer.

### **Activation Functions**
- **ReLU (Rectified Linear Unit)**:  
  \( f(x) = \max(0, x) \)  
  Helps reduce the vanishing gradient problem.

- **Softmax**:  
  Converts raw scores into probabilities for multi-class classification.

### **Loss Function**
- **Categorical Cross-Entropy Loss** is widely used for classification tasks:  
  Measures the difference between predicted probability distribution and the true distribution.

### **Optimization Algorithm**
- **Adam Optimizer**:  
  Adaptive learning rate and momentum features make it effective for faster convergence.

---

## 3. Training Process

1. **Forward Propagation**: Compute output predictions.
2. **Loss Calculation**: Compare predictions with actual labels.
3. **Backpropagation**: Compute gradients and update weights.
4. **Iteration/Epochs**: Repeat until convergence.

---

## Conclusion
Deep Neural Networks are powerful tools for modeling complex relationships in data.  
By combining multiple layers, activation functions, and optimization techniques, DNNs can effectively perform tasks such as classification, regression, and prediction across various domains.
