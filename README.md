# Asthma Disease Prediction Using Spark for Big Data Preprocessing and Statistical Analysis

## Project Overview
This project focuses on using **Apache Spark** for big data preprocessing and machine learning to predict asthma diagnosis. We explored a dataset of **2,392 patients** with detailed health information and sought to identify key factors contributing to asthma. Our goal was to leverage **Spark** for efficient data handling and statistical analysis, ensuring that the large-scale data was processed effectively to uncover meaningful insights.

### Key Technologies:
- **Apache Spark** for distributed data processing
- **Python** for machine learning model implementation
- **scikit-learn** for logistic and linear regression models
- **Hadoop Cluster** for VM configuration and Spark job submission

### Dataset:
We used the [Asthma Disease Dataset](https://www.kaggle.com/datasets/rabieelkharoua/asthma-disease-dataset/data) from Kaggle, which contains lifestyle, environmental, and clinical factors contributing to asthma diagnosis. 

---

## Implementation Steps

### 1. Virtual Machines (VMs) Setup and Spark Configuration
- Accessed Michigan Tech's **vSphere** client to manage VMs (hadoop1 and hadoop2).
- Configured network settings, including IP addresses and gateways.
- **Spark Installation**: Spark was already installed on the VMs. Configured it for distributed processing by setting hadoop1 as the master and hadoop2 as the worker node. 
- **Spark Job Submission**: Submitted preprocessing and machine learning jobs using Spark’s cluster mode.

### 2. Data Preprocessing
- **Handling Missing Values**: Filled missing values in continuous features like Age, BMI, DietQuality, and lung function metrics with their respective means.
- **Encoding Categorical Variables**: Applied **Label Encoding** to transform categorical variables (Gender, PetAllergy, FamilyHistoryAsthma, etc.) into numerical values for machine learning compatibility.
- **Scaling**: Scaled continuous features using **MinMaxScaler** to normalize them within the range [0,1], ensuring consistency across features.
- **Binning Continuous Variables**: Converted continuous features like Age, BMI, and LungFunctionFEV1 into quartiles using **KBinsDiscretizer**, simplifying the data for analysis.

### 3. Dataset Splitting
The dataset was split into training and testing sets (70% training, 30% testing) using **train_test_split** for:
- **Classification**: Predicting asthma diagnosis based on various health and lifestyle factors.
- **Regression**: Predicting lung function (LungFunctionFEV1) as a continuous outcome.

---

## Machine Learning Models

### 1. **Logistic Regression**
Implemented logistic regression to predict asthma diagnosis, achieving **94.8% accuracy** on both training and testing datasets. The model used binned and encoded features for classification.

### 2. **Linear Regression**
Linear regression was applied to predict **LungFunctionFEV1** based on continuous variables like Age, BMI, and DietQuality. The model achieved a perfect **R² score of 1.0**, suggesting strong predictive power, though potential overfitting requires further testing.

---

## Statistical Analysis

### Correlation Analysis
Performed correlation analysis to explore linear relationships between features like BMI, DietQuality, and lung function. The low correlation between variables indicated that asthma risk might involve more complex, non-linear interactions.

### Chi-Square Tests
Chi-square tests were conducted to assess the relationships between categorical variables (e.g., Gender, PetAllergy) and asthma diagnosis. Results showed no significant associations, suggesting that these variables may not serve as strong independent predictors.

### K-Means Clustering
Used **K-Means Clustering** to segment the dataset into 3 clusters based on continuous variables, identifying distinct patient profiles. This clustering could inform tailored asthma management strategies based on different health profiles.

---

## Conclusion

Despite challenges with the VM configuration and running Spark on the full cluster, the project successfully demonstrated the use of big data analytics for asthma prediction. We gained valuable experience with **Hadoop** and **Spark** for distributed processing, handling large-scale data efficiently, and building robust machine learning models. The analysis provided valuable insights into asthma risk factors and patient grouping, demonstrating the potential of Spark and big data tools in healthcare analytics.

---



---

## Acknowledgments
- **Kaggle** for providing the asthma dataset.
- **Michigan Tech** for supporting the virtual machine environment.

---

