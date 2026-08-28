# Experiment 4 — CNN Architectures & Transfer Learning

## 🎯 Objective
Study the evolution of important CNN architectures and compare their performance using **CIFAR-10**. The experiment also demonstrates **transfer learning and fine-tuning** using pretrained CNN models.

## 🧠 Architectures Studied

| Architecture | Main Idea |
|---|---|
| **LeNet-5** | Compact CNN for early image recognition |
| **AlexNet** | ReLU, dropout, data augmentation and GPU-based training |
| **VGG16** | Deep network using repeated `3 × 3` convolutions |
| **GoogleNet / Inception** | Multi-scale feature extraction using parallel operations |
| **ResNet** | Residual learning with skip connections |

## 📌 What I Did
- Studied the evolution of CNN architectures.
- Implemented and compared CNN models on CIFAR-10.
- Used ImageNet-pretrained **VGG16, InceptionV3 and ResNet50**.
- Initially froze pretrained convolutional layers.
- Added new classification heads for the 10 CIFAR-10 classes.
- Trained the classification heads.
- Fine-tuned selected pretrained layers.
- Compared accuracy, precision, recall, F1-score and training time.
- Studied dilated convolution and transpose convolution.

## 📊 Dataset
**CIFAR-10**
- Training images: **50,000**
- Testing images: **10,000**
- Classes: **10**
- Image size: **32 × 32 × 3**

For transfer learning, images were resized to **96 × 96** and converted to the preprocessing format expected by the pretrained models.

## 🔄 Transfer Learning Workflow

```text
ImageNet-pretrained CNN
          ↓
     Freeze base
          ↓
   Add classifier head
          ↓
     Train new head
          ↓
   Unfreeze selected layers
          ↓
      Fine-tune
          ↓
       Predict
```

## 🏆 Model Comparison

| Model | Parameters | Test Accuracy | Training Time |
|---|---:|---:|---:|
| LeNet-5 | 83,126 | 52.79% | 0.97 min |
| AlexNet-style | 3,369,802 | 70.24% | 3.08 min |
| VGG16 | 14,781,642 | 82.48% | 7.70 min |
| InceptionV3 | 22,066,346 | 69.12% | 2.52 min |
| **ResNet50** | **23,851,274** | **91.71%** | **10.53 min** |

### 🥇 Best Model
**ResNet50 achieved the highest test accuracy: 91.71%.**

It also required the most training time among the compared models.

## 🔧 Fine-Tuning Results

### VGG16
- Frozen best validation accuracy: **82.06%**
- Fine-tuned best validation accuracy: **83.38%**
- Test accuracy: **82.48%**
- Weighted F1-score: **82.43%**

Fine-tuning improved validation accuracy by **1.32 percentage points**.

### ResNet50
- Frozen best validation accuracy: **87.68%**
- Fine-tuned best validation accuracy: **92.08%**
- Test accuracy: **91.71%**

The last **30 layers** were unfrozen and fine-tuned using a learning rate of `0.0001`.

Fine-tuning improved validation accuracy by **4.40 percentage points**.

## 🔍 Class-wise Observation
For the final VGG16 model:
- **Automobile** and **Ship** were among the strongest classes, both with F1-score **0.89**.
- **Cat** was the most difficult class, with F1-score **0.70**.

## ⚡ Other Concepts Studied

### Dilated Convolution
Expands the receptive field without proportionally increasing the number of kernel parameters.

### Transpose Convolution
A learnable upsampling operation used when spatial dimensions need to be increased.

### Residual Learning
ResNet learns a residual mapping:

`Output = F(x) + x`

Skip connections provide a direct path for information and gradients, making very deep networks easier to optimize.

## 🛠️ Technologies
- Python
- TensorFlow / Keras
- NumPy
- Pandas
- Matplotlib
- Scikit-learn

## 💡 Takeaway
This experiment shows how CNN architectures evolved from small networks such as LeNet to very deep networks such as ResNet. The results demonstrate that **architecture, depth, preprocessing and transfer learning all strongly affect performance**.

In this experiment, **ResNet50 + transfer learning + fine-tuning gave the best overall result**, reaching **91.71% test accuracy**.
