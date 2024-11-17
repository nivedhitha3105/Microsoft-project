# Microsoft-project
Microsoft: Classifying Cybersecurity Incidents Using Machine Learning


The goal of this initiative is to enhance the operational efficiency of Security Operation Centres (SOC) by developing a machine learning model that automatically classifies cybersecurity incidents. The model categorizes incidents into three distinct groups: True Positive (TP), Benign Positive (BP), and False Positive (FP). This classification system assists SOC analysts by automating incident triage, enabling faster identification of actual threats while reducing false positives. The model is built on the GUIDE dataset provided by Microsoft, enriched with historical customer responses and supporting evidence.

Challenge Definition

SOC analysts often manually classify security incidents, a process that is both time-consuming and prone to human error. Misclassifications, especially false positives, can significantly delay responses and compromise security. The challenge is to design a machine learning model capable of automating this classification, which will help analysts prioritize and address threats more effectively.

Dataset Description

The dataset utilized in this project is the GUIDE dataset, which is structured across multiple levels of security data:

- Evidence: Contains individual data points such as IP addresses, emails, and user information.
- Alert: Groups related pieces of evidence together.
- Incident: Represents a potential security threat, summarizing alert data into an incident.

Key Features:

- 45 features, covering incident context, customer responses, and metadata.
- Target Variable: Incident classification grade (TP, BP, FP).
- Data Size: 1 million incidents, split into training (80%) and test (20%) sets.

Objectives of the Project

The primary objectives are:

- To create a machine learning model that can classify cybersecurity incidents into the categories of TP, BP, and FP.
- To fine-tune the model’s performance through effective preprocessing, feature engineering, and hyperparameter optimization.
- To minimize false positives and ensure consistent performance on unseen data.
- To evaluate the model’s effectiveness using metrics like Precision, Recall, Accuracy, and Macro-F1 Score.

Approach and Methodology

 Data Preprocessing:

- Missing Data Handling: Missing values were addressed by either imputation or removal, depending on the feature’s relevance.
- Feature Engineering: Derived new features such as day, month, and year from timestamp fields, and combined similar features to enhance predictive power.
- Encoding: Label Encoding was applied to categorical variables for better model compatibility.
- Scaling: Numerical features were scaled using StandardScaler to ensure comparability between values.

 Model Selection:

- Initial Models: We began with Decision Trees to establish baseline performance.
- Advanced Models: We tested Random Forest and XGBoost to improve classification accuracy.
- Cross-Validation: K-fold cross-validation was employed to validate model robustness and prevent overfitting.

Class Imbalance Handling:

Given the class imbalances in the dataset, bias in predictions could arise. To address this, we used:

- SMOTE (Synthetic Minority Over-sampling Technique): This technique helped to balance the class distribution by oversampling minority classes, making the model more sensitive to less-represented classes.

Model Evaluation and Results

Evaluation Metrics:

- Macro-F1 Score: Provides balanced importance across all classes (TP, BP, FP).
- Precision: Measures the accuracy of positive predictions.
- Recall: Evaluates the model's ability to correctly identify true positives.

Performance Summary:
In case of both training and test data, we got an accuracy of 92.76% while training with XGBoost algorithm whereas in decision tree and random forest the accuracy was 62% and 81% 

Insights:

- The XGBoost model showed excellent performance on the training set with a high accuracy of 92.85%.
- However, performance on the test set decreased to 92.76% after applying class imbalance techniques. This suggests that while SMOTE improved the training set balance, but not much in unseen data.
