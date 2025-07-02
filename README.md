# InformationGain Library

This module helps you calculate **Information Gain** for categorical data using **entropy**.

---
## Installation
```
pip install InformationGain==1.0.0
```

---
## Pypi
https://pypi.org/project/InformationGain/1.0.0/
---
## Class
`InfoGain.calculate(data, target, fIndex=True)`

---

## Parameters

| Parameter | Type      | Description                                                      | Default  |
|-----------|-----------|------------------------------------------------------------------|----------|
| `data`    | DataFrame | Dataset in pandas dataframe format                               | Required |
| `target`  | String    | Output column (the target variable)                              | Required |
| `fIndex`  | Boolean   | Specifies if the first column of the dataset is an index column  | True     |

---

## Description
- Calculates **Information Gain** for each feature/column in the dataset with respect to the target column.
- Useful for decision tree splitting based on entropy.
- **Returns:** A dictionary where keys are feature/column names and values are their corresponding Information Gain with respect to the target column.

---

## Example Usage
```python
from InformationGain import InfoGain

import pandas as pd

# Load dataset
data = pd.read_csv('your_dataset.csv')

# Initialize
ig = InfoGain()

# Calculate Information Gain
result = ig.calculate(data, target='Output', fIndex=True)

print(result)
# Example Output:
# {'Feature1': 0.25, 'Feature2': 0.18, 'Feature3': 0.0}
