# Vanilla_Steel
Task 1
# Inventory Data Processing

## Overview

This project processes supplier inventory data using Python and Pandas. The data from multiple suppliers is cleaned, merged, and analyzed to generate insights.

## Features

- Load inventory data from multiple Excel files.
- Handle missing values and inspect dataset structure.
- Merge datasets into a single CSV file.
- Perform exploratory data analysis (EDA) on numerical and categorical data.
- Rename columns for better readability.

## Installation

Ensure you have Python installed along with the required dependencies.

```bash
pip install pandas openpyxl
```

## Usage

### Step 1: Load Supplier Data

```python
import pandas as pd
supplier1 = pd.read_excel('supplier_data_1.xlsx')
supplier2 = pd.read_excel('supplier_data_2.xlsx')
```

### Step 2: Check for Missing Values

```python
print(supplier1.isnull().sum())
print(supplier2.isnull().sum())
```

### Step 3: Merge Datasets

```python
inventory_dataset = pd.concat([supplier1, supplier2], ignore_index=True)
inventory_dataset.to_csv('inventory_dataset.csv', index=False)
```

### Step 4: Analyze Data

```python
print(inventory_dataset.describe())
print(inventory_dataset.describe(include='O'))
print(inventory_dataset.info())
```

### Step 5: Rename Columns for Readability

```python
inventory_dataset.rename(columns={
    'Nenndicke NNN.NN mm mit Dezimalpunkt': 'Thickness (mm)',
    'Breite': 'Width (mm)',
    'Gewicht (kg)': 'Weight (kg)',
    'NOMINAL_THICKNESS_MM': 'Thickness (mm)',
    'WIDTH_MM': 'Width (mm)',
    'MASS_MIN_KG': 'Weight (kg)'
}, inplace=True)
```

## Output

- **inventory\_dataset.csv**: The cleaned and merged dataset.
- Console output with dataset insights and structure.

## License

This project is open-source and free to use.

