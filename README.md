# HMS - Harmful Brain Activity Classification Project
###### Created by Emir Yorgun

## Project Overview
This project is a proud submission to the **Harvard Medical School Research Code Competition**, a distinguished initiative fostering innovation in biomedical research. The work centers on the automated detection and classification of seizures and other harmful brain activity patterns using electroencephalography (EEG) signals from critically ill patients. By enhancing the accuracy of EEG pattern recognition, the aim is to contribute meaningfully to neurocritical care, epilepsy management, and drug development. Supported by **Harvard Medical School**, the **Sunstella Foundation**, **Persyst**, and **Jazz Pharmaceuticals**, this effort addresses the challenges of manual EEG analysis, which can be time-consuming and susceptible to human error due to fatigue.

## Research Objectives
The goal is to develop a reliable model to classify six EEG patterns: **seizure (SZ)**, **generalized periodic discharges (GPD)**, **lateralized periodic discharges (LPD)**, **lateralized rhythmic delta activity (LRDA)**, **generalized rhythmic delta activity (GRDA)**, and **other**. This classification seeks to enable faster clinical decisions and support advancements in therapeutic research, reflecting a commitment to improving patient outcomes.

## Methodology and Implementation
The detailed approach is documented in the project, which outlines the following steps:
- **Data Processing**: EEG data with 20 channels (e.g., Fp1, F3) and spectrograms with 400 frequency bands from a 33.3 GB dataset are utilized, accessible via [Kaggle](https://www.kaggle.com/competitions/hms-harmful-brain-activity-classification).
- **Feature Engineering**: A total of 1,600 numerical features were extracted from spectrograms using both short-term (50 seconds) and long-term (10–15 minutes) windows. These include statistical measures such as mean and minimum values across various brain regions.
- **Model Development**: The solution employs **XGBoost**, a highly effective gradient boosting algorithm. The model was evaluated using **GroupKFold (n=5)** patient-based cross-validation. Log-loss metrics were monitored at each fold, and early stopping was applied between 40–60 boosting rounds to prevent overfitting. Fold 3 demonstrated particularly strong generalization with lower log-loss values.

## Results and Performance
The project achieved a **private score of 0.779680**, placing it among the top performers in the competition. For the sample case, the predicted probabilities are: seizure (10.1%), LPD (5.3%), GPD (0.6%), LRDA (25.0%), GRDA (4.3%), and other (54.6%). The prominence of "other" highlights the model’s strength in navigating complex, uncertain classifications.

The model's learning behavior showed rapid log-loss reduction in the first 20–30 boosting rounds, stabilizing thereafter. This indicates stable and reliable classification performance. Feature importance analysis revealed that short-term features such as `RL_11_33_mean_50s`, `RP_8_79_mean_50s`, and `LL_7_42_mean_50s` were most influential, suggesting sensitivity to sudden, localized EEG changes. In contrast, long-term minimum features (e.g., `RP_5.47_min_15m`) had lower importance, indicating limited contribution from low-frequency, sustained activity.

## Technical Contributions
- **XGBoost**: Chosen for its ability to manage complex, noisy datasets with optimized decision trees, XGBoost proved instrumental in achieving competitive performance.
- **5-Fold Cross-Validation**: This technique enhances model reliability by ensuring generalization across diverse patient data, a vital consideration in biomedical applications.
- **Feature Engineering**: Carefully crafted features from spectrogram data enable the model to detect subtle EEG dynamics, contributing significantly to its success.

## Conclusion and Future Work
This study presents a machine learning-based system for the automatic classification of harmful brain activities using EEG and spectrogram data. The model demonstrated consistent performance across validation folds and was protected from overfitting through early stopping.

Several directions are proposed for future improvements:
- **Biological Interpretability**: Incorporating EEG frequency band features (Delta, Theta, Alpha, etc.) may enhance clinical relevance.
- **Raw Signal Features**: Extracting time-series features (e.g., entropy, wavelength, variance) directly from raw EEG signals could enrich the model’s input space.
- **Deep Learning Approaches**: Implementing architectures such as 1D CNNs or LSTMs may allow the model to learn hierarchical representations directly from data, potentially improving classification accuracy.

## Acknowledgements
Heartfelt thanks go to the **Critical Care EEG Monitoring Research Consortium (CCEMRC)** and institutions like **Massachusetts General Hospital** for their invaluable expertise. Appreciation is also extended to **Harvard Medical School** and the **Sunstella Foundation** for hosting this inspiring competition.

## Citation
Jin Jing, Zhen Lin, Chaoqi Yang, Ashley Chow, Sohier Dane, Jimeng Sun, and M. Brandon Westover. HMS - Harmful Brain Activity Classification . https://kaggle.com/competitions/hms-harmful-brain-activity-classification, 2024. Kaggle.
