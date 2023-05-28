# Data-Preprocessing

# AIM:

     To Perform Data Visualization on a complex dataset and save the data to a file.

# EXPLANATION:

     Data Visualization is the graphical representation of information and data. By using visual elements like charts, graphs, and maps, data visualization tools provide an accessible way to see and understand trends, outliers, and patterns in data.

# ALGORITHM:

      Step 1: Read the given data.
      
      Step 2: Clean the Data Set using Data Cleaning Process.
      
      Step 3: Apply Feature Generation and selection techniques to all the features of the data set.
      
      Step 4: Apply data visualization techniques to identify the patterns of the data.

# CODE:

import seaborn as sns

import pandas as pd

import matplotlib.pyplot as plt

df = sns.load_dataset("tips")

print(df)

df.isnull().sum()

plt.figure(figsize=(5,5))

plt.title("Data with Outliers")

df.boxplot()

plt.show()

plt.figure(figsize=(5,5))

cols = ['size','tip','total_bill']

Q1 = df[cols].quantile(0.25)

Q3 = df[cols].quantile(0.75)

IQR = Q3 - Q1

df = df[~((df[cols] < (Q1 - 1.5 * IQR)) |(df[cols] > (Q3 + 1.5 * IQR))).any(axis=1)]

plt.title("Dataset after removing outliers")

df.boxplot()

plt.show()

sns.barplot(x=df['day'], y=df['total_bill'], hue=df['day'])

plt.legend(loc="center")

plt.title("Highest Total Bill Amount by day of the week")

plt.show()

sns.boxplot(x=df['smoker'], y=df['tip'], hue=df['smoker'])

plt.title("Average Tip Amount given by smokers and non-smokers")

df["tip_percent"] = df["tip"] / df["total_bill"]

sns.scatterplot(x=df['size'],y=df['tip_percent'],data=df)

plt.title("Tip Percentage by Dining Party Size")

sns.boxplot(x=df['sex'], y=df['tip'],hue=df['sex'])

plt.title("Tips based on gender")

sns.scatterplot(x=df['day'],y=df['total_bill'],hue=df['day'])

plt.legend(loc="best")

plt.title("Total bill amount by day of the week")

sns.histplot(data=df, x="total_bill", hue="time", element="step", stat="density")

plt.title("Distribution of Total Bill Amounts by Time of Day")

plt.show()

sns.barplot(x=df['size'],y=df['total_bill'],hue=df['size'])

plt.title("Average Total Bill Amount by Dining Party Size")

plt.show()

sns.boxplot(x="day", y="tip", data=df)

plt.title("Tip Amount by Day of Week")

plt.show()

sns.violinplot(x="time", y="tip", data=df)

plt.title("Tip Amount by Time of Day")

plt.show()

sns.scatterplot(x="total_bill", y="tip", data=df)

plt.title("Correlation between Tip Amount and Total Bill Amount")

plt.show()

# OUTPUT:

![image](https://github.com/akshitha-ks/Data-Preprocessing/assets/123535064/f7a17a13-486a-4ab1-935e-63d0243233a3)

![image](https://github.com/akshitha-ks/Data-Preprocessing/assets/123535064/5949b026-65b1-4e73-97c4-0e5cf1437e1e)

![image](https://github.com/akshitha-ks/Data-Preprocessing/assets/123535064/9d1d8720-a4cd-4355-8261-ef50d19e0198)

![image](https://github.com/akshitha-ks/Data-Preprocessing/assets/123535064/fb435791-7b11-4c18-a1bb-1b93c15ec768)

![image](https://github.com/akshitha-ks/Data-Preprocessing/assets/123535064/19256a74-7c90-4e25-beb3-5d8f8e87bf1e)

![image](https://github.com/akshitha-ks/Data-Preprocessing/assets/123535064/9497b2a5-5be3-405f-b9b5-ccd72c2317c9)

 ![image](https://github.com/akshitha-ks/Data-Preprocessing/assets/123535064/ac9039d0-2917-4bae-9b4c-31ccbb05affe)

![image](https://github.com/akshitha-ks/Data-Preprocessing/assets/123535064/bf04964f-5703-45d8-8004-300feed1d5ff)

![image](https://github.com/akshitha-ks/Data-Preprocessing/assets/123535064/41a41389-f60d-4521-be93-36872d409cfc)

![image](https://github.com/akshitha-ks/Data-Preprocessing/assets/123535064/e3ce1052-e21e-4c63-81dd-10275dfebca9)

![image](https://github.com/akshitha-ks/Data-Preprocessing/assets/123535064/10f7a3c7-9a74-4fab-8a5d-6962b70b39b0)

![image](https://github.com/akshitha-ks/Data-Preprocessing/assets/123535064/752128ff-deba-4ce4-800b-378ea36aeed4)

![image](https://github.com/akshitha-ks/Data-Preprocessing/assets/123535064/d79a733c-fe80-4103-8bff-e61990f21314)

![image](https://github.com/akshitha-ks/Data-Preprocessing/assets/123535064/ec18455b-94a6-4854-8e91-4c32566c405c)

# RESULT:

      Thus, the Feature Visualization for the given datasets had been executed successfully.
