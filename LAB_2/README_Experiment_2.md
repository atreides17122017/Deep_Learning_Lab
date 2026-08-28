# Experiment 2 — Multi-Layer Perceptron (MLP)

## Objective
Build a **Multi-Layer Perceptron (MLP)** for multi-class image classification using the **Fashion-MNIST** dataset, then improve it using automated hyperparameter optimization.

## What I Did
- Loaded and explored Fashion-MNIST.
- Visualized sample images and class distribution.
- Flattened each `28 × 28` image into **784 features**.
- Normalized pixel values to `[0, 1]`.
- Built a baseline MLP.
- Trained it for 20 epochs.
- Evaluated it using accuracy, precision, recall, F1-score and a confusion matrix.
- Used **RandomizedSearchCV + SciKeras** with **5-fold cross-validation** to search for better hyperparameters.
- Retrained the model using the best configuration.
- Compared the baseline and optimized models.

## Dataset
**Fashion-MNIST**
- Training images: **60,000**
- Testing images: **10,000**
- Classes: **10**
- Image size: **28 × 28**

The ten classes represent clothing categories such as T-shirt/top, Trouser, Pullover, Dress, Coat, Sandal, Shirt, Sneaker, Bag and Ankle Boot.

##Baseline Architecture

```text
784
 ↓
Dense(128, ReLU)
 ↓
Dense(64, ReLU)
 ↓
Dense(10, Softmax)
```

The output layer uses **Softmax** because this is a 10-class classification problem.

## Hyperparameter Optimization
The search explored combinations of:
- Number of hidden layers
- Number of neurons
- Learning rate
- Batch size
- Epochs
- Optimizer
- Activation function
- Dropout

**RandomizedSearchCV** was used instead of checking every possible combination.

## Best Configuration
| Hyperparameter | Best Value |
|---|---|
| Hidden Layers | 3 |
| Hidden Neurons | 128 |
| Learning Rate | 0.001 |
| Batch Size | 32 |
| Optimizer | RMSProp |
| Activation | Tanh |
| Epochs | 30 |
| Dropout | 0.2 |

### Results
- Cross-validation accuracy: **89.018%**
- Baseline test accuracy: **88.12%**
- Optimized test accuracy: **88.55%**
- Optimized F1-score: **88.50%**

The optimized model showed a **small but measurable improvement** over the baseline.

## Observations
- Training accuracy increased steadily.
- Training loss decreased throughout training.
- Validation accuracy became more stable after the initial epochs.
- The confusion matrix showed most predictions along the diagonal.
- Some visually similar clothing classes, especially **Shirt, T-shirt/Top and Pullover**, were harder to distinguish.

## Technologies
- Python
- TensorFlow / Keras
- NumPy
- Pandas
- Matplotlib
- Scikit-learn
- SciKeras

## Takeaway
This experiment demonstrates how an MLP can learn useful representations from flattened images and how **hyperparameter tuning can improve model performance**. It also shows the limitation of treating an image as a flat vector, which motivates the use of CNNs.
