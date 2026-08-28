# Experiment 3 — Convolutional Neural Network (CNN)

##Objective
Understand and implement the core components of a **Convolutional Neural Network** for image classification using CIFAR-10.

## What I Did
- Loaded and explored CIFAR-10.
- Normalized image pixels to `[0, 1]`.
- Split the original training data into:
  - **45,000 training images**
  - **5,000 validation images**
- Kept **10,000 test images** for final evaluation.
- Studied different convolution kernels.
- Compared kernel sizes: `3 × 3`, `5 × 5`, `7 × 7`.
- Studied stride and padding.
- Visualized feature maps.
- Compared **Max Pooling** and **Average Pooling**.
- Built and trained a CNN.
- Evaluated the model using accuracy, precision, recall, F1-score and a confusion matrix.

## Dataset
**CIFAR-10**
- Training images: **50,000**
- Testing images: **10,000**
- Classes: **10**
- Image size: **32 × 32 × 3**

Classes:
`Airplane, Automobile, Bird, Cat, Deer, Dog, Frog, Horse, Ship, Truck`

## CNN Architecture

```text
Input
  ↓
Convolution
  ↓
ReLU
  ↓
Max Pooling
  ↓
Convolution
  ↓
ReLU
  ↓
Max Pooling
  ↓
Flatten
  ↓
Dense
  ↓
Softmax
```

### Training
- Optimizer: **Adam**
- Epochs: **20**
- Batch size: **32**

##Convolution Experiments
Different kernels were studied to understand how convolution extracts visual features such as:
- edges
- textures
- shapes
- boundaries

Feature-map visualizations showed that early convolution layers learn simpler patterns such as edges and textures.

## Pooling
Both pooling methods were compared:
- Max Pooling
- Average Pooling

**Max pooling slightly outperformed average pooling** in the experiment.

## Key Results
- **Final Test Accuracy: 71.32%**
- **Weighted F1-score: 71.49%**
- `3 × 3` convolution performed better than the tested `5 × 5` and `7 × 7` alternatives.
- ReLU performed substantially better than Sigmoid.
- Increasing the number of filters improved accuracy, but also increased computational cost.

## Important Observations
CNNs are more suitable than a plain MLP for images because convolution:
- uses **local connectivity**
- shares weights across the image
- preserves spatial structure
- learns hierarchical visual features

This allows the network to learn useful image patterns without manually designing features.

## Technologies
- Python
- TensorFlow / Keras
- NumPy
- Pandas
- Matplotlib
- Scikit-learn

## Takeaway
This experiment demonstrates the complete CNN workflow, from convolution and pooling to feature-map visualization and image classification. It shows why CNNs are a natural choice for computer vision tasks.
