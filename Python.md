# Python
## Data Cleaning
``` python
import pandas as pd
import numpy as np
from sklearn.preprocessing import StandardScaler
import seaborn as sns
import matplotlib.pyplot as plt

# Load the dataset
df = pd.read_csv('credit_card_transactions.csv')

# Data Cleaning
# Remove duplicates
df.drop_duplicates(inplace=True)

# Check for missing values
missing_values = df.isnull().sum()
print("Missing Values:\n", missing_values)

# Handle missing values if any (for this example, we'll assume there are no missing values)

# Convert 'TransactionDate' to datetime
df['TransactionDate'] = pd.to_datetime(df['TransactionDate'])

# Convert categorical columns to category type
categorical_columns = ['MerchantCategory', 'CardType', 'Gender']
for col in categorical_columns:
    df[col] = df[col].astype('category')

# Summary of the cleaned data
print("Data Types:\n", df.dtypes)
print("Summary Statistics:\n", df.describe(include='all'))
```

## Exploratory Data Analysis
``` python
# Exploratory Data Analysis (EDA)
# Distribution of Transaction Amount
plt.figure(figsize=(10, 6))
sns.histplot(df['TransactionAmount'], kde=True, bins=30)
plt.title('Distribution of Transaction Amount')
plt.xlabel('Transaction Amount')
plt.ylabel('Frequency')
plt.show()

# Distribution of Age
plt.figure(figsize=(10, 6))
sns.histplot(df['Age'], kde=True, bins=30)
plt.title('Distribution of Age')
plt.xlabel('Age')
plt.ylabel('Frequency')
plt.show()

# Transaction Amount by Merchant Category
plt.figure(figsize=(12, 6))
sns.boxplot(x='MerchantCategory', y='TransactionAmount', data=df)
plt.title('Transaction Amount by Merchant Category')
plt.xlabel('Merchant Category')
plt.ylabel('Transaction Amount')
plt.xticks(rotation=45)
plt.show()

# Correlation heatmap
plt.figure(figsize=(10, 8))
sns.heatmap(df.corr(), annot=True, cmap='coolwarm', fmt='.2f')
plt.title('Correlation Heatmap')
plt.show()
```
