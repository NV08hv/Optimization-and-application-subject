# Classification of Cardiac Arrhythmia Using GA Stacking in Ensemble Learning

## Description

This project presents a hybrid ensemble learning approach for classifying cardiac arrhythmia types using the Cardiac Arrhythmia Database from the UCI Machine Learning Repository. The approach combines five machine learning and deep learning models as base learners, including Random Forest, Gradient Boosting, Support Vector Classifier (SVC), XGBoost, and Convolutional Neural Network (CNN). A Logistic Regression (LR) model serves as the meta-learner to combine the predictions from the base models.

To optimize the ensemble, two methods are employed: Genetic Algorithm (GA) and Grid Search. GA is used to search for the optimal combination of base models by maximizing the F1-score, while Grid Search performs an exhaustive search over all possible combinations to identify the best ensemble configuration.

The dataset consists of 452 patient records with 279 features, including ECG parameters, age, and gender, and 16 initial diagnostic labels (reduced to 13 after preprocessing). The class imbalance in the dataset is addressed using label weighting.

Feature selection is performed using the Maximum Relevance Minimum Redundancy (mRMR) method to select the top 100 features, enhancing model efficiency and reducing overfitting.

The project demonstrates the effectiveness of ensemble learning and optimization techniques in improving diagnostic accuracy for cardiac arrhythmia classification.

## Methods

### Base Models

- Random Forest
- Gradient Boosting
- Support Vector Classifier (SVC)
- XGBoost
- Convolutional Neural Network (CNN)

### Meta-Model

- Logistic Regression (LR)

### Optimization Techniques

- **Genetic Algorithm (GA)**: Used to find the optimal combination of base models by simulating natural evolution processes (mutation, crossover, selection). The fitness function is the F1-score, and the best configuration found includes Gradient Boosting, SVC, XGBoost, and CNN with a fitness score of 0.9708.

- **Grid Search**: Performs an exhaustive search over all possible combinations of base models, identifying the best ensemble as all five base models with a fitness score of 0.723.

### Feature Selection

- Maximum Relevance Minimum Redundancy (mRMR) to select the top 100 features from 279.

## Results

- **GA Best Configuration**: Gradient Boosting, SVC, XGBoost, and CNN with a fitness score of 0.9708.

- **Grid Search Best Configuration**: All five base models with a fitness score of 0.723.

- **Performance Metrics**:
  - Ensemble models achieved accuracies above 0.70.
  - Grid Search ensemble: Accuracy = 0.71, Precision = 0.48, F1-Score = 0.49 on the test set.
  - Individual base models like Gradient Boosting and XGBoost achieved accuracies of 0.72.

- **Comparison**: Grid Search outperformed GA due to the small dataset size, offering exhaustive evaluation and shorter training times. GA is noted for scalability to larger datasets.

| Method                        | Configuration                              | Fitness Score | Accuracy | Precision | F1-Score |
|-------------------------------|--------------------------------------------|---------------|----------|-----------|----------|
| GA                            | Gradient Boosting, SVC, XGBoost, CNN       | 0.9708        | -        | -         | -        |
| Grid Search                   | All five base models                       | 0.723         | 0.71     | 0.48      | 0.49     |
| Gradient Boosting (Individual)| -                                          | -             | 0.72     | -         | -        |
| XGBoost (Individual)          | -                                          | -             | 0.72     | -         | -        |

## Applications

This approach is applicable to automated medical diagnostic systems, particularly for classifying physiological signals like ECGs in healthcare. It highlights the potential of ensemble learning and optimization techniques to improve diagnostic accuracy and efficiency in cardiovascular disease detection.
