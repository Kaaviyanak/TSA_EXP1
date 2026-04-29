# Ex.No: 01A PLOT A TIME SERIES DATA
###  Date: 28/04/2026
### Name : Kaaviyan K
### Reg no : 212224240066

# AIM:
To Develop a python program to Plot a time series data (population/ market price of a commodity
/temperature.
# ALGORITHM:
1. Import the required packages like pandas and matplot
2. Read the dataset using the pandas
3. Calculate the mean for the respective column.
4. Plot the data according to need and can be altered monthly, or yearly.
5. Display the graph.
# PROGRAM:

```py

from matplotlib import pyplot as plt
import pandas as pd


df = pd.read_csv("user_behavior_timeseries.csv")
df.head()
df.tail()

df.columns = df.columns.str.strip()

df['Date'] = pd.date_range(start='2024-01-01', periods=len(df))


df['Date'] = pd.to_datetime(df['Date'])

df.set_index('Date', inplace=True)

df_resampled = df['App Usage Time'].resample('D').mean()

df_resampled.plot(kind='line', label='App Usage Time')

plt.title('Time Series Plot of App Usage')
plt.xlabel('Date')
plt.ylabel('Usage Time (minutes)')
plt.legend()
plt.grid(True)
plt.show()

```


# OUTPUT:
<img width="722" height="566" alt="image" src="https://github.com/user-attachments/assets/dd8aed9b-f48a-450b-914b-588bb0285060" />


# RESULT:
Thus we have created the python code for plotting the time series of given data.
