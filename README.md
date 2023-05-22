# EX-09 Data-Visualization
# AIM:
To Perform Data Visualization on a complex dataset and save the data to a file.

# EXPLANATION:
Data visualization is the graphical representation of information and data. By using visual elements like charts, graphs, and maps, data visualization tools provide an accessible way to see and understand trends, outliers, and patterns in data.

# ALGORITHM:
# STEP-1:
Read the given Data.

# STEP-2:
Clean the Data Set using Data Cleaning Process.

# STEP-3:
Apply Feature generation and selection techniques to all the features of the data set.

# STEP-4:
Apply data visualization techniques to identify the patterns of the data.

# CODE:
import seaborn as sns

import pandas as pd

import matplotlib.pyplot as plt

tips = sns.load_dataset('tips')

tips

# Data Cleaning Process:
tips.describe()

tips.info()

tips.isnull().sum()

~tips.duplicated()

df1=tips[~tips.duplicated()]

df1

sns.boxplot(x="day", y="total_bill", hue="smoker", data=tips, linewidth=2, width=0.6, boxprops={"facecolor": "lightblue", "edgecolor": "darkblue"}, whiskerprops={"color": "black", "linestyle": "--", "linewidth": 1.5 }, capprops={"color": "black", "linestyle": "--", "linewidth": 1.5})

# Day of the week has the highest total bill amount:
sns.barplot(x=tips['day'], y=tips['total_bill'],hue=tips['sex'])

plt.xlabel('Day of the Week')

plt.ylabel('Total Bill')

plt.show()

# Average tip amount given by smokers and non-smokers:
avg_tip = tips.groupby('smoker')['tip'].mean()

p1= plt.bar(avg_tip.index, avg_tip, label='Tip', width=0.4)

plt.title('Average tip amount given by smokers and non-smokers')

plt.show()

# Tip percentage vary based on the size of the dining party:
tips["tip_per"] = tips["tip"] / tips["total_bill"]

sns.scatterplot(x="size", y="tip_per", data=tips)

plt.title("Tip Percentage by Dining Party Size")

plt.show()

# Gender tends to leave higher tips:
states=tips.loc[:,["sex","tip"]]

states=states.groupby(by=["sex"]).sum().sort_values(by="tip")

sns.barplot(x=states.index,y="tip",data=states)

plt.xlabel=("Sex")

plt.ylabel=("Tips")

plt.show()

# Relationship between the total bill amount and the day of the week:
sns.histplot(data=tips, x="total_bill", hue="time", element="step", stat="density")

plt.title("Distribution of Total Bill Amounts by Time of Day")

plt.show()

# Distribution of total bill amounts vary across different time periods:
sns.relplot(data=tips,x=tips["time"],y=tips["total_bill"],hue="time")

# Dining party size group tends to have the highest average total bill amount:
avg_total_bill = tips.groupby('size')['total_bill'].mean()

p1 = plt.bar(avg_total_bill.index, avg_total_bill, label='Total Bill', width=0.4)

plt.title('Average Total bill amount given by Dining Party Size')

plt.show()

# Distribution of tip amounts for each day of the week:
sns.relplot(data=tips,x="day",y="tip",hue="day")

# Tip amount vary based on the type of service:
sns.barplot(x=tips['time'], y=tips['tip'])

plt.xlabel=("Service")

plt.ylabel=("Tips")

plt.show()

# Correlation between the total bill amount and the tip amount:
tips.corr()

sns.heatmap(tips.corr(),annot=True)

sns.scatterplot(x="total_bill", y="tip", data=tips)

plt.title("Correlation between Tip Amount and Total Bill Amount")

plt.show()

# OUTPUT:
![Screenshot (229)](https://github.com/Dhivya-bharathi88/EX.NO-9/assets/128019999/52bde0d2-cd93-4109-95f3-418ddb198a1e)
# Data Cleaning Process:
![Screenshot (230)](https://github.com/Dhivya-bharathi88/EX.NO-9/assets/128019999/c72a2a72-4899-4118-b115-755e2eecf332)
![Screenshot (231)](https://github.com/Dhivya-bharathi88/EX.NO-9/assets/128019999/c349613f-7c20-42d9-b773-d2ac2d19a944)
![Screenshot (232)](https://github.com/Dhivya-bharathi88/EX.NO-9/assets/128019999/0e6dd441-d7bb-4b7a-b46b-7d9b63a26b1a)
![Screenshot (233)](https://github.com/Dhivya-bharathi88/EX.NO-9/assets/128019999/4f2b7d0c-d034-4503-b5be-2d46a1adb645)
# Day of the week has the highest total bill amount:
![Screenshot (234)](https://github.com/Dhivya-bharathi88/EX.NO-9/assets/128019999/0ded70ef-00f1-4806-809a-be661d1e1fcc)
# Average tip amount given by smokers and non-smokers:
![Screenshot (235)](https://github.com/Dhivya-bharathi88/EX.NO-9/assets/128019999/cde13a2c-33f9-4475-a822-1c515f5c4738)
# Tip percentage vary based on the size of the dining party:
![Screenshot (236)](https://github.com/Dhivya-bharathi88/EX.NO-9/assets/128019999/576be9de-02df-49da-be68-8b8f712dd1d4)
# Gender tends to leave higher tips:
![Screenshot (237)](https://github.com/Dhivya-bharathi88/EX.NO-9/assets/128019999/9d47ef57-03bb-4fa1-b7e3-295c59dc1664)
# Relationship between the total bill amount and the day of the week:
![Screenshot (238)](https://github.com/Dhivya-bharathi88/EX.NO-9/assets/128019999/21d26b1a-b609-4618-94dc-658e6f1586f9)
# Distribution of total bill amounts vary across different time periods:
![Screenshot (239)](https://github.com/Dhivya-bharathi88/EX.NO-9/assets/128019999/eecf200a-c4d9-4e5c-8d87-4873cb112d61)
# Dining party size group tends to have the highest average total bill amount:
![Screenshot (240)](https://github.com/Dhivya-bharathi88/EX.NO-9/assets/128019999/7277084a-f884-4f22-975d-0fa9760d409b)
# Distribution of tip amounts for each day of the week:
![Screenshot (241)](https://github.com/Dhivya-bharathi88/EX.NO-9/assets/128019999/ccee0486-a471-4f20-893e-0ac48a503ab1)
# Tip amount vary based on the type of service:
![Screenshot (242)](https://github.com/Dhivya-bharathi88/EX.NO-9/assets/128019999/82ea76bc-1837-455b-b8d0-1fa417893ad4)
# Correlation between the total bill amount and the tip amount:
![Screenshot (243)](https://github.com/Dhivya-bharathi88/EX.NO-9/assets/128019999/ae32c997-b419-40ae-bb30-16c152b8cda9)
![Screenshot (244)](https://github.com/Dhivya-bharathi88/EX.NO-9/assets/128019999/53a4c797-ac2d-4455-9f54-0fee22525612)
![Screenshot (245)](https://github.com/Dhivya-bharathi88/EX.NO-9/assets/128019999/c0a8df13-e4ff-4fd1-a178-468502a88d19)

# RESULT:
Thus the Data Visualization techniques were performed for the given dataset and output was verified successfully.
