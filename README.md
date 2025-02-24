EEG Seizure Detection using Deep Learning
Introduction
This project implements a deep learning-based EEG seizure detection system inspired by the research paper A Multi-View Deep Learning Framework for EEG Seizure Detection. The primary goal is to automate seizure detection using scalp EEG signals, avoiding the need for time-consuming manual analysis.

The methodology includes:

Converting EEG signals into spectrogram representations.
Leveraging denoising and convolutional autoencoders for feature extraction.
Implementing a channel-aware module to enhance seizure detection.
Training a model on the CHB-MIT dataset and comparing results with the original paper.
Our implementation achieved an accuracy of 81%, compared to the 94% reported in the original study. The difference is primarily due to variations in data preprocessing and the number of EEG channels used.

Dataset
CHB-MIT Scalp EEG Dataset: A publicly available dataset containing EEG recordings from 23 patients with epilepsy.
Modifications in our implementation:
The original study used 96 channels, while our implementation used 23 channels.
Labels were already provided in CSV format, whereas the paper’s method extracted labels from real-time recordings.
Implementation Details
Preprocessing: EEG signals were segmented into 4.5-second windows with 1-second overlap and converted into 2D spectrograms.
Model Architecture:
Denoising Autoencoder (DA): Extracts robust latent features from EEG spectrograms.
Convolutional Autoencoder (ConvA): Preserves spatial locality in spectrograms for better feature extraction.
Channel-Aware Module: Identifies key EEG channels to improve classification accuracy.
Supervised Learning Component: Uses a deep neural network with softmax activation for seizure classification.
Performance Metrics: Evaluated using F1-score, Accuracy, Precision-Recall (PR) curves, and ROC curves.

Results & Challenges
Achieved test accuracy: 81% (compared to 94% in the original paper).
Key challenge: The dataset used fewer channels (23 vs. 96), leading to performance differences.
Potential improvements: Experimenting with different feature extraction techniques and fine-tuning hyperparameters.
