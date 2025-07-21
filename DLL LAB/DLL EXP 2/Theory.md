# Implementing Multilayer Perceptron to Simulate XOR Gate

---

## Aim
To implement a **Multilayer Perceptron (MLP)** algorithm using TensorFlow/Keras that simulates the behavior of the **XOR logic gate**.

---

## Theory

### What is a Multilayer Perceptron (MLP)?

- An MLP is a type of **feedforward artificial neural network**.
- It contains multiple layers:
  - **Input layer**
  - **One or more hidden layers**
  - **Output layer**
- Each layer consists of neurons connected by weighted edges.
- MLPs can learn **nonlinear decision boundaries** by applying **activation functions** in hidden layers.
- This ability allows MLPs to solve problems that are **not linearly separable**.

### XOR Gate Problem

| Input A | Input B | XOR Output (A ⊕ B) |
|---------|---------|--------------------|
| 0       | 0       | 0                  |
| 0       | 1       | 1                  |
| 1       | 0       | 1                  |
| 1       | 1       | 0                  |

- The XOR function outputs true only when inputs differ.
- It is **not linearly separable**, meaning a single-layer perceptron cannot model it.
- A neural network requires at least **one hidden layer with nonlinear activation** to learn XOR.

---

## Code Explanation and Implementation

```python
import os
os.environ['TF_CPP_MIN_LOG_LEVEL'] = '2'  # Suppress TensorFlow info/debug logs

import numpy as np
import tensorflow as tf
from tensorflow.keras.models import Sequential
from tensorflow.keras.layers import Dense, Input

# 1. Define XOR input and output data
X = np.array([[0, 0], [0, 1], [1, 0], [1, 1]])
y = np.array([[0], [1], [1], [0]])

# 2. Build the MLP model
model = Sequential([
    Input(shape=(2,)),            # Input layer with 2 features
    Dense(2, activation='relu'),  # Hidden layer: 2 neurons with ReLU activation
    Dense(1, activation='sigmoid') # Output layer: 1 neuron with sigmoid activation
])

# 3. Compile the model
model.compile(optimizer='adam', loss='binary_crossentropy', metrics=['accuracy'])

# 4. Train the model
model.fit(X, y, epochs=5000, verbose=0)

# 5. Evaluate the model
loss, accuracy = model.evaluate(X, y, verbose=0)
print(f"Loss: {loss}, Accuracy: {accuracy}")

# 6. Make predictions
predictions = model.predict(X)
print("Predictions:")
print(predictions.round())

# Explanation of Key Code Components

---

### `os.environ['TF_CPP_MIN_LOG_LEVEL'] = '2'`

- Configures TensorFlow to suppress less important log messages (INFO and DEBUG), showing only warnings and errors.
- Helps keep the output clean during execution.

---

### `np.array()`

- Converts Python lists into NumPy arrays, which are efficient structures for numerical operations.
- Used here to store input features (`X`) and labels (`y`).

---

### `Sequential`

- A Keras class to build neural networks layer-by-layer.
- It stacks layers in a linear sequence where the output of one layer is the input to the next.

---

### `Input(shape=(2,))`

- Defines the input layer shape.
- `(2,)` means each input sample has 2 features (e.g., two bits for XOR).

---

### `Dense(units, activation)`

- Adds a fully connected layer with:
  - **`units`**: number of neurons.
  - **`activation`**: activation function for introducing non-linearity.
- `relu` activation outputs zero for negative inputs and passes positive inputs unchanged.
- `sigmoid` squashes output between 0 and 1, useful for binary outputs.

---

### `model.compile()`

- Prepares the model for training by specifying:
  - **`optimizer`**: Algorithm to update weights (Adam is an efficient optimizer).
  - **`loss`**: Function to measure how far predictions are from true labels (`binary_crossentropy` for binary classification).
  - **`metrics`**: What performance metrics to track (e.g., accuracy).

---

### `model.fit(X, y, epochs=5000, verbose=0)`

- Trains the model on data `X` with labels `y`.
- `epochs=5000`: Number of full passes over the training data.
- `verbose=0`: Suppresses the training progress output.

---

### `model.evaluate(X, y, verbose=0)`

- Tests the model on the given data.
- Returns loss and accuracy metrics.
- `verbose=0`: Runs silently without printing progress.

---

### `model.predict(X)`

- Uses the trained model to predict outputs for inputs `X`.
- Returns probabilities, which are then rounded to 0 or 1.

---

### `.round()`

- Rounds the predicted probabilities to the nearest integer (0 or 1), converting probabilities into binary predictions.

---

