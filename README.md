# Credit Card Fraud Detection

A machine learning project that implements and compares multiple unsupervised anomaly detection algorithms to identify fraudulent credit card transactions.

## Project Overview

This project analyzes credit card transaction data to detect fraudulent activities using unsupervised learning techniques. The dataset contains transactions made by European cardholders in September 2013, with features transformed through PCA for confidentiality.

## Objectives

- Perform exploratory data analysis on imbalanced fraud detection dataset
- Implement and compare multiple anomaly detection algorithms
- Evaluate model performance using appropriate metrics for imbalanced datasets
- Provide insights into transaction patterns and fraud characteristics

## Dataset Description

- **Total Transactions**: 284,807
- **Features**: 31 (Time, V1-V28, Amount, Class)
- **Fraud Cases**: 492 (0.17% of all transactions)
- **Normal Cases**: 284,315 (99.83% of all transactions)
- **Class Distribution**: Highly imbalanced dataset

### Feature Details
- `Time`: Seconds elapsed between transactions
- `V1-V28`: Principal components obtained through PCA transformation
- `Amount`: Transaction amount
- `Class`: Target variable (0 = Normal, 1 = Fraud)

## Exploratory Data Analysis

### Key Findings
- **Class Imbalance**: Only 0.17% of transactions are fraudulent
- **Transaction Amounts**: 
  - Fraud transactions: Mean $122.21, Max $2,125.87
  - Normal transactions: Mean $88.29, Max $25,691.16
- **No Missing Values**: Complete dataset with 284,807 records
- **Feature Correlations**: Analyzed through correlation heatmap

## Machine Learning Models

Three unsupervised anomaly detection algorithms were implemented and compared:

### 1. Isolation Forest
- **Accuracy**: 99.74%
- **Precision (Fraud)**: 0.26
- **Recall (Fraud)**: 0.27
- **F1-Score (Fraud)**: 0.26

### 2. Local Outlier Factor (LOF)
- **Accuracy**: 99.66%
- **Precision (Fraud)**: 0.02
- **Recall (Fraud)**: 0.02
- **F1-Score (Fraud)**: 0.02

### 3. One-Class SVM
- **Accuracy**: 37.09%
- **Precision (Fraud)**: 0.00
- **Recall (Fraud)**: 0.67
- **F1-Score (Fraud)**: 0.00

## Results Analysis

**Best Performing Model**: Isolation Forest
- Achieved the highest overall accuracy and balanced performance
- Better precision-recall trade-off for fraud detection
- Most suitable for production deployment

**Model Comparison Insights**:
- Isolation Forest: Best balance between precision and recall
- LOF: High accuracy but poor fraud detection capability
- One-Class SVM: High recall but extremely poor precision

## Technologies Used

- **Python 3.x**
- **Libraries**:
  - `pandas` - Data manipulation and analysis
  - `numpy` - Numerical computations
  - `scikit-learn` - Machine learning algorithms
  - `matplotlib` & `seaborn` - Data visualization
  - `scipy` - Scientific computing

## Project Structure

```
fraud-detection/
│
├── fraud_detection.py          # Main analysis script
├── output.txt                  # Model evaluation results
├── README.md                   # Project documentation
└── data/
    └── creditcard.csv         # Dataset (not included due to size)
```

## Getting Started

### Prerequisites
```bash
pip install pandas numpy scikit-learn matplotlib seaborn scipy
```

### Running the Analysis
1. Download the credit card fraud dataset
2. Update the file path in the script
3. Run the analysis:
```bash
python fraud_detection.py
```

## Key Code Features

- **Data Preprocessing**: Handling imbalanced dataset
- **Visualization**: Transaction distribution analysis and correlation heatmaps
- **Model Implementation**: Three different anomaly detection approaches
- **Performance Evaluation**: Comprehensive metrics including precision, recall, and F1-score
- **Contamination Handling**: Adaptive contamination parameter based on fraud ratio

## Business Impact

This fraud detection system can help financial institutions:
- Reduce financial losses from fraudulent transactions
- Improve customer trust and security
- Optimize fraud investigation resources
- Minimize false positive rates

## Future Improvements

- **Feature Engineering**: Create additional features from existing data
- **Ensemble Methods**: Combine multiple algorithms for better performance
- **Deep Learning**: Implement neural network-based approaches
- **Real-time Processing**: Develop streaming fraud detection capabilities
- **Cost-Sensitive Learning**: Incorporate business costs of false positives/negatives

## Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/improvement`)
3. Commit your changes (`git commit -am 'Add new feature'`)
4. Push to the branch (`git push origin feature/improvement`)
5. Create a Pull Request

## Acknowledgments

- Dataset provided by Kaggle Credit Card Fraud Detection Challenge
- Machine learning algorithms implemented using scikit-learn
- Inspiration from various fraud detection research papers

