# Predictive Maintenance with Custom Decision Trees
## Overview
This repository demonstrates the application of supervised machine learning techniques, focusing on decision trees and ensemble methods, to predict equipment failures using historical sensor data.

## Repository Structure
sklearn_trees.ipynb: Implements standard machine learning models using scikit-learn, including Decision Tree, Random Forest, and Gradient Boosting classifiers.

custom_trees.ipynb: Develops custom decision tree classifiers from scratch, utilizing entropy-based splits and information gain.

data/maintenance.csv: Contains 500 records of machine sensor readings and operational metrics, labeled with failure outcomes.

## Methodology
### Data Preprocessing:

Transformed failure outcomes into a binary variable indicating the occurrence of failure within a future window.

Applied one-hot encoding for categorical variables and standardized numerical features.

Addressed class imbalance using SMOTE (Synthetic Minority Oversampling Technique) to generate synthetic samples of the minority failure class.

Model Training and Evaluation:

Trained various classifiers, including:

Decision Tree (scikit-learn)

Random Forest

Gradient Boosting

AdaBoost

XGBoost

LightGBM

CatBoost

Evaluated models using metrics such as accuracy, precision, recall, and F1-score.

Custom Model Development:

Built decision tree classifiers from the ground up in custom_trees.ipynb, focusing on interpretability and domain-specific insights.

Benchmarked the custom models against scikit-learn implementations to assess performance improvements.

## Results
### Model	Accuracy
Decision Tree(scikit-learn):0.92

Random Forest:0.81

Gradient Boosting:0.83

AdaBoost:0.79

XGBoost:0.85

LightGBM:0.84

CatBoost	0.86

Custom Decision Tree:0.84

Custom Gradient Boosting:0.96

The custom gradient boosting model outperformed all other models, achieving an accuracy of 96%. Notably, it demonstrated superior precision and recall for the minority failure class, indicating its effectiveness in detecting rare but critical failure events.

## Feature Importance
The custom gradient boosting model identified the following features as most influential in predicting equipment failure:

Operational Hours: 0.5427

Air Temperature: 0.1312

Rotational Speed [rpm]: 0.1034

Process Temperature [K]: 0.1022

Torque [Nm]: 0.0575

Vibration Levels: 0.0562


Understanding feature importance aids in pinpointing key factors contributing to equipment failures, facilitating targeted maintenance strategies.

## Interpretability and Deployment
Visualization: Utilized plot_tree() from scikit-learn to visualize decision paths in the custom decision tree, enhancing interpretability.

SHAP Analysis: Applied SHAP (SHapley Additive exPlanations) to the custom gradient boosting model to elucidate feature contributions on a per-instance basis.

### Deployment: While not covered in this repository, models can be integrated into maintenance systems using platforms like Streamlit or Gradio for interactive user interfaces.

### Getting Started
Clone the repository:

bash
Copy
Edit
git clone [https://github.com/yourusername/predictive-maintenance.git](https://github.com/4CDA/predictive_maintenance_decisiontrees.git)
cd predictive-maintenance
Install dependencies:

bash
Copy
Edit
pip install -r requirements.txt
Run notebooks:

Open sklearn_trees.ipynb or custom_trees.ipynb in Jupyter Notebook or JupyterLab.

