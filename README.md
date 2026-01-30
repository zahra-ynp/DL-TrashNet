# DL-TrashNet 🗑️♻️

A deep learning project for waste classification using the TrashNet dataset with various data augmentation techniques and ResNet-50 architecture.

## 📖 About

This project implements an intelligent trash classification system using convolutional neural networks (CNNs) to automatically categorize waste into different recycling categories. The system uses transfer learning with ResNet-50 and explores how data augmentation improves model generalization and robustness.

## 📊 Dataset

This project uses the [TrashNet Dataset](https://www.kaggle.com/datasets/feyzazkefe/trashnet) from Kaggle.

**Classes (6 categories):**
- 🟫 Cardboard
- 🔵 Glass
- ⚙️ Metal
- 📄 Paper
- 🟣 Plastic
- 🗑️ Trash

**Dataset Size:** 2,527 images (70% train, 15% val, 15% test)

## 📝 Implementation Details

**Transfer Learning Strategy:**
- Use ImageNet pretrained ResNet-50 weights
- Replace final FC layer for 6-class classification
- Add dropout (0.5) for regularization
- Train with Adam optimizer and learning rate scheduling

**Data Split Strategy:**
- 70% Training | 15% Validation | 15% Test
- Fixed random seed (42) for reproducibility
- Augmentation only on training data

**Early Stopping:**
- Monitor validation loss with patience=5
- Save best model based on validation accuracy
  
## 🏗️ Project Structure

```
DL-TrashNet/
├── notebooks/
│   ├── 01_baseline_resnet.ipynb          # Baseline model (basic preprocessing)
│   └── 02_augmented_resnet.ipynb         # Augmented model (advanced techniques)
├── dataset-resized/                      # Raw dataset
│   ├── cardboard/
│   ├── glass/
│   ├── metal/
│   ├── paper/
│   ├── plastic/
│   └── trash/
├── plots/                                # Training curves & visualizations
├── results/                              # Model metrics & statistics
└── README.md
```

## 📄 License

This project is open source and available for educational and research purposes.
