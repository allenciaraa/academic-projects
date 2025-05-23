# Glucose Monitoring and Meal Detection in Artificial Pancreas Systems

## Overviewg

This project investigates the use of data science and machine learning techniques to analyze continuous glucose monitoring (CGM) and insulin pump data, with the overarching goal of improving glycemic control and automation in artificial pancreas systems. By leveraging real-world datasets, the work encompasses a range of tasks including time-series analysis, supervised classification, and unsupervised clustering, ultimately generating insights with medical relevance to diabetes management.

## Project Summary

The project began by developing a comprehensive pipeline for extracting clinically significant glucose metrics from CGM data. Each day’s CGM readings were segmented into full-day, daytime, and overnight intervals to calculate metrics such as percentage of time in the appropriate range (70–180 mg/dL), hyperglycemia (>180 mg/dL), and hypoglycemia (<70 mg/dL). Special consideration was given to identifying the switch from manual to auto insulin delivery, a key event marked by specific log entries in the insulin pump data. Missing data was handled through filtering and interpolation strategies to ensure robust metric computation.

Building upon the time-series analysis, the next phase focused on developing a supervised machine learning model to detect meal intake based on CGM data patterns. Meal events were identified from insulin pump logs, and corresponding CGM segments were extracted to represent both meal and no-meal scenarios. Feature engineering was a critical step, transforming glucose curves into numerical representations suitable for classification. An SVM (Support Vector Machine) was trained using these features, and performance was validated using k-fold cross-validation to ensure generalizability. The trained model was serialized using Python’s `pickle` module, enabling its deployment in a separate inference script. This script accepts new CGM data and outputs a prediction vector indicating whether each time segment represents a meal event.

The final component applied unsupervised clustering to categorize glucose responses by meal size. Using previously engineered features from the supervised learning phase, clustering algorithms such as KMeans and DBSCAN grouped meal data according to carbohydrate intake levels. Ground truth meal sizes were discretized into 20g bins, providing a benchmark for evaluating clustering performance. Clustering effectiveness was quantified using metrics like Sum of Squared Errors (SSE), entropy, and purity—each offering insight into intra-cluster cohesion and inter-cluster distinction.

## Tools and Technologies

- **Languages & Libraries**: Python, NumPy, Pandas, Scikit-learn, Pickle
- **Key Techniques**:

  - Time-series segmentation and missing data handling
  - Feature extraction and engineering for glucose patterns
  - Supervised learning with SVM
  - Model serialization and deployment
  - Clustering with KMeans and DBSCAN
  - Evaluation with SSE, entropy, and purity

## Medical Significance

The project contributes to the advancement of closed-loop insulin delivery systems by automating the detection of unannounced meals and characterizing individual glucose responses. These capabilities support the personalization of diabetes treatment, facilitating more precise insulin dosing and reducing the burden on patients and clinicians alike.
