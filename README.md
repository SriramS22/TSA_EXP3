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
       SARIMAX Results                                
==============================================================================
Dep. Variable:                      Q   No. Observations:                19409
Model:                 ARIMA(1, 0, 1)   Log Likelihood              -96043.714
Date:                Tue, 12 Nov 2024   AIC                         192095.428
Time:                        16:17:57   BIC                         192126.922
Sample:                             0   HQIC                        192105.747
                              - 19409                                         
Covariance Type:                  opg                                         
==============================================================================
                 coef    std err          z      P>|z|      [0.025      0.975]
------------------------------------------------------------------------------
const         53.2083      4.209     12.642      0.000      44.959      61.458
ar.L1          0.9167      0.002    439.359      0.000       0.913       0.921
ma.L1          0.3431      0.005     63.638      0.000       0.333       0.354
sigma2      1163.1746      6.566    177.142      0.000    1150.305    1176.044
===================================================================================
Ljung-Box (L1) (Q):                  33.47   Jarque-Bera (JB):             23021.14
Prob(Q):                              0.00   Prob(JB):                         0.00
Heteroskedasticity (H):               0.85   Skew:                            -0.79
Prob(H) (two-sided):                  0.00   Kurtosis:                         8.10
===================================================================================

![download (1)](https://github.com/user-attachments/assets/8b2f5288-50b3-4694-b881-2051ac19cfab)

### RESULT:
        Thus we have successfully implemented the auto correlation function in python.
