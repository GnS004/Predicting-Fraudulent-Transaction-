# Fraud Detection in Financial Transactions

## Project Overview

This project focuses on developing a machine learning model to predict fraudulent transactions for a financial company. The goal is to build a robust model that can identify fraudulent behavior and provide actionable insights for fraud prevention.

## Business Context

Financial fraud is a critical concern for companies, resulting in significant monetary losses and damage to customer trust. This project aims to develop a predictive model that can:

- Identify fraudulent transactions in real-time
- Understand patterns and characteristics of fraudulent behavior
- Provide actionable insights for fraud prevention strategies
- Help the financial company minimize losses and protect customers

The fraudulent behavior in this dataset specifically involves agents taking control of customer accounts, transferring funds to another account, and then cashing out of the system.

## Dataset Information

### DATASET Link: https://drive.google.com/file/d/1YNBydtFFPtJUPCwyiz2q9JWEy1MVDIJR/view?usp=sharing

### Dataset Size
- **Format**: CSV
- **Rows**: 6,362,620 transactions
- **Columns**: 10 features
- **Time Period**: 30 days simulation (744 hours)

### Data Dictionary

| Column | Description |
|--------|-------------|
| `step` | Unit of time in the real world (1 step = 1 hour). Total steps: 744 |
| `type` | Transaction type: CASH-IN, CASH-OUT, DEBIT, PAYMENT, TRANSFER |
| `amount` | Transaction amount in local currency |
| `nameOrig` | Customer who initiated the transaction |
| `oldbalanceOrg` | Initial balance before the transaction (originator) |
| `newbalanceOrig` | New balance after the transaction (originator) |
| `nameDest` | Customer who is the recipient of the transaction |
| `oldbalanceDest` | Initial balance before the transaction (recipient). Note: No information for Merchants (starting with M) |
| `newbalanceDest` | New balance after the transaction (recipient). Note: No information for Merchants (starting with M) |
| `isFraud` | **Target variable** - Indicates fraudulent transactions (1 = fraud, 0 = legitimate) |
| `isFlaggedFraud` | Business rule flag for transfers exceeding 200,000 in a single transaction |

### Key Insights about the Data

1. **Fraudulent Behavior Pattern**: Fraudsters take control of customer accounts, transfer funds to another account, and cash out
2. **Merchant Transactions**: Merchants (accounts starting with 'M') have limited balance information
3. **Business Rule**: The company flags transactions attempting to transfer more than 200,000 as potentially illegal
4. **Temporal Nature**: Data spans 30 days with hourly granularity

## Project Requirements

### Objectives

1. **Model Development**: Build a machine learning model to predict fraudulent transactions
2. **Statistical Analysis**: Perform exploratory data analysis and statistical testing
3. **Model Evaluation**: Estimate model performance on calibration data and validate on test data
4. **Actionable Insights**: Derive business recommendations from model results
5. **Interpretation**: Focus on both fine-tuning and interpreting model outcomes

### Methodology Freedom

- Follow standard model development procedures:
  - Data exploration and preprocessing
  - Feature engineering
  - Model selection and training
  - Hyperparameter tuning
  - Model validation and testing
  - Results interpretation

### Key Focus Areas

- ⚖️ **Balance**: Both statistical rigor and creative judgment
- 🔍 **Analysis**: Deep exploratory data analysis
- 🎯 **Performance**: Model fine-tuning and optimization
- 💡 **Insights**: Actionable recommendations for the business
- 📊 **Interpretation**: Clear explanation of model behavior and predictions

## Getting Started

### Prerequisites

```bash
# Python 3.8+
# Common libraries
pandas
numpy
scikit-learn
matplotlib
seaborn
imbalanced-learn  # For handling imbalanced datasets
```

### Installation

```bash
# Clone the repository
git clone <repository-url>
cd fraud-detection-project

# Install dependencies
pip install -r requirements.txt
```

### Data Loading

```python
import pandas as pd

# Load the dataset
df = pd.read_csv('fraud_data.csv')

# Display basic information
print(df.info())
print(df.head())
```

## Project Structure

```
fraud-detection-project/
│
├── data/
│   ├── raw/                    # Raw CSV data
│   ├── processed/              # Processed datasets
│   └── Data_Dictionary.txt     # Data dictionary
│
├── notebooks/
│   ├── 01_eda.ipynb           # Exploratory Data Analysis
│   ├── 02_preprocessing.ipynb  # Data preprocessing
│   ├── 03_modeling.ipynb       # Model development
│   └── 04_evaluation.ipynb     # Model evaluation
│
├── src/
│   ├── data_processing.py      # Data preprocessing functions
│   ├── feature_engineering.py  # Feature engineering
│   ├── models.py               # Model definitions
│   └── evaluation.py           # Evaluation metrics
│
├── reports/
│   ├── figures/                # Visualizations
│   └── final_report.pdf        # Final report
│
├── README.md
└── requirements.txt
```
---
## 🔗 Connect With Me

Feel free to reach out for any questions or collaboration opportunities!

## 📄 License

This project is available for educational and portfolio purposes.

**Note**: This is a simulated dataset for educational/assessment purposes. The patterns and behaviors may not fully represent real-world fraud scenarios.
