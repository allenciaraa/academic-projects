# Anomaly Detection in Fetal Monitoring Using Negative Selection

## Overview

This project applies an immune system-inspired machine learning technique, negative selection, to detect anomalies in fetal cardiotocography (CTG) data. Originating from the domain of artificial immune systems, negative selection is particularly well-suited for one-class classification problems, where the goal is to detect deviations from normal patterns. By leveraging [Johanne Textor's Negative Selection Algorithm](https://johannes-textor.name/negativeselection.html) and performing rigorous ROC analysis, this work evaluates how effectively negative selection can identify abnormal fetal heart rate and uterine contraction patterns, which are signals critical to prenatal care.

## Project Summary

The project began by preprocessing a cardiotocography dataset obtained from the UCI Machine Learning Repository. This dataset comprises 21 continuous features derived from fetal heart rate and uterine contraction signals. Since the negative selection algorithm operates on categorical data, each feature was discretized into one of 10 bins, mapped to alphabetic characters (‘A’ through ‘J’). The result was a transformed dataset of 21-character strings—one string per data sample—formatted for compatibility with the negative selection algorithm.

Following preprocessing, I employed the negative selection algorithm to perform anomaly detection. The model was trained on normal samples and evaluated on a test set that included both normal and abnormal cases. Detection scores for each test instance were computed across varying values of the `r` parameter, which defines the length of contiguous matching segments required for a detector to recognize a string as "normal." The impact of different `r` values (ranging from 2 to 10) was evaluated using ROC curve analysis.

To quantify detection performance, a custom pipeline was implemented to calculate the Area Under the Curve (AUC) of each ROC curve. For each value of `r`, the pipeline computed true positive and false positive rates over a range of thresholds (θ from 0 to 10). AUC scores were then collected in a summary table to identify optimal parameter settings. Results indicated a strong sensitivity of the model to `r`, with performance peaking within a specific range and degrading outside of it, highlighting the importance of tuning this parameter.

## Tools and Technologies

- **Languages & Libraries**: Python, Pandas, Scikit-learn, Subprocess, Matplotlib
- **Key Techniques**:
  - Data binning and categorical transformation
  - Textor’s negative selection algorithm
  - ROC curve generation and AUC calculation
  - Parameter sweep over contiguous match lengths (`r`)
  - Integration of ground truth labels for validation

## Medical Significance

Cardiotocography is a vital tool in prenatal diagnostics, used to monitor fetal health and identify conditions such as hypoxia or fetal distress. By automating anomaly detection using negative selection, this project contributes to the development of intelligent screening tools that can support obstetric decision-making. Detecting abnormal patterns early and reliably could lead to better clinical outcomes and reduce the risk of complications during pregnancy and childbirth.

## Why I Loved This Project

I’ve always loved the intersection of biology and computer science, and this project exemplified that perfectly. Exploring the mechanics of immune responses and applying them to anomaly detection was incredibly fascinating. In cybersecurity, algorithms modeled after the immune system can identify and reject threats, developing a kind of immunological memory to recognize similar attacks in the future. I’m drawn to the creativity involved in studying natural immune systems and finding ways to replicate them computationally. In this case, I found it especially clever to apply that approach to detect anomalies in fetal heart rate and uterine contractions. We took a biological process, recreated it digitally, and then reapplied it to a biological context. While much is said about how computing advances biology, I’m particularly inspired when biology informs computing. Projects like this highlight the elegance of natural systems and how they can shape technological innovation.
