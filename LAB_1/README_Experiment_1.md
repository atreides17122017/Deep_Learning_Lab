# Experiment 1 — Single Layer Perceptron

## Objective
Implement a **Single Layer Perceptron from scratch** and understand how a basic artificial neuron performs binary classification.

## What I Did
- Explored the **Banknote Authentication Dataset**.
- Performed basic EDA using histograms, a correlation heatmap, scatter plot and boxplots.
- Normalized the numerical features.
- Split the data into **80% training** and **20% testing**.
- Implemented the perceptron manually using:
  - weights
  - bias
  - step activation
  - perceptron learning rule
- Tracked training error, weights and bias across epochs.
- Evaluated the model using accuracy, precision, recall, F1-score and a confusion matrix.
- Compared different learning rates.
- Also studied the perceptron on AND, OR, NOT and XOR logic gates.

## Dataset
**Banknote Authentication Dataset**
- Samples: **1,372**
- Features: **4**
- Classes: **2**
- Features: Variance, Skewness, Curtosis, Entropy
- `0` → Authentic
- `1` → Forged

## Perceptron
The perceptron calculates:

`z = wᵀx + b`

and applies a step function:

- `1` if `z ≥ 0`
- `0` if `z < 0`

When a prediction is wrong, the weights and bias are updated using the perceptron learning rule.

## Key Results
- **Test Accuracy: 98.18%**
- All **148 authentic** banknotes were correctly classified.
- **5 forged** banknotes were classified as authentic.
- Learning rate **0.01** gave a good balance between convergence speed and stable learning.
- The weights and bias gradually stabilized during training.

## Important Observation
The Banknote Authentication dataset is approximately **linearly separable**, making it a good problem for a Single Layer Perceptron.

The logic-gate experiment also showed the main limitation of the perceptron:
- AND → solvable
- OR → solvable
- NOT → solvable
- XOR → **not solvable by a single-layer perceptron**

## Technologies
- Python
- NumPy
- Pandas
- Matplotlib
- Seaborn
- Scikit-learn

## Takeaway
This experiment builds the foundation for neural networks by showing how a single artificial neuron learns a decision boundary. It also demonstrates why **multiple layers and non-linear activation functions** are needed for more complex problems.
