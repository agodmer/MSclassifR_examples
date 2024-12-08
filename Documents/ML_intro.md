<h1 align="center">A Brief Introduction concerning Machine Learning</h1>
Alexandre Godmer, Quentin Giai Gianetto

---

Machine Learning (ML) is a field within artificial intelligence (AI) that focuses on creating algorithms and models that allow computers to learn from and make predictions or decisions based on data. Unlike traditional programming, where explicit instructions are given for every task, ML enables systems to learn from patterns and insights within data, improving their performance over time as they are exposed to more information.

- There are several types of learning paradigms within ML:

    - Supervised Learning: In supervised learning, algorithms are trained on labeled datasets, meaning the input data has corresponding known outputs or labels. The goal is to create a model that can predict these outputs when given new, unseen data. Examples of supervised learning algorithms include linear regression, logistic regression, support vector machines (SVM), and decision trees.

    - Unsupervised Learning: In unsupervised learning, algorithms work with unlabeled data. The model's task is to find hidden patterns, structures, or groupings within the data without predefined outcomes. Clustering (such as K-Means) and dimensionality reduction (such as Principal Component Analysis, PCA) are common unsupervised learning methods.

    - Reinforcement Learning: This type of learning involves an agent interacting with an environment and making decisions to maximize cumulative rewards. Unlike supervised or unsupervised learning, reinforcement learning focuses on learning optimal actions through trial and error, adjusting the strategy based on feedback.


## 1. Summary Table of some Machine Learning Algorithms

| Algorithm Name                | Type               | Description                                                                                                         |
|-------------------------------|--------------------|---------------------------------------------------------------------------------------------------------------------|
| Linear Regression             | Supervised         | Predicts a quantitative output using one or more explanatory variables (linear relationship).                       |
| Logistic Regression           | Supervised         | Predicts a binary qualitative output using a sigmoid function (classification).                                     |
| Support Vector Machines (SVM) | Supervised         | Projects data into a higher-dimensional space to separate classes using a hyperplane, applicable to linear or non-linear data. |
| Decision Trees                | Supervised         | Uses decision rules represented in a tree structure for classification or regression.                              |
| Random Forests (RF)           | Supervised         | Combines multiple decision trees trained on subsets of data to improve prediction accuracy (bagging method).        |
| Gradient Boosting Machine (GBM)| Supervised        | Sequentially builds decision trees to reduce prediction error by addressing residuals of prior models (boosting).   |
| K-Means Clustering            | Unsupervised       | Groups unlabeled data into clusters based on feature similarity.                                                   |
| Principal Component Analysis (PCA) | Unsupervised   | Reduces data dimensionality by projecting data onto principal components that maximize variance.                    |         |
| Multilayer Perceptron (MLP)   | Deep Learning      | Neural network architecture with interconnected layers for solving complex problems.                                |
| Convolutional Neural Networks (CNN) | Deep Learning | Neural network architecture specialized for processing image data, using convolutional layers to extract features.  |

## 2. Metrics for Evaluating Machine Learning Models

Various metrics are used to evaluate machine learning algorithms depending on the type of problem (classification or regression) and the dataset. Below is a summary of commonly used metrics:

### 2.1. Classification Metrics for Classification

| Metric                  | Description                                                                                                 | Use Case                                    |
|-------------------------|-----------------------------------------------------------------------------------------------------------|--------------------------------------------|
| Accuracy                | (True Positives + True Negatives) / Total Samples                                                         | Measures the percentage of correct predictions. |
| Precision (Positive Predictive Value - PPV) | True Positives / (True Positives + False Positives)                                                | Focuses on the relevance of predicted positive cases. |
| Recall (Sensitivity)    | True Positives / (True Positives + False Negatives)                                                        | Measures the ability to correctly identify all relevant instances. |
| Specificity             | True Negatives / (True Negatives + False Positives)                                                        | Evaluates the ability to correctly identify negative instances. |
| F1 Score                | 2 × (Precision × Recall) / (Precision + Recall)                                                           | Balances precision and recall in a single metric. |
| Cohen's Kappa           | (Observed Agreement - Expected Agreement) / (1 - Expected Agreement)                                       | Measures the agreement between predicted and actual labels, adjusting for chance. |
| Confusion Matrix        | Layout showing True Positives, True Negatives, False Positives, and False Negatives in a matrix format.   | Summarizes predictions for classification problems. |

### 2.2. Multi-class Classification Metrics for Classification

| Metric                  | Formula or Description                                                                     | Use Case                                    |
|-------------------------|--------------------------------------------------------------------------------------------|--------------------------------------------|
| Accuracy (Multi-class)  | (Correct Predictions) / (Total Samples)                                                    | Measures overall performance across multiple classes. |
| Macro-averaged F1 Score | Calculates the average F1 score across all classes, treating each class equally.            | Suitable for imbalanced datasets.          |
| Weighted F1 Score       | Calculates the F1 score, weighted by the number of instances in each class.                 | Accounts for class imbalance in the dataset. |

## 3. Machine Learning Process

After defining a problem and setting an objective, the steps to resolve the problem using Machine Learning (ML) can be summarized as follows :

