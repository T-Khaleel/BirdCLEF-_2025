# BirdCLEF-_2025

This project was developed as part of the Machine Learning in Practice course and focuses on improving audio classification performance by using multiple feature representations. The solution was designed and evaluated in the context of the BirdCLEF+ 2025 Kaggle competition, which tasked participants with identifying avian and other species from audio recordings.


## Project Overview
We experimented with mel-spectrogram, MFCC, and CQT feature representations extracted from raw audio files. These were used as inputs to various pretrained CNN models (RegNetY, ResNet, EfficientNet) for multi-label classification.

Key components:
Denoising: Human voice removed using Silero VAD
Tiling: Repeats short audio segments to meet model input length
Segmentation: Long test audio is split into 5-second chunks
Ensembling: Combines predictions across models/features


## Feature Extraction
Implemented in Preprocessing.ipynb, this notebook:

Loads audio files
Removes human noise
Segments/tiles to 5 seconds (or 10 for specific tests)
Extracts and saves features (mel-spectrogram, MFCC, CQT) using librosa


## Inference Pipeline
Implemented in Inference.ipynb, this notebook:

Loads test audio and segments it

Loads trained model weights

Applies same pre-processing steps as training

Predicts labels for each segment and aggregates results

Note: Human voice removal during inference was found unnecessary as test data lacked human voices.
