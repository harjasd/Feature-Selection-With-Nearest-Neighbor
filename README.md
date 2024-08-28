# Feature-Selection-With-Nearest-Neighbor

## I. Introduction
In this project, we implemented a feature selection algorithm using the nearest neighbor classifier to understand its sensitivity to irrelevant features. We employed two primary search strategies: forward selection and backward elimination. Our goal was to determine the optimal subset of features that maximize classification accuracy.

## II. Challenges
- **Data Handling:** Ensuring correct loading and preprocessing of the datasets.
- **Algorithm Implementation:** Implementing the nearest neighbor classifier and the leave-one-out validation efficiently.
- **Optimization:** Balancing computational efficiency with accuracy, especially for large datasets.
- **Feature Search:** Accurately implementing and debugging the forward selection and backward elimination algorithms.

## III. Code Design - Key Components
- **NNClassifier:** A class implementing the nearest neighbor classifier.
- **evaluate:** A function that uses `NNClassifier` to compute the accuracy of a given feature subset using leave-one-out validation.
- **load_dataset:** A function to load and preprocess the dataset.
- **forward_selection:** A function implementing the forward selection algorithm.
- **backward_elimination:** A function implementing the backward elimination algorithm.
- **main:** The main function to prompt user input and execute the chosen feature selection algorithm.

## IV. Dataset Details
- **General Small Dataset:**
  - Number of Features: 10
  - Number of Instances: 100
- **General Large Dataset:**
  - Number of Features: 40
  - Number of Instances: 1000
- **Personal Small Dataset:**
  - Number of Features: 10
  - Number of Instances: 100
- **Personal Large Dataset:**
  - Number of Features: 40
  - Number of Instances: 1000

### Plots and Exploration
We plotted several features and color-coded them by class to explore the dataset. This helped in identifying which features might be more relevant for classification.

## V. Algorithms
- **Forward Selection:**
  - Starts with an empty feature set and iteratively adds features that provide the highest increase in accuracy until no further improvement is possible.
- **Backward Elimination:**
  - Starts with the full feature set and iteratively removes the least significant feature (the one whose removal improves the accuracy the most) until no further improvement is possible.

## VI. Analysis
### Experiment 1: Comparing Forward Selection vs Backward Elimination
- **Without Feature Selection:**
  - Accuracy: 0.548
- **With Feature Selection:**
  - Forward Selection Accuracy: 0.89 (Small Dataset), 0.949 (Large Dataset)
  - Backward Elimination Accuracy: 0.83 (Small Dataset), 0.73 (Large Dataset)
  
#### Findings:
- Both forward selection and backward elimination identified the same optimal feature subsets for the datasets.
- **Pros and Cons of Each Algorithm:**
  - **Forward Selection:** Easier to implement and understand but may get stuck in local maxima.
  - **Backward Elimination:** Can potentially find better feature subsets by removing irrelevant features early but is computationally more expensive and can be less accurate with larger datasets.

### Experiment 2: Normalized vs Unnormalized Data
- **Accuracy with Normalized Data:**
  - Small Dataset: 0.89
  - Large Dataset: 0.81
- **Accuracy with Unnormalized Data:**
  - Small Dataset: 0.75
  - Large Dataset: 0.94

#### Findings:
Normalizing the data generally led to better performance by ensuring that all features contribute equally to the distance computations in the nearest neighbor classifier.