1. **Import and Inspect the Initial Dataset**:
   - once the data is imported into an environment like R, it is essential to ensure the data is of good quality. This involves handling missing data, verifying data consistency, and inspecting the dataset using unsupervised techniques (e.g., Principal Component Analysis, PCA) to identify potential outliers.

2. **Prepare the Datasets**:
   - at this stage, the initial dataset is split into a training set, which is used to train the ML algorithm (typically 70-80% of the data), and a test set, which remains completely independent (usually 20-30% of the data). The test set is later used to evaluate the model’s performance.

3. **Select and Configure an ML Algorithm**:
   - several factors must be considered when choosing an algorithm: the nature of the problem (regression or classification), the size and nature of the data, and the resources and tools available for training and implementing the algorithm. Adjustable parameters, known as hyperparameters, need to be configured as they influence the model’s training. Examples of hyperparameters include the number of neurons and layers in a Multilayer Perceptron (MLP) or the kernel used in a Support Vector Machine (SVM). These hyperparameters can be tuned either randomly or via a predefined grid of values provided by the user.

4. **Train the ML Algorithm**:
   - training a supervised ML algorithm is an iterative process. The error between the predicted and actual outcomes (defined during the labeling phase) is measured using a cost function. The model parameters are adjusted based on the measured error to minimize it with each iteration. Various optimization algorithms, such as gradient descent, are used to fine-tune the model parameters. During the training process, the training dataset can be further split into a training subset (used to train the model and adjust parameters) and a validation subset (used to evaluate the model’s performance and determine optimal parameters and hyperparameters). A widely used technique is cross-validation, which involves dividing the dataset into `k` subsets. The ML algorithm is trained on `k-1` subsets, and its performance is evaluated on the remaining subset. These steps are repeated iteratively until all subsets have been used as validation sets.

By following these structured steps, researchers can build and evaluate effective ML models that are tailored to their specific data and objectives.

## 4. A Brief Glossary of Artificial Intelligence

| Name                  | Acronym | Definition                                                                                                                                                                                                                                     |
|-------------------------------|-----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Algorithm                     | -               | A sequence of operations or tasks to perform following a certain logic to solve a problem or answer a question.                                                                                                                                |
| Machine Learning              | ML              | "A field of study that gives computers the ability to learn without being explicitly programmed" (Arthur Lee Samuel, 1959).                                                                                                                     |
| Deep Learning                 | DL              | A subfield of machine learning that uses artificial neural networks as algorithms.                                                                                                                                                               |
| Kernel Trick                  | -               | A method that allows solving a non-linear problem using a linear classifier by projecting the data into a higher-dimensional space.                                                                                                              |
| Classifier                    | -               | An algorithm capable of classifying data.                                                                                                                                                                                                       |
| Linear Classifier             | -               | Classification based on a linear combination of variables, where data can be separated by a hyperplane (linearly separable data).                                                                                                                |
| Non-Linear Classifier         | -               | Classification based on a non-linear combination of variables.                                                                                                                                                                                  |
| Hidden Layer                  | -               | An intermediate layer between the input and output layers in a neural network.                                                                                                                                                                   |
| Gradient Descent              | -               | An optimization algorithm that minimizes the cost function by finding an optimal point corresponding to minimal error.                                                                                                                           |
| Cost Function                 | -               | A mathematical function that measures the discrepancy between predictions and actual values.                                                                                                                                                     |
| Decision Boundary             | -               | A boundary used to classify data (e.g., a hyperplane).                                                                                                                                                                                           |
| Artificial Intelligence       | AI              | The discipline of reproducing human intelligence through digital simulation on computers.                                                                                                                                                        |
| Natural Language              | NL              | The ability of computer systems to understand, interpret, and generate human language in a way similar to human communication.                                                                                                                   |
| Big Data                      | -               | Large, diverse datasets generated exponentially over time.                                                                                                                                                                                       |
| Model                         | -               | In machine learning, the representation learned from data by the algorithm.                                                                                                                                                                      |
| Artificial Neuron             | -               | Also called a formal or artificial neuron, it is an algorithm capable of performing calculations to detect features in input data and classify them into two output groups. It is essentially a binary classifier.                                 |
| Artificial Neural Networks    | ANN             | A network of interconnected artificial neurons.                                                                                                                                                                                                  |
| Chatbot                       | -               | A software program capable of conversing with a user (e.g., ChatGPT - Generative Pre-trained Transformer).                                                                                                                                       |
| Data Sciences                 | -               | A field involving techniques, methods, and tools for extracting meaningful insights from raw data.                                                                                                                                               |
| Underfitting                  | -               | Describes a model that generalizes poorly because it is not well-fitted to the training data.                                                                                                                                                    |
| Overfitting                   | -               | Describes a model that generalizes poorly because it is too tailored to the training data, often due to insufficiently representative or diverse datasets.                                                                                        |
| Expert System                 | -               | A set of predefined rules designed to solve a specific problem.                                                                                                                                                                                  |
| Natural Language Processing   | NLP             | A set of techniques aimed at creating computational tools for processing natural language.                                                                                                                                                        |
| Computer Vision               | -               | A field of artificial intelligence focusing on enabling computers to process and analyze images or videos, inspired by the human visual system.                                                                                                   |

-------------------------------------------------------
**Dr Alexandre Godmer, Dr Quentin Giai-Gianetto**