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
import matplotlib.pyplot as plt
from statsmodels.graphics.tsaplots import plot_acf

# Load dataset (replace 'your_data.csv' with the actual filename)
data = pd.read_csv('/content/mulgrave.csv', parse_dates=['Timestamp'], index_col='Timestamp')

# Selecting the "Q" column and dropping NaN values
data_q = data['Q'].dropna()

# Plot ACF for the first 35 lags
plot_acf(data_q, lags=35)
plt.title('ACF of Q for the first 35 lags')
plt.show()
```
                        
### OUTPUT:

![download (2)](https://github.com/user-attachments/assets/12c3c0fb-8617-400e-8f14-edd21ec76e8a)

### RESULT:
        Thus we have successfully implemented the auto correlation function in python.
