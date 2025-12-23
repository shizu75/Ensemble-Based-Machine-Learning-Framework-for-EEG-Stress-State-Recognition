# Ensemble-Based Machine Learning Framework for EEG Stress State Recognition

## Abstract
This repository presents a comprehensive and methodologically rigorous machine learning framework for **EEG-based stress state recognition**, focusing on ensemble learning and comparative model analysis. The work emphasizes robust preprocessing, principled class balancing, structured validation protocols, and the integration of multiple classical and ensemble-based classifiers. The pipeline is designed to reflect research-grade experimental practices suitable for doctoral-level portfolios, with particular attention to reproducibility, generalization, and analytical transparency.

---

## Research Motivation
Physiological stress detection from EEG signals is a challenging problem due to high-dimensional feature spaces, inter-subject variability, and class imbalance. Rather than relying on a single model family, this project systematically explores **individual classifiers, stacked ensembles, and gradient-boosted methods**, demonstrating how model diversity and aggregation can enhance predictive robustness in biosignal classification tasks.

---

## Dataset and Label Engineering
The dataset consists of multichannel EEG-derived features annotated with emotional states. To establish a well-defined binary classification task:
- Metadata fields (timestamps, subject identifiers) are removed
- Emotional labels are consolidated into two categories: *Stressed* and *Unstressed*
- Duplicate records are detected and removed
- Class distributions are explicitly controlled through subsampling to ensure balance

This design minimizes bias and aligns with best practices in empirical machine learning research.

---

## Feature Processing and Normalization
All numerical EEG features are standardized using z-score normalization to ensure consistent scaling across dimensions. Emotional labels are encoded numerically to enable compatibility with a wide range of classifiers.

---

## Experimental Protocol
The dataset is partitioned into **training, validation, and test sets** using randomized and reproducible splits. Validation data is explicitly separated from the test set to support model selection without information leakage.

To analyze learning behavior, classifiers are trained using a pseudo-epoch batching strategy, enabling:
- Epoch-wise tracking of training and validation accuracy
- Monitoring of log-loss dynamics
- Visualization of convergence and stability trends

---

## Models and Architectures
The framework evaluates a diverse family of classifiers, including:

- Support Vector Machines with nonlinear kernels
- Random Forest ensembles
- Decision Trees
- k-Nearest Neighbors
- Logistic Regression with both L1 and L2 regularization
- Gradient Boosted Trees (XGBoost)
- Stacking-based ensemble models combining heterogeneous learners

Each model is trained and evaluated under identical data conditions to ensure fair comparison.

---

## Ensemble Learning Strategy
A stacking ensemble is constructed using:
- Base learners: Support Vector Machine and Random Forest
- Meta-learner: Logistic Regression
- Cross-validation at the ensemble level to enhance generalization

This hierarchical learning approach exploits complementary decision boundaries across models and demonstrates the advantages of ensemble reasoning in physiological signal classification.

---

## Hyperparameter Optimization
The framework integrates systematic hyperparameter search techniques:
- Randomized and grid-based search for ensemble and boosting models
- Explicit comparison between baseline and optimized configurations
- Quantitative evaluation of performance improvements

Such optimization is critical for extracting maximal performance from classical machine learning models.

---

## Evaluation Metrics and Diagnostics
Model performance is assessed using:
- Accuracy on unseen test data
- Log-loss for probabilistic calibration analysis
- Confusion matrices for error structure inspection
- Epoch-wise accuracy and loss curves for training diagnostics

These metrics collectively provide both quantitative rigor and qualitative interpretability.

---

## Key Contributions
- End-to-end EEG stress classification pipeline with balanced data design
- Comparative evaluation of individual, ensemble, and boosted models
- Stacking-based ensemble architecture with cross-validated meta-learning
- Integrated hyperparameter optimization for multiple model families
- Research-oriented evaluation methodology emphasizing robustness and transparency

---

## Technologies Used
Python, NumPy, Pandas, scikit-learn, XGBoost, Matplotlib

---

## Research Significance
This work demonstrates that carefully engineered ensemble-based machine learning systems can achieve robust performance on EEG-derived stress classification tasks without relying exclusively on deep learning. The framework provides a strong empirical baseline and a scalable foundation for future research involving subject adaptation, temporal modeling, or multimodal physiological data fusion.

---

## Author
This repository represents a research-driven implementation intended for advanced academic and doctoral portfolios, highlighting experimental rigor, ensemble learning strategies, and reproducible machine learning practice.
