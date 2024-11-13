# Ex.No: 03   COMPUTE THE AUTO FUNCTION(ACF)
### Date : 12.11.2024 
### Name : Sriram S
### Reg No : 212222240105
### AIM:
To Compute the AutoCorrelation Function (ACF) of the data for the first 35 lags to determine the model
type to fit the data.
### ALGORITHM:
1. Import the necessary packages
2. Find the mean, variance and then implement normalization for the data.
3. Implement the correlation using necessary logic and obtain the results
4. Store the results in an array
5. Represent the result in graphical representation as given below.
### PROGRAM:
```
import pandas as pd
from statsmodels.tsa.arima.model import ARIMA
import matplotlib.pyplot as plt

# Load dataset (replace 'your_data.csv' with the actual filename after uploading the dataset)
data = pd.read_csv('/content/mulgrave.csv', parse_dates=['Timestamp'], index_col='Timestamp')

# Selecting the "Q" column and dropping NaN values
data_q = data['Q'].dropna()

# Fit ARMA model (ARMA is a specific case of ARIMA with no differencing, so use ARIMA with order=(p, 0, q))
p = 1  # Order of the autoregressive part
q = 1  # Order of the moving average part
model = ARIMA(data_q, order=(p, 0, q))
arma_result = model.fit()

# Print the model summary
print(arma_result.summary())

# Plotting the original data and the fitted values
plt.figure(figsize=(10, 6))
plt.plot(data_q, label='Original')
plt.plot(arma_result.fittedvalues, color='red', label='Fitted')
plt.title('ARMA Model Fit')
plt.legend()
plt.show()

```
                        
### OUTPUT:

![download (1)](https://github.com/user-attachments/assets/8b2f5288-50b3-4694-b881-2051ac19cfab)

### RESULT:
        Thus we have successfully implemented the auto correlation function in python.
