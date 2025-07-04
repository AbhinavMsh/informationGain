# informationGain Library

This module helps you calculate **Information Gain** for both **categorical** and **continuous** features.

---
## Installation
pip install InformationGain

---
## Pypi
https://pypi.org/project/InformationGain/0.1.0/
---

## Class  
`infoGain.calculate(data, target, criteria="gini", fIndex=True)`

---

## Parameters

| Parameter  | Type      | Description                                                      | Default |
|------------|-----------|------------------------------------------------------------------|---------|
| `data`     | DataFrame | Dataset in pandas DataFrame format                              | Required |
| `target`   | String    | Output column (the target variable)                             | Required |
| `fIndex`   | Boolean   | If `True`, assumes the first column is an index and skips it     | True     |
| `criteria` | String    | Splitting criteria: `"gini"` or `"entropy"`                     | `"gini"` |

---

## Description

- Calculates **Information Gain** for each feature/column in the dataset with respect to the target column.
- Handles both **categorical** and **continuous** features:
  - For categorical features, splits data by unique values.
  - For continuous features, finds the best threshold (value) that gives maximum Information Gain.
- Supports **Gini Index** or **Entropy** as the impurity metric.
- Returns a **DataFrame** with:
  - Feature name
  - Best threshold (or `'none'` for categorical)
  - Corresponding Information Gain

---

## Returns

A `pandas.DataFrame` with columns:
- `'feature'`: Name of the feature
- `'threshold'`: Best threshold value (for continuous features), or `'none'`
- `'infogain'`: Calculated Information Gain

---

## Example Usage

```python
from informationGain import infoGain
import pandas as pd

# Load dataset
data = pd.read_csv('your_dataset.csv')

# Initialize
ig = infoGain()

# Calculate Information Gain
result = ig.calculate(data, target='Output', fIndex=True)

print(result)
# Example Output:
#     feature  threshold   infogain
# 0   outlook      none    0.246750
# 1      temp      72.5    0.029223
# 2  humidity      80.0    0.151836
# 3      wind      none    0.048127
