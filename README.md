## Linear Regression: Jupyter Notebook vs. Azure Machine Learning
# Project Overview
This project aims to compare the development and performance of a Linear Regression model using two different environments: Jupyter Notebook (within Jupyter Lab) and Azure Machine Learning Designer. Additionally, I will utilize Azure Automated ML (AutoML) to evaluate multiple algorithms and identify the best-performing model for the given dataset.

The dataset used for this project focuses on Social Anxiety, a subject that has gained increased relevance in the post-COVID-19 era. With the rise of remote work and reduced face-to-face interactions, many individuals are experiencing heightened levels of social discomfort and isolation. Social media platforms, while offering connection, may also contribute to social anxiety through excessive screen time, comparison culture, and digital fatigue.

# Dataset Information
The dataset consists of responses from real-world surveys and observational studies exploring psychological and behavioral indicators of social anxiety. It has been cleaned and preprocessed for analytical purposes.

# Disclaimer:
This dataset is intended strictly for educational and research purposes. It should not be used for clinical diagnosis or treatment. Although derived from real-world sources, it does not substitute for professional mental health evaluation or care.

# Personal Motivation
I believe that Machine Learning and AI have the potential to significantly impact healthcare, particularly in diagnostics and mental health. However, I also approach the modeling of human behavior with a degree of skepticism, especially given the complexity and nuance involved in psychological conditions. This project serves as both a technical exercise and a critical exploration of the role of ML in analyzing social and behavioral data.

# Jupyter Notebook
In the Jupyter Notebook environment, I performed a comprehensive preprocessing workflow to prepare the dataset for training with a Linear Regression model. This process included one-hot encoding of categorical variables, normalization of numerical features, and a thorough inspection for outliers to ensure data quality and consistency.

  - [Linear-Regression-JupyterNotebook](Linear_Rgression_JupyerNotebook_Social_Anxiety.ipynb) 

I also placed strong emphasis on data visualization, as it is a critical step in understanding the underlying structure and relationships within the dataset. Specifically, I plotted each independent variable against the target variable to assess potential correlations, trends, and patterns. This exploratory step not only informed feature selection but also provided valuable insights into variable distributions and model interpretability.

# Azure Machine Learning - Designer tool

The purpose of utilizing Azure Machine Learning Designer is to evaluate how effectively the no-code, drag-and-drop interface performs in comparison to a manually coded Linear Regression model developed in a traditional programming environment. This comparison aims to assess both model performance and workflow efficiency between automated tools and custom-coded approaches.

# Azure Automated ML

Azure Automated ML provides valuable insights by automatically identifying the most suitable model for a given dataset. It streamlines the model development process by evaluating a wide range of algorithms and hyperparameter combinations, significantly reducing the time and effort required for manual experimentation. In addition to model selection, AutoML offers detailed performance metrics for each candidate model, enabling data-driven decisions and accelerating the path to deploying high-performing solutions

## Project issues:
- In the dataset, the Gender column consisted of three distinct categories: 'Male', 'Female', and 'Other'. Notably, the 'Other' category represented over one-third of the total observations. Due to its significant representation, I chose not to drop this category, as doing 
  so would have resulted in the loss of a substantial portion of the data and potential bias.

  To prepare this categorical feature for modeling, I applied one-hot encoding, which generated three binary indicator columns—one for each category. However, during model training, I observed unusually large coefficients associated with the encoded gender variables. This 
  behavior is a classic indication of multicollinearity, a condition where independent variables are highly correlated, causing instability in regression coefficient estimates.

  This issue arises because one-hot encoding all categories of a variable introduces perfect linear dependency (dummy variable trap). To resolve this issue I removed one of the columns 'gender Other' from the dataset.

- Feature selection presented a notable challenge during the modeling process. While visualizing the relationship between each independent variable and the target variable, some features appeared to have weak or negative correlations. Despite this, domain knowledge 
  indicated that these features were likely to be important.

  To assist with feature selection, I applied a Lasso regression model, which uses L1 regularization to shrink less important feature coefficients to zero. However, this approach negatively impacted model performance—some genuinely valuable features were penalized too 
  heavily, resulting in their exclusion from the model. This outcome highlighted a limitation of automated regularization techniques, particularly when dealing with features that may have non-linear or interaction effects not captured through simple correlation analysis.
