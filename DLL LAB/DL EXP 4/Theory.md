# CSL701.2: Learning Algorithms for Single Layer Feedforward Neural Network

## Aim
Apply any of the following learning algorithms to learn the parameters of the supervised single-layer feedforward neural network:  
a. Stochastic Gradient Descent (SGD)  
b. Mini Batch Gradient Descent (MBGD)  
c. Momentum Gradient Descent (Momentum GD)  
d. Nesterov Gradient Descent (Nesterov GD)  
e. Adagrad Gradient Descent (Adagrad GD)  
f. Adam Learning Gradient Descent (Adam GD)  

---

## Theory

### 1. Stochastic Gradient Descent (SGD)
SGD updates the model parameters using the gradient computed from **each individual training example**. This often introduces noise in the gradient updates but allows faster convergence and can escape shallow local minima.

**Pros:** Fast updates, can handle large datasets.  
**Cons:** Noisy updates, may require careful tuning of learning rate.

---

### 2. Mini Batch Gradient Descent (MBGD)
MBGD computes the gradient using a **small batch of samples** rather than the full dataset or single example. It balances the stability of batch gradient descent and the speed of SGD.

**Pros:** Efficient computation, stable convergence, utilizes vectorized operations.  
**Cons:** Requires tuning batch size.

---

### 3. Momentum Gradient Descent
Momentum adds a fraction of the previous update vector to the current update. This helps accelerate convergence, especially in directions of consistent gradient, and reduces oscillations.

**Update Rule:**  
\( v_t = \gamma v_{t-1} + \eta \nabla J(\theta) \)  
\( \theta = \theta - v_t \)  

where \( \gamma \) is momentum term (usually ~0.9).

**Pros:** Faster convergence, smooths updates.  
**Cons:** Requires setting momentum parameter.

---

### 4. Nesterov Accelerated Gradient (Nesterov GD)
Nesterov GD improves momentum by calculating the gradient **at the lookahead position** (current position plus momentum), resulting in more informed updates.

**Pros:** More accurate updates than momentum, faster convergence.  
**Cons:** Slightly more complex implementation.

---

### 5. Adagrad Gradient Descent
Adagrad adapts the learning rate for each parameter individually by scaling it inversely proportional to the square root of the sum of all historical squared gradients. It is well-suited for sparse data.

**Pros:** Automatically adjusts learning rate, no need for manual tuning.  
**Cons:** Learning rate decays aggressively, can stop learning prematurely.

---

### 6. Adam Optimizer
Adam combines momentum and adaptive learning rate ideas by maintaining moving averages of both gradients and their squared values, with bias correction for better estimates.

**Pros:** Fast convergence, adaptive learning rates, works well in practice.  
**Cons:** More hyperparameters to tune (β1, β2, learning rate).

---

## Conclusion

- **SGD and Mini-Batch GD** provide foundational gradient descent techniques with trade-offs between update speed and stability.
- **Momentum and Nesterov GD** introduce momentum to accelerate and stabilize convergence, with Nesterov offering a predictive update improvement.
- **Adagrad** adapts learning rates based on past gradients, useful for sparse features but may lead to overly small learning rates.
- **Adam** combines the benefits of momentum and adaptive learning rates, often outperforming other methods in deep learning tasks.
  
Selecting an algorithm depends on dataset size, computational resources, and convergence speed requirements. For most modern neural network applications, **Adam optimizer** is preferred due to its robustness and efficiency.

---

**Note:** Proper hyperparameter tuning (learning rate, batch size, momentum coefficients) is critical for optimal performance in all these algorithms.

