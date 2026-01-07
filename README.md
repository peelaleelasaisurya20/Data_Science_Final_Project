# Heart Sound Classification: Jupyter Notebook Pipeline

## Overview
This Jupyter Notebook (`AAAAA Heart (2).ipynb`) implements a complete end-to-end deep learning pipeline for the classification of heart sounds. The primary goal is to differentiate between normal heart sounds and various types of cardiac murmurs using advanced audio processing and neural network architectures.

The notebook explores two main models:
1.  **CNN (Convolutional Neural Network)**: A 2D CNN that processes Mel-spectrogram images of heart sounds.
2.  **CRNN (Convolutional Recurrent Neural Network)**: A hybrid model that combines CNN layers for spatial feature extraction with **Bidirectional LSTMs** and an **Attention Mechanism** to model the temporal sequence of the heartbeat.

## Key Features
- **Integrated Environment**: Combines data analysis, visualization, and model training in a single interactive workflow.
- **Advanced Metadata Handling**: Processes clinical annotations from Excel, handles missing values, and aligns patient records with audio files.
- **Signal Processing**: Converts raw `.wav` recordings into robust feature representations (Mel-spectrograms) with normalization and padding.
- **Deep Learning Architectures**: Implementation of multi-layered CNNs and CRNNs with Attention for superior classification performance.
- **Evaluation Suite**: Includes confusion matrices, classification reports, and training history plots.
- **Interactive Inference**: A built-in prediction helper to test new audio files directly within the notebook with audio playback and spectrogram visualization.

## Dataset Structure
The notebook expects:
- **Audio Data**: A directory of `.wav` heart sound recordings.
- **Annotations**: `Heart Data_Annotation.xlsx` containing clinical findings for cada patient.

### Target Classes
The models classify sounds into:
- `N`: Normal
- `AR`: Aortic Regurgitation
- `MR`: Mitral Regurgitation
- `TR`: Tricuspid Regurgitation
- `AS`: Aortic Stenosis
- `MS`: Mitral Stenosis
- `PS`: Pulmonic Stenosis

## Dependencies
The notebook requires the following Python libraries:
```bash
pip install numpy pandas matplotlib seaborn librosa soundfile tqdm tensorflow scikit-learn joblib ipywidgets
```

## Notebook Sections
1.  **Annotation Analysis**: Loading and cleaning the Excel clinical data.
2.  **Audio File Mapping**: Parsing filenames and merging with clinical metadata.
3.  **Preprocessing**: Class filtering and label encoding.
4.  **Feature Extraction**: Multi-threaded extraction of Mel-spectrograms.
5.  **Model Definition**: Building the CNN and CRNN (with Attention) architectures.
6.  **Training**: Running training with Early Stopping and Model Checkpointing.
7.  **Evaluation**: Comparative analysis of model performance.
8.  **Prediction**: Sample file classification and visualization.

## Usage
1.  Ensure all heart sound `.wav` files are in the directory specified by `AUDIO_DIR`.
2.  Place `Heart Data_Annotation.xlsx` in the same directory as the notebook.
3.  Execute the cells in sequence.
4.  The best model will be saved as `best_heart_model.h5`.

## Visualizations
The notebook generates several critical plots:
- **Waveforms**: Visual representation of the sound amplitude.
- **Mel-Spectrograms**: Frequency-time heatmaps used as input for the models.
- **Accuracy/Loss Curves**: Progress trackers for model training.
- **Confusion Matrix**: Error analysis for each murmur class.
