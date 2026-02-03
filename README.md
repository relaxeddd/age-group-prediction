# Yeti Age Group Prediction Model

## 📋 Project Overview
Development of a machine learning model for automatic age group prediction of internet service users for the "Yeti" advertising network. The project aims to create an accurate age classification tool to optimize age-based ad targeting, improve campaign relevance, and enhance advertising platform efficiency.

Research relevance is driven by the need for precise demographic targeting in digital advertising, where accurate age group identification can significantly reduce irrelevant ad impressions and increase conversion rates.

## 🔍 Machine Learning Problem Statement

### **Task Type**
**Multi-class Classification** — predicting user membership in one of 5 predefined age categories based on digital behavioral patterns.

### **Learning Type**
**Supervised Learning** — based on labeled user data with known age groups and their corresponding digital footprints.

### **Target Variable**
Age group category — multiclass feature with 5 distinct classes representing different age ranges.

## 📊 Quality Metrics & Success Criteria

### **Primary Metric:**
**F1-macro** — averaged F1-score across all classes, accounts for category imbalance

### **Additional Metrics:**
- **Precision-macro** — averaged precision across classes
- **Recall-macro** — averaged recall across classes

### **Success Criteria**
- **Model Quality**: F1-macro ≥ 0.75 on cross-validation and test sets
- **Stability**: Consistent performance across validation strategies
- **Practicality**: Ready for integration into advertising platform

## 🔬 Validation Strategy

### **Cross-Validation**
- **Stratified K-Fold Cross-Validation** (5-10 folds) to preserve class proportions
- Ensures robust performance estimation across different data splits

### **Test Strategy**
- **Holdout Test Set** (20-30% of data) for final model evaluation
- Strict separation from training/validation data

## 🤖 Machine Learning Models

### **Planned Model Pipeline**

#### **Baseline Model:**
- **DummyClassifier** — establishes performance baseline for comparison

#### **Linear Models:**
- **LogisticRegression** (multiclass) — linear classification approach

#### **Non-linear Models:**
- **SVC** (Support Vector Classifier) with multiple strategies:
    - One-vs-One (OvO) decomposition
    - One-vs-Rest (OvR) decomposition

## 📈 Results & Performance

### **Target Metrics Exceeded:**
- **Achieved**: F1-macro = 0.835 on test data (Target: F1-macro ≥ 0.75)
- **Precision-macro**: 0.840
- **Recall-macro**: 0.831

### **Performance Improvement:**
- **Baseline (DummyClassifier)**: F1-macro = 0.216
- **Final Model (Optimized SVC)**: F1-macro = 0.835
- **Improvement**: 287% over baseline

## 🛠️ Technical Implementation

### **Data Processing:**
- **Data Warehouse Creation**: User-level data mart with 5,826 objects
- **Feature Engineering**: Aggregation of behavioral patterns into 43 informative features
- **Class Balance Handling**: Strategic use of class weights

### **Model Optimization:**
- **Best Model**: SVC with parameters:
    - `C=10`, `kernel='rbf'`, `gamma='auto'`
    - `class_weight=None`
    - `decision_function_shape='ovr'`
- **Feature Selection**: RFE method improved F1-macro from 0.768 to 0.793
- **Hyperparameter Tuning**: GridSearchCV optimization achieving 0.792 on CV

### **Solution Architecture:**
- **Approach**: Multiclass classification (5 age categories)
- **Best Algorithm**: Support Vector Classifier (SVC)
- **Strategy**: One-vs-Rest (OvR) decomposition
- **Regularization**: Class weight balancing for handling imbalance

## 🎯 Key Success Factors

### **Model Performance:**
- **High Accuracy**: F1-macro of 0.835 significantly exceeds target of 0.75
- **Class Balance**: Effective handling of imbalanced age group distribution
- **Feature Quality**: Well-engineered behavioral features capturing user patterns

## ✅ Conclusion

The project successfully achieved its objectives: the developed multiclass classification model demonstrates F1-macro = 0.835, significantly exceeding the target metric of 0.75. The solution is ready for integration into the "Yeti" advertising platform to optimize age-based targeting and enhance the effectiveness of advertising campaigns.
