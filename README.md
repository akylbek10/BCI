# EEG Motor Imagery Classification Project

## 🚀 Project Overview
This project focuses on the classification of Motor Imagery (MI) signals from the **BCI Competition IV-2a dataset**. The goal is to translate brain activity associated with imagined movements (Left Hand, Right Hand, Feet, and Tongue) into control signals, enabling BCI-based communication and control.

## 🧠 Methodology & Approaches
During the development process, we explored several state-of-the-art architectures and signal processing techniques:

### 1. Deep Learning: EEGNet
- **Architecture**: Implemented a specialized Convolutional Neural Network (EEGNet) designed specifically for EEG signals.
- **Features**: Utilized depthwise and separable convolutions to extract spatial and temporal features efficiently while maintaining a low parameter count.
- **Outcome**: Achieved significant improvements in capturing complex non-linear patterns in brain waves.

### 2. Signal Processing: FB-CSP (Filter Bank Common Spatial Patterns)
- **Filtering**: Applied multiple band-pass filters (4-8Hz, 8-12Hz, 12-16Hz, 16-30Hz) to isolate key frequency bands (Theta, Alpha, Beta).
- **Feature Extraction**: Used Common Spatial Patterns (CSP) to find spatial filters that maximize the variance between classes, followed by Linear Discriminant Analysis (LDA) for classification.
- **Outcome**: This classical approach provided a strong baseline for spatial feature discrimination.

### 3. Machine Learning Baseline
- **Pre-processing**: Data was segmented into epochs, normalized, and cleaned of artifacts using Notch and Band-pass filtering.
- **Models**: Evaluated Random Forest and SVM classifiers using handcrafted features like spectral entropy, Hjorth parameters (mobility, complexity), and power spectral density (PSD).

## 🛠️ Tech Stack
- **Languages**: Python
- **Libraries**: 
    - `MNE-Python`: For specialized EEG signal processing.
    - `PyRiemann`: For Riemannian geometry-based covariance analysis.
    - `TensorFlow/Keras`: For deep learning model development.
    - `Scikit-learn`: For traditional ML models and evaluation metrics.
    - `Pandas/NumPy/Matplotlib`: For data wrangling and visualization.

## 📊 Results & Insights
- **Accuracy**: Demonstrated strong performance in multi-class classification, with CSP+LDA and EEGNet showing complementary strengths.
- **Data Handling**: Addressed challenges like class imbalance and non-finite value artifacts through robust preprocessing pipelines.

## 🎯 Future Scope
- Integration with real-time EEG hardware (e.g., OpenBCI).
- Implementation of Transfer Learning to reduce calibration time for new users.
- Exploring Transformers (Attention mechanisms) for better temporal modeling.
