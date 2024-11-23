# Arabic Dialect Classification with Synthetic Data and Semi-Supervised Learning

## Overview

This project investigates the impact of Large Language Model (LLM)-generated synthetic data on Arabic dialect classification, utilizing semi-supervised learning (SSL) techniques to address the challenges posed by the lack of labeled data. We experiment with both real and synthetic data to evaluate their effect on model performance in the classification of Arabic dialects from the MADAR dataset. Our approach demonstrates that synthetic data, in conjunction with SSL, can partially mitigate the lack of labeled data and enhance the performance of dialect classification models in low-resource settings.

## Abstract

The scarcity of labeled data presents significant challenges in training high-performance machine learning models, especially for underrepresented languages like Arabic dialects. To address this, we generated synthetic data using LLMs and applied an SSL approach to effectively utilize unlabeled data. Three main experiments were conducted:
1. **Real Data + SSL**: Using real data with SSL.
2. **Real + Synthetic Data + SSL**: Combining real data with synthetic data for SSL.
3. **Synthetic Data + SSL**: Using only synthetic data for SSL.

Our results show that semi-supervised models outperform supervised models trained on limited real data, while synthetic data, when used alone, performs within 5.3% of supervised models trained on a small portion of real data. These findings indicate that both SSL and synthetic data hold promise in overcoming data scarcity issues in Arabic dialect classification.

## Objectives
The primary objectives of this project are:
- To address the **data scarcity** issue by generating synthetic data using LLMs.
- To mitigate the **label shortage** problem by leveraging SSL to utilize both labeled and unlabeled data.
- To evaluate the impact of combining synthetic and real data in improving model performance for Arabic dialect classification.

## Methodology

![Screenshot 2024-11-24 000953](https://github.com/user-attachments/assets/15c1d9a5-6118-4832-b8c7-803a168868af)
Figure 1. A parallel workflow for Arabic dialect classification that involves sampling real datasets and generating synthetic data using
prompts, followed by data analysis, evaluation, and testing with different learning methods.

### Data Generation
- **Real Data**: We used the MADAR dataset, which includes samples from various Arabic dialects.
- **Synthetic Data**: Synthetic sentences were generated using GPT-4o and GPT-4o-mini models for five dialect categories. These synthetic sentences were then utilized alongside real data to evaluate their impact.

### Experiments
We conducted three primary experiments to assess the effectiveness of synthetic data:
1. **Real Data + SSL**: Evaluated SSL performance using only real data.
2. **Real + Synthetic Data + SSL**: Combined real and LLM-generated synthetic data for SSL, with models tested on real data.
3. **Synthetic Data + SSL**: Tested SSL using only synthetic data to determine its effectiveness as a substitute for real data.

### Machine Learning Models
The models implemented include:
- **Stochastic Gradient Descent (SGD) Classifier**
- **Logistic Regression**
- **Linear Support Vector Classifier (SVC)**
- **Passive-Aggressive Classifier**
- **Multinomial Naive Bayes**

All models were tested under both supervised and self-training settings to evaluate their effectiveness with different combinations of real and synthetic data.



## Research Focus
We focus on classifying five Arabic dialects from the **MADAR dataset** using three main experiments:
1. **Real Data + SSL**: Evaluate the performance of SSL with only real data.
2. **Real + Synthetic Data + SSL**: Combine real data with LLM-generated synthetic data in SSL and test on real data.
3. **Synthetic Data + SSL**: Test SSL using only synthetic data to assess its potential as a substitute for real data.


## Steps to run the code



## Main Results

<img src="https://github.com/user-attachments/assets/953ed38a-3d7b-4446-a51f-b1a41eca05f4" alt="dialects_difff" width="500">


Figure 2. Comparison of Real and Generated Datasets Across Dialects by Training Method and Metric: Each graph illustrates Precision,
Recall, or F1-Score for 100% Supervised, 20% Supervised, and Self-Training methods, highlighting performance differences of average
linear classifiers between Real and Generated datasets across dialects

### Takeaways
1. **Precision**: Real data outperforms generated data in all settings, with smaller gaps in 20% Supervised and Self-Training.
2. **Recall**: Generated data performs competitively, particularly in 20% Supervised and Self-Training.
3. **F1-Score**: Generated data shows near-parity with real data in Self-Training, especially for Gulf and Levantine dialects.
4. **Dialect-Specific**: Egyptian has the best performance, while Maghrebi consistently lags behind.
5. **Overall**: Self-Training effectively bridges the gap between real and generated data.



