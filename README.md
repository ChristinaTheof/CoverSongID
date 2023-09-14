# CoverSongID

Overview

The Cover Song Identification is a project aimed at developing an intelligent system for recognizing cover songs within a given database. This system leverages machine learning and neural networks to perform this music analysis task. It aligns, extracts features, computes cross-correlation matrices, and processes them using the Similarity Network Fusion (SNF) method. Finally, these matrices and the SNF results are fed into a Convolutional Neural Network (CNN) to make predictions.

Dataset

We have created a dataset for this project, where each folder in the cover clique contains two or more songs that are known covers of one another. The dataset is structured for supervised learning, with labeled cover song pairs.

Methodology

Data Preprocessing
Sampling: We randomly sample 10,000 frames from each song to ensure manageable input data size, or we calculate the median and trim/zero-pad the songs accordingly (the median for the current database is 32.000 frames).
Data Alignment: Dynamic Time Warping (DTW) is applied to align the sampled frames for each pair of cover songs.

Feature Extraction
Feature Choice: We extract either Mel-frequency Cepstral Coefficients (MFCCs) or Harmonic Pitch Class Profiles (HPCPs) as audio features, depending on the experimental setup.

Cross-correlation Analysis
Cross-correlation Matrices: We compute cross-correlation matrices for each pair of cover songs using the chosen audio features.

Similarity Network Fusion (SNF)
Fusion of Similarity Matrices: The cross-correlation matrices are processed using SNF to create a fused similarity network, capturing relationships among cover songs.

Convolutional Neural Network (CNN)
Input: We feed the fused similarity network, as well as the individual cross-correlation matrices, into a CNN for the final classification task.
