# Sentiment Analysis for Auto Reviews

## Abstract

This project designs, implements, and evaluates classifiers to recognize sentiment in automotive e-commerce reviews. We present two approaches: an unsupervised clustering method using K-means and a discriminative classification method using XGBoost. Our experiments result in models that demonstrate high silhouette scores for K-means and very high accuracies for both F1 scores and XGBoost. The results show that both models are effective in sentiment classification, but each exhibits advantages over the others with respect to clustering quality and predictive accuracy. The report further explores all preprocessing steps, model selection rationale, and performance analysis, providing complete insight into practical applications in sentiment analysis.

---

## Table of Contents

1. [Introduction](#introduction)
2. [Features](#features)
3. [Installation](#installation)
4. [Usage](#usage)
5. [Analysis Highlights](#analysis-highlights)
6. [Contributing](#contributing)
7. [License](#license)

---

## Introduction

In this project, we selected two sentiment classification models: 
- **K-means Clustering**: An unsupervised learning algorithm that divides input data into clusters based on feature similarity.
- **XGBoost**: A powerful and scalable machine learning algorithm for solving classification and regression problems using gradient boosting procedures.

The goal is to analyze patterns from the data without needing labeled samples (K-means) and to leverage labeled data for high accuracy and F1 scores (XGBoost). 

---

## Features

This project includes the following features:
- **Data Preprocessing**: Text cleaning, lemmatization, and TF-IDF vectorization.
- **Unsupervised Learning**: K-means clustering to identify natural groupings within the dataset.
- **Supervised Learning**: XGBoost classification to predict sentiment labels.
- **Evaluation Metrics**: Silhouette scores for K-means and accuracy/F1 scores for XGBoost.
- **Visualization**: UMAP for dimensionality reduction and visualization of clusters.

---

## Installation

To run this project locally, follow these steps:

### Prerequisites
- Install [Python](https://www.python.org/) (preferably Python 3.8 or higher).
- Ensure you have Git installed: [Git Downloads](https://git-scm.com/downloads).

### Clone the Repository
```bash
git clone https://github.com/your-username/sentiment-analysis-auto-reviews.git
cd sentiment-analysis-auto-reviews
```

### Install Required Libraries
Run the following commands in your terminal to install the necessary libraries:
```bash
pip install numpy pandas scikit-learn xgboost umap-learn
```

### Load the Dataset
Place the dataset file in the root directory of the project. Ensure the file path matches the one specified in the script. I have added all the datasets in the data folder.

---

## Usage

1. Open the Python script (`sentiment_analysis.py`) in your preferred IDE.
2. Set the working directory to the project folder:
   ```python
   import os
   os.chdir("path/to/sentiment-analysis-auto-reviews")
   ```
3. Run the script step-by-step to preprocess the data, train the models, and evaluate their performance.
4. Explore the outputs:
   - Cluster visualizations using UMAP.
   - Performance metrics (Silhouette scores, F1 scores, accuracy).

---

## Analysis Highlights

### Key Findings
1. **K-means Clustering**:
   - High Silhouette scores (0.8627 for training, 0.8719 for validation) indicate well-formed clusters.
   - Low F1 scores (0.1677 for training, 0.1481 for validation) highlight limitations in sentiment classification tasks due to the unsupervised nature of the algorithm.
2. **XGBoost**:
   - High accuracy (96% for training, 88% for validation) and F1 scores (0.979 for training, 0.928 for validation) demonstrate superior performance in sentiment classification.
   - Effectively handles class imbalances and provides precise predictions.

### Examples
- **Text**: "Not good"  
  - Ground Truth: Negative  
  - K-means: Positive  
  - XGBoost: Positive  
- **Text**: "Hubby is happy with this, has it filled already."  
  - Ground Truth: Positive  
  - K-means: Negative  
  - XGBoost: Positive  

These examples highlight the strengths of XGBoost in capturing nuanced contextual information.

---

## Contributing

We welcome contributions to this project! If you'd like to contribute, please follow these steps:
1. Fork the repository.
2. Create a new branch (`git checkout -b feature/your-feature-name`).
3. Commit your changes (`git commit -m "Add your feature"`).
4. Push to the branch (`git push origin feature/your-feature-name`).
5. Open a pull request.

For major changes, please open an issue first to discuss your ideas.

---

## Acknowledgments

- Thanks to the creators of the Python libraries used in this project.
- Special thanks to the contributors of the automotive reviews dataset for making this analysis possible.
