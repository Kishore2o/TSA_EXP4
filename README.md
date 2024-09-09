## DEVELOPED BY : Kishore S
## REG NO : 212222240050
# Ex.No:04   FIT ARMA MODEL FOR TIME SERIES
# Date: 


### AIM:
To implement ARMA model in python.
### ALGORITHM:
1. Import necessary libraries.
2. Set up matplotlib settings for figure size.
3. Define an ARMA(1,1) process with coefficients ar1 and ma1, and generate a sample of 1000

data points using the ArmaProcess class. Plot the generated time series and set the title and x-
axis limits.

4. Display the autocorrelation and partial autocorrelation plots for the ARMA(1,1) process using
plot_acf and plot_pacf.
5. Define an ARMA(2,2) process with coefficients ar2 and ma2, and generate a sample of 10000

data points using the ArmaProcess class. Plot the generated time series and set the title and x-
axis limits.

6. Display the autocorrelation and partial autocorrelation plots for the ARMA(2,2) process using
plot_acf and plot_pacf.
### PROGRAM:
```
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
from statsmodels.tsa.arima_process import ArmaProcess
from statsmodels.graphics.tsaplots import plot_acf, plot_pacf
import warnings
warnings.filterwarnings('ignore')

# Load the dataset
data = pd.read_csv('/content/NFLX.csv')

# Use the 'Close' price column
close_prices = data['Close'].dropna()

plt.rcParams['figure.figsize'] = [10, 7.5]

# Simulate ARMA(1,1) Process
ar1 = np.array([1, 0.33])
ma1 = np.array([1, 0.9])
ARMA_1 = ArmaProcess(ar1, ma1).generate_sample(nsample=len(close_prices))
plt.plot(ARMA_1)
plt.title('Simulated ARMA(1,1) Process')
plt.xlim([0, 200])
plt.show()

# Plot ACF and PACF for ARMA(1,1)
plot_acf(ARMA_1)
plot_pacf(ARMA_1)

# Simulate ARMA(2,2) Process
ar2 = np.array([1, 0.33, 0.5])
ma2 = np.array([1, 0.9, 0.3])
ARMA_2 = ArmaProcess(ar2, ma2).generate_sample(nsample=len(close_prices) * 10)
plt.plot(ARMA_2)
plt.title('Simulated ARMA(2,2) Process')
plt.xlim([0, 200])
plt.show()

# Plot ACF and PACF for ARMA(2,2)
plot_acf(ARMA_2)
plot_pacf(ARMA_2)
```

### OUTPUT:

![image](https://github.com/user-attachments/assets/3f6ad94b-caec-49ef-8c4f-ee23bf8aab00)
![image](https://github.com/user-attachments/assets/1583313d-c170-4076-9b03-17274d3287d4)
![image](https://github.com/user-attachments/assets/dbb53360-4df1-4ef4-97a0-a79a3473a29d)
![image](https://github.com/user-attachments/assets/11ee5a2b-0bfd-4fdb-98e8-cdf9216bff7b)
![image](https://github.com/user-attachments/assets/ca987e17-d165-4438-a58e-5307c0184f33)
![image](https://github.com/user-attachments/assets/3a3ff299-2cff-4e7c-89d1-488b68be398b)





## RESULT:
Thus, a python program is created to fir ARMA Model successfully.
