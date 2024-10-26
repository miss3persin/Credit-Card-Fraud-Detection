# Credit Card Fraud Detection Model  

This project implements a **Credit Card Fraud Detection Model** using **Logistic Regression**. The goal is to detect fraudulent transactions from legitimate ones based on transaction data. Fraud detection is a crucial task to prevent financial losses for individuals and organizations.

---

## Overview  
The dataset contains records of transactions, and each transaction is labeled as **fraudulent (1)** or **legitimate (0)**. This model provides a quick and effective way to classify incoming transactions as fraudulent or non-fraudulent.

---

## Dataset Description  
The dataset used for this project was obtained from Kaggle:  
[Credit Card Fraud Detection Dataset](https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud)  

The dataset consists of numerical input features that are transformed through PCA (Principal Component Analysis) for privacy reasons. It includes 30 columns such as:

| Feature | Description                        |
|---------|------------------------------------|
| V1-V28  | PCA-transformed features          |
| Time    | Time elapsed between transactions |
| Amount  | Transaction amount                |
| Class   | Target variable (1 = Fraud, 0 = Legit) |

---

## Model Performance  
- **Training Accuracy:** 94.66%  
- **Testing Accuracy:** 91.88%  

---

## Usage  
Here’s how you can use the model to detect fraudulent transactions:

```python
import numpy as np

# Input data: (Time, V1, V2, ..., V28, Amount)
input_data = (
    0, -1.3598071336738, -0.0727811733098497, 2.53634673796914, 
    1.37815522427443, -0.338320769942518, 0.462387777762292, 
    0.239598554061257, 0.0986979012610507, 0.363786969611213, 
    0.0907941719789316, -0.551599533260813, -0.617800855762348, 
    -0.991389847235408, -0.311169353699879, 1.46817697209427, 
    -0.470400525259478, 0.207971241929242, 0.0257905801985591, 
    0.403992960255733, 0.251412098239705, -0.018306777944153, 
    0.277837575558899, -0.110473910188767, 0.0669280749146731, 
    0.128539358273528, -0.189114843888824, 0.133558376740387, 
    -0.0210530534538215, 149.62
)

# Convert input data to a numpy array
input_as_np_array = np.asarray(input_data)

# Reshape data for prediction (single instance)
input_reshaped = input_as_np_array.reshape(1, -1)

# Predict the transaction status
prediction = model.predict(input_reshaped)

# Display the result
if prediction == 0:
    print('The Transaction is Legit')
else:
    print('The Transaction is a Fraud')
```

---

## Conclusion  
This Credit Card Fraud Detection Model provides a reliable way to identify fraudulent transactions. While the model performs well on the dataset, real-world applications may require further optimization and regular updates to maintain accuracy as fraud patterns evolve.
