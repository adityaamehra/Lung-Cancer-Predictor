# Tumor Size Prediction using Linear Regression

## Overview
This project implements a **tumor size prediction model** using **linear regression**. Given a set of test samples with multiple features, the model predicts the tumor size in centimeters. The model is trained on a dataset and normalizes the test samples using the mean (`mu`) and standard deviation (`sigma`) from the training set before making predictions.

## Features
- **Feature Normalization**: Ensures proper scaling of test data.
- **Bias Term Inclusion**: Uses a bias term in each test sample for correct prediction.
- **Linear Regression Model**: Utilizes a pre-trained `theta` vector for prediction.
- **Prediction Clipping**: Ensures tumor size remains within a valid range (0 to 100 cm).

## Requirements
This project requires **Python 3.x** and the following libraries:

```bash
pip install numpy
```

## File Structure
```
📂 Tumor-Size-Prediction
│── 📜 a.ipynb              # Jupyter Notebook containing the model
│── 📜 README.md            # Project Documentation
│── 📜 requirements.txt     # List of dependencies
```

## Installation & Usage
### 1. Clone the Repository
```bash
git clone https://github.com/yourusername/tumor-size-prediction.git
cd tumor-size-prediction
```

### 2. Install Dependencies
```bash
pip install -r requirements.txt
```

### 3. Run the Model
Run the Jupyter Notebook (`a.ipynb`) to test the tumor size predictions:
```python
# Import necessary libraries
import numpy as np

# Load the test dataset
X_test = np.array([...])

# Normalize the dataset using training mean (mu) and standard deviation (sigma)
X_test[:, 1:] = (X_test[:, 1:] - mu[1:]) / sigma[1:]

# Perform predictions
price = X_test @ theta
price = np.clip(price, 0, 100)

# Display results
for i, pred in enumerate(price):
    print(f"Sample {i+1} - Predicted Tumor Size: {pred:.2f} cm")
```

## Troubleshooting
- **Dimension Mismatch Error**: Ensure `mu`, `sigma`, and `theta` are correctly shaped to match `X_test`.
- **Invalid Normalization**: Exclude the bias term while normalizing features (`mu[1:]` and `sigma[1:]`).
- **Incorrect Predictions**: Ensure `theta` was obtained from a properly trained model.

## Contributing
Feel free to submit pull requests to improve the project. For major changes, open an issue first to discuss the proposal.

## License
This project is licensed under the **MIT License**.
