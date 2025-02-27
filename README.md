# 🚀 Lightweight ResNet for CIFAR-10
🏆 Lightweight ResNet with ≤5M Parameters, optimized for CIFAR-10.

![Framework](results/model_architecture.png)

---

## 📖 Overview
This project focuses on designing a **lightweight ResNet** for **CIFAR-10**, ensuring:
- **≤5M parameters** for efficient inference.
- **Depthwise Separable Convolutions** for reduced computation.
- **Pruning & Quantization** for model compression.
- **Data Augmentation (Cutout, Mixup, Cutmix)** for improved generalization.

---

## **🔥 Experimental Results**
| Model Variant       | Parameters | Test Accuracy (%) |
|--------------------|------------|------------------|
| **Baseline ResNet-18** | 11.2M | 93.5% |
| **Lightweight ResNet (Ours)** | **3.5M** | **88.5%** |
| Lightweight ResNet + Pruning | 2.8M | 85.2% |
| Lightweight ResNet + Quantization | 1.5M | 83.7% |

📊 **Final Model Accuracy:** **88.5% on CIFAR-10**  
📉 **Reduced Parameters:** **From 11.2M → 3.5M (~68% reduction!)**  

---

## **⚡ Model Architecture**
The model is based on **ResNet**, but with **Depthwise Separable Convolutions** to reduce computation.
```plaintext
Input (3x32x32)
↓
Depthwise Separable Conv (3 → 32)
↓
Residual Block (32 → 64)
↓
Residual Block (64 → 128)
↓
Residual Block (128 → 256)
↓
Global Average Pooling
↓
Fully Connected (256 → 10)
↓
Softmax
