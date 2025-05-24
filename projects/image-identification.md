# Handwritten Digit Classification Using Naive Bayes and Deep Learning

## Overview

This project explores two distinct yet complementary machine learning approaches—probabilistic modeling and deep learning—for the classification of handwritten digits using the MNIST dataset. The aim is to understand and compare traditional feature-based classification with modern end-to-end learning through convolutional neural networks (CNNs). The implementation spans supervised learning with a Naive Bayes classifier for binary classification, and a deep learning pipeline using a CNN for multi-class classification, highlighting the evolution of algorithmic complexity in solving visual recognition tasks.

## Project Summary

The project began with a Naive Bayes classifier focused on distinguishing digits "0" and "1". Feature extraction was performed on each image to compute two key statistical features: the average pixel brightness and its standard deviation. These features were assumed to be independent and modeled as two-dimensional Gaussian distributions for each digit. Maximum Likelihood Estimation (MLE) was used to derive the parameters of the distributions, and the classifier was then applied to test data to predict labels and compute accuracy. This provided a strong baseline for understanding the relationship between handcrafted features and classification performance.

In the second phase, a convolutional neural network (CNN) was developed to classify all ten digits (0–9). The architecture consisted of two convolutional layers, each followed by max pooling, and a sequence of fully connected layers with ReLU activation. The final output layer used a softmax activation function for multi-class classification. Hyperparameters such as kernel size and number of feature maps were varied to observe their impact on training and test accuracy. Throughout training, loss and accuracy metrics were plotted across epochs to monitor model convergence and generalization. Additional experiments involved increasing kernel sizes and the number of feature maps, illustrating the effect of architectural changes on learning dynamics.

The contrast between the two models offered rich insight into the trade-offs between simplicity, interpretability, and performance. The Naive Bayes approach proved efficient and interpretable, while the CNN significantly improved classification accuracy by learning complex spatial patterns directly from the pixel data.

## Tools and Technologies

**Languages & Libraries**: Python, NumPy, SciPy, Matplotlib, TensorFlow/Keras
**Key Techniques**:

- Statistical feature engineering (mean and standard deviation of image intensity)
- Maximum Likelihood Estimation and Gaussian modeling
- Naive Bayes classification for binary image recognition
- Design and training of Convolutional Neural Networks (CNNs)
- Hyperparameter tuning and performance visualization
- Loss and accuracy tracking during training

## Educational Significance

This project served as a deep dive into both the theoretical foundations and practical implementations of machine learning algorithms for visual recognition. It reinforced core concepts like feature independence in probabilistic models and the hierarchical feature extraction of deep networks. By comparing the effectiveness of each method on the MNIST dataset, it highlighted the strengths and limitations of both handcrafted and learned features. This comparison equips practitioners with a nuanced understanding of when to apply traditional methods versus deep learning in real-world classification tasks.

## Why I Loved This Project

I loved this project because it gave me a hands-on understanding of how convolutional neural networks (CNNs) perform image classification It was amazing to see how convolutional filters were essentially small frames that can learn to identify patterns like edges, shapes, and textures within handwritten digits. Digging into the underlying math and logic behind each layer of the network helped me appreciate the elegance and complexity of these models. It’s truly inspiring to explore, at a fundamental level, how such powerful algorithms are constructed and refined. This project not only deepened my technical knowledge but also reinforced my passion for machine learning and computer vision.
