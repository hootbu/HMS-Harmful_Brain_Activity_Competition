# Harvard Medical School - Harmful Brain Activity Classification Research Code Competition
###### Created by Emir Yorgun

## Project Overview
This project is a proud submission to the **Harvard Medical School Research Code Competition**, a distinguished initiative fostering innovation in biomedical research. The work centers on the automated detection and classification of seizures and other harmful brain activity patterns using electroencephalography (EEG) signals from critically ill patients. By enhancing the accuracy of EEG pattern recognition, the aim is to contribute meaningfully to neurocritical care, epilepsy management, and drug development. Supported by **Harvard Medical School**, the **Sunstella Foundation**, **Persyst**, and **Jazz Pharmaceuticals**, this effort addresses the challenges of manual EEG analysis, which can be time-consuming and susceptible to human error due to fatigue.

## Research Objectives
The goal is to develop a reliable model to classify six EEG patterns: **seizure (SZ)**, **generalized periodic discharges (GPD)**, **lateralized periodic discharges (LPD)**, **lateralized rhythmic delta activity (LRDA)**, **generalized rhythmic delta activity (GRDA)**, and **other**. This classification seeks to enable faster clinical decisions and support advancements in therapeutic research, reflecting a commitment to improving patient outcomes.

## Methodology and Implementation
The detailed approach is documented in the project, which outlines the following steps:
- **Data Processing**: EEG data with 20 channels (e.g., Fp1, F3) and spectrograms with 400 frequency bands from a 33.3 GB dataset are utilized, accessible via [Kaggle](https://www.kaggle.com/competitions/hms-harmful-brain-activity-classification) due to its size and copyright restrictions.
- **Feature Engineering**: Meaningful features are extracted, such as mean and minimum values over time intervals (e.g., 15 minutes, 50 seconds), to capture the nuances of brain activity.
- **Model Development**: The solution employs **XGBoost**, a highly effective gradient boosting algorithm, enhanced by **5-fold cross-validation** to ensure robustness and prevent overfitting. Five models are trained, with averaged predictions to optimize accuracy.

## Results and Performance
The project achieved a **private score of 0.779680**, placing it among the top performers in the competition. For the sample case, the predicted probabilities are: seizure (10.1%), LPD (5.3%), GPD (0.6%), LRDA (25.0%), GRDA (4.3%), and other (54.6%). The prominence of "other" highlights the model’s strength in navigating complex, uncertain classifications.

## Technical Contributions
- **XGBoost**: Chosen for its ability to manage complex, noisy datasets with optimized decision trees, XGBoost proved instrumental in achieving competitive performance.
- **5-Fold Cross-Validation**: This technique enhances model reliability by ensuring generalization across diverse patient data, a vital consideration in biomedical applications.
- **Feature Engineering**: Carefully crafted features from spectrogram data enable the model to detect subtle EEG dynamics, contributing significantly to its success.

## Acknowledgements
Heartfelt thanks go to the **Critical Care EEG Monitoring Research Consortium (CCEMRC)** and institutions like **Massachusetts General Hospital** for their invaluable expertise. Appreciation is also extended to **Harvard Medical School** and the **Sunstella Foundation** for hosting this inspiring competition.

## Citation
Jin Jing, Zhen Lin, Chaoqi Yang, Ashley Chow, Sohier Dane, Jimeng Sun, and M. Brandon Westover. HMS - Harmful Brain Activity Classification . https://kaggle.com/competitions/hms-harmful-brain-activity-classification, 2024. Kaggle.
