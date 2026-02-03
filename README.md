# DL-TrashNet 🗑️♻️

A deep learning project for waste classification using the three datasets with various data augmentation techniques and ResNet-50 architecture.

## 📖 About

This project implements an intelligent trash classification system using convolutional neural networks (CNNs) to automatically categorize waste into different recycling categories. The system uses transfer learning with ResNet-50 and explores how data augmentation improves model generalization and robustness.

## 📊 Dataset

To overcome the limitations of small-scale datasets, this project utilizes a **Unified Dataset** constructed by merging three distinct open-source repositories. This combination creates a robust, diverse dataset of approximately **14,000 images**, ensuring better generalization and minimizing overfitting.

**Data Sources:**
1. [TrashNet](https://www.kaggle.com/datasets/feyzazkefe/trashnet)
2. [Garbage Classification](https://www.kaggle.com/datasets/mostafaabla/garbage-classification)
3. [Garbage Classification V2](https://www.kaggle.com/datasets/sumn2u/garbage-classification-v2?resource=download)

| **Final Class**
| 🟫 Cardboard
| 🔵 Glass
| ⚙️ Metal
| 📄 Paper
| 🟣 Plastic

### 📊 Final Split Strategy

- **Training:** 70%
- **Validation:** 15%
- **Testing:** 15%

## 📝 Implementation Details

**Transfer Learning Strategy:**
- Use ImageNet pretrained ResNet-50 weights
- Replace final FC layer for 5-class classification
- Add dropout (0.5) for regularization
- Train with Adam optimizer and learning rate scheduling

**Data Split Strategy:**
- 70% Training | 15% Validation | 15% Test
- Fixed random seed (42) for reproducibility
- Augmentation only on training data

**Early Stopping:**
- Monitor validation loss with patience=4
- Save best model based on validation accuracy
  
## 🏗️ Project Structure

```
DL-TrashNet/
├── notebooks/
│   ├── 01_baseline_resnet.ipynb          # Baseline model (basic preprocessing)
│   ├── 02_augmented_resnet.ipynb         # Augmented model (advanced techniques)
│   └── 03_cutmix_resnet.ipynb            # Augmented model with cutmix
├── plots/                                # Training curves & visualizations
├── results/                              # Model metrics & statistics
└── README.md
```

## 📄 License

This project is open source and available for educational and research purposes.
