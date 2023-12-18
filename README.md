# Multiple-track PhonoCardioGraphy (PCG) and Artificial Intelligence (AI) for Heart Defect Detection

## Table of Contents
1. [Introduction](#introduction)
2. [Dataset](#dataset)
3. [Data Preprocessing](#data-preprocessing)
4. [Deep Learning Models](#deep-learning-models)
   - [Binary Classifier](#binary-classifier)
   - [Autoencoder](#autoencoder)
   - [Results](#deep-learning-model-results)
5. [Corrupted Segment Detection](#corrupted-segment-detection)
   - [Dataset](#dataset-corrupted-segment-detection)
   - [Data Preprocessing](#data-preprocessing-corrupted-segment-detection)
   - [Proposed Algorithm](#proposed-algorithm)
   - [Results](#results-for-corrupted-segment-detection)

## Introduction
This project focuses on the development and implementation of Multiple-track PhonoCardioGraphy (PCG) combined with Artificial Intelligence (AI) to detect heart defects. The AI component includes a Binary Classifier and an Autoencoder for supervised and unsupervised learning, respectively.

## Dataset
PhysioNet/CinC Challenge 2016, consisting of normal and abnormal heart sound recordings related to various pathological conditions is used.

## Data Preprocessing
Digital stethoscopes are used to capture PCG data with a recording duration of 10 seconds. The raw signals undergo a low pass filter, down-sampling, and spectrogram computation for efficient feature extraction. The dataset is split into training (80%) and validation (20%) sets.

## Deep Learning Models
### Binary Classifier
A Convolutional Neural Network (CNN) is employed for predicting normal and abnormal heart sounds. The model uses ReLU activation, binary crossentropy loss, and is trained with the Adam optimizer.

### Autoencoder
An Autoencoder, used for unsupervised data encoding, comprises an encoder and decoder. The model is trained using the Adam optimizer and Mean Squared Error (MSE) loss function. The training aims to minimize the difference between original and reconstructed input signals.

## Deep Learning Model Results
### Binary Classifier
- Training accuracy: 90.5%
- Validation accuracy: 92.5%
- Overall accuracy: 84.14%
- Specificity: 89.04%

### Autoencoder
The prediction results of the autoencoder model were in terms of reconstruction error. It was observed that for a few noisy but normal recordings, the overall reconstruction error is found high, causing false positives in the prediction of normal recordings.

## Corrupted Segment Detection
### Dataset (Corrupted Segment Detection)
The CirCor DigiScope dataset includes 5,282 Phonocardiogram (PCG) recordings obtained from various auscultation locations for 1,568 patients.

### Data Preprocessing (Corrupted Segment Detection)
Preprocessing involves spike removal, baseline wandering mitigation, and signal normalization for enhanced signal quality.

### Proposed Algorithm
1. **Quality Index:** Defines the quality of heart sound signals based on cyclic correlation function and Fourier transform.
2. **Time-varying Quality Index:** Utilizes a sliding window approach to capture localized variations in the signal's periodicity.

### Results for Corrupted Segment Detection
Binary mask plots derived from annotations and the degree of periodicity show close alignment, indicating successful automation of corrupted segment detection.

**Note:** This README provides an overview of the project. For detailed information, refer to the project report and code documentation.
