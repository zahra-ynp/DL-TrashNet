# DL-TrashNet 🗑️♻️

A deep learning project for waste classification using three merged datasets with various data augmentation techniques and ResNet-50 architecture. The model is validated on real-world images using the TACO dataset and includes explainability analysis through Grad-CAM visualization.

## 📖 About

This project implements an intelligent trash classification system using convolutional neural networks (CNNs) to automatically categorize waste into different recycling categories. The system uses transfer learning with ResNet-50 and explores how data augmentation improves model generalization and robustness.

**Key Features:**
- Transfer learning with ResNet-50 architecture
- Advanced data augmentation techniques including CutMix
- Real-world validation using the TACO dataset
- Model explainability through Grad-CAM heatmap visualizations

## 📊 Datasets

### Training Dataset

To overcome the limitations of small-scale datasets, this project utilizes a **Unified Dataset** constructed by merging three distinct open-source repositories. This combination creates a robust, diverse dataset of approximately **14,000 images**, ensuring better generalization and minimizing overfitting.

**Data Sources:**
1. [TrashNet](https://www.kaggle.com/datasets/feyzazkefe/trashnet)
2. [Garbage Classification](https://www.kaggle.com/datasets/mostafaabla/garbage-classification)
3. [Garbage Classification V2](https://www.kaggle.com/datasets/sumn2u/garbage-classification-v2?resource=download)

**Final Classes:**
| Class | Category |
|-------|----------|
| 🟫 | Cardboard |
| 🔵 | Glass |
| ⚙️ | Metal |
| 📄 | Paper |
| 🟣 | Plastic |

**Final Split Strategy:**
- **Training:** 60%
- **Validation:** 20%
- **Testing:** 20%

### Validation Dataset (Real-World Testing)

**[TACO](https://www.kaggle.com/datasets/kneroma/tacotrashdataset)**

To evaluate model performance on real-world scenarios, the best-performing models are tested on the TACO dataset, which contains images of litter captured in diverse natural environments.

## 📝 Implementation Details

**Transfer Learning Strategy:**
- Use ImageNet pretrained ResNet-50 weights
- Replace final FC layer for 5-class classification
- Add dropout (0.5) for regularization
- Train with Adam optimizer and learning rate scheduling

**Data Augmentation Techniques:**
- Basic preprocessing (baseline)
- Advanced augmentation (rotation, flip, color jitter, etc.)
- CutMix augmentation

**Model Explainability:**
- GradCAM (Gradient-weighted Class Activation Mapping) visualizations
- Heatmap overlays showing which regions influence predictions
- Analysis on both original data and real-world TACO images

## 🏗️ Project Structure

```
DL-TrashNet/
├── notebooks/
│   ├── 01_baseline_resnet.ipynb          # Baseline model (basic preprocessing)
│   ├── 02_augmented_resnet.ipynb         # Augmented model (advanced techniques)
│   ├── 03_cutmix_resnet.ipynb            # Augmented model with CutMix
│   ├── 04_tacoTest.ipynb                 # Test best models on TACO dataset (real-world validation)
│   └── 05_explainability.ipynb           # Grad-CAM visualization on Original & TACO datasets
├── plots/                                 # Training curves & visualizations
├── results/                               # Model metrics & statistics
└── README.md
```

## 📄 License

This project is open source and available for educational and research purposes.
