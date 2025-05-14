# EXNO-6-DS-DATA VISUALIZATION USING SEABORN LIBRARY

# Aim:
  To Perform Data Visualization using seaborn python library for the given datas.

# EXPLANATION:
Data visualization is the graphical representation of information and data. By using visual elements like charts, graphs, and maps, data visualization tools provide an accessible way to see and understand trends, outliers, and patterns in data.

# Algorithm:
STEP 1:Include the necessary Library.

STEP 2:Read the given Data.

STEP 3:Apply data visualization techniques to identify the patterns of the data.

STEP 4:Apply the various data visualization tools wherever necessary.

STEP 5:Include Necessary parameters in each functions.

# Coding and Output:
```
import seaborn as sns
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
x=[1,2,3,4,5]
y=[3,6,2,7,9]
sns.lineplot(x=x,y=y)
```
![image](https://github.com/user-attachments/assets/36055b2e-1122-4da2-b817-991a132088a0)
```
df=sns.load_dataset("tips")
df
```
![image](https://github.com/user-attachments/assets/dc4cc195-733e-47f7-bdc7-37c03c24ddeb)
```
sns.lineplot(x="total_bill", y="tip", data=df, hue="sex", linestyle="solid", legend="full")
plt.show()
```
![image](https://github.com/user-attachments/assets/77ca75f0-df98-4a5e-ab1f-1b559fcda7fb)
```
x=[1,2,3,4,5]
y1=[3,5,6,3,1]
y2=[7,5,9,3,6]
y3=[5,3,7,1,4]
sns.lineplot(x=x,y=y1)
sns.lineplot(x=x,y=y2)
sns.lineplot(x=x,y=y3)
plt.title("MULTI-LINE PLOT")
plt.xlabel("X AXIS")
plt.ylabel("Y AXIS")
```
![image](https://github.com/user-attachments/assets/220f950e-96c1-42a6-84ba-2f315ec00af9)
```
avg_total_bill=df.groupby('day')['total_bill'].mean()
avg_tip=df.groupby('day')['tip'].mean()

print(avg_total_bill)
```
![image](https://github.com/user-attachments/assets/5d238e13-8868-47a3-8286-1f7d2b769946)
```
print(avg_tip)
```
![image](https://github.com/user-attachments/assets/084d0e88-be75-403a-9e94-e0e837e735f3)
```
plt.figure(figsize=(8,6))
p1=plt.bar(avg_total_bill.index,avg_total_bill,label="TOTAL BILL")
p2=plt.bar(avg_tip.index,avg_tip,bottom=avg_total_bill,label="TIP")
plt.xlabel("Day of the week")
plt.ylabel('Amount')
plt.title("Average Total Bill and Tip by Day")
plt.legend()
```
![image](https://github.com/user-attachments/assets/e5c3746f-585b-4f3b-887d-58b438a8c775)
```
avg_total_bill = df.groupby('time')['total_bill'].mean()
avg_tip = df.groupby('time')['tip'].mean()
p1 = plt.bar(avg_total_bill.index, avg_total_bill, label="TOTAL BILL", width=0.4)
p2 = plt.bar(avg_tip.index, avg_tip, bottom=avg_total_bill, label="TIP", width=0.4)
plt.xlabel("Time of Day")
plt.ylabel("Amount")
plt.title("Average Total Bill and Tip by Time of the Day")
plt.legend()
plt.show()
```
![image](https://github.com/user-attachments/assets/c9731ca5-7528-4f1b-90f2-afb0a812b725)
```
years = range(2000, 2010)
apples = [0.895, 0.91, 0.919, 0.926, 0.929, 0.931, 0.934, 0.936, 0.937, 0.9375]
oranges = [0.962, 0.941, 0.938, 0.923, 0.918, 0.906, 0.907, 0.904, 0.901, 0.8]
plt.bar(years, apples, label="Apples")
plt.bar(years, oranges, bottom=apples, label="Oranges")
plt.xlabel("Year")
plt.ylabel("Amount")
plt.title("Stacked Bar Chart: Apples and Oranges Over Years")
plt.legend()
plt.show()
```
![image](https://github.com/user-attachments/assets/e9c33c13-dc77-4a49-b9a6-04365d992765)
```
sns.barplot(x="day",y="total_bill",hue="sex",data=df,palette="Set1")
plt.xlabel("Day of the Week")
plt.ylabel("Total Bill")
plt.title("Total Bill")
```
![image](https://github.com/user-attachments/assets/e49120d1-364c-4123-895f-9a4b3c5756d9)
```
tit=pd.read_csv("/content/titanic_dataset (2).csv")
tit
```
![image](https://github.com/user-attachments/assets/60a5ceb8-473e-4ad1-8c8a-b0a266bfba37)
```
plt.figure(figsize=(8,5))
sns.barplot(x="Embarked",y='Fare',data=tit,palette='rainbow')
plt.title("Fare of passenger by Embarked town")
```
![image](https://github.com/user-attachments/assets/d4800dbd-10bb-4f26-9f5f-c73e8af6065e)
```
plt.figure(figsize=(8,5))
sns.barplot(x="Embarked",y='Fare',data=tit,palette='rainbow',hue='Pclass')
plt.title("Fare of passenger by Embarked town divided by class")
```
![image](https://github.com/user-attachments/assets/b670f116-d6ac-4cfc-9a96-20f7769b1a91)
```
sns.scatterplot(x="total_bill",y='tip',hue="sex",data=df)
plt.xlabel("total bill")
plt.ylabel("tip amount")
plt.title("Scatter plot")
```
![image](https://github.com/user-attachments/assets/201565cb-713b-41e6-a5db-0fd6ce2de6fd)
```
np.random.seed(1)
num=np.random.randn(1000)
num=pd.Series(num,name="Numerical Variable")
num
```
![image](https://github.com/user-attachments/assets/e9494645-a01f-4ff0-bc99-5cd26c49c78f)
```
sns.histplot(data=num,kde=True)
```
![image](https://github.com/user-attachments/assets/c392989b-692a-4577-aa77-70e01999bf9d)
```
sns.histplot(data=tit,x="Pclass",hue='Survived',kde=True)
```
![image](https://github.com/user-attachments/assets/1e6cd0cd-6abf-44d8-ab94-1c5c044f43e0)
```
np.random.seed(0)
marks=np.random.normal(loc=70,scale=10,size=100)
marks
```
![image](https://github.com/user-attachments/assets/3a213b51-61aa-4821-a234-711099be1fe9)
```
sns.histplot(data=marks, bins=10, kde=True, stat='count', cumulative=False, multiple='layer')
plt.xlabel("Marks")
plt.ylabel("Density")
plt.title("Histogram")
plt.show()
```
![image](https://github.com/user-attachments/assets/23c32801-1956-4830-82e2-b68439a57247)
```
sns.boxplot(x=df['day'],y=df['total_bill'],hue=df['sex'])
```
![image](https://github.com/user-attachments/assets/b8aaabcb-aaec-42e0-b1b6-22eb9d8e69d9)
```
sns.boxplot(x='day', y='total_bill', hue='smoker', data=df, linewidth=2, width=0.5)
plt.title("Boxplot of Total Bill by Day and Smoking Status")
plt.xlabel("Day")
plt.ylabel("Total Bill")
plt.legend(title="Smoker")
plt.show()
```
![image](https://github.com/user-attachments/assets/5766fe14-734c-4186-bf73-52dc40944e7e)
```
sns.boxplot(x='Pclass',y='Age',data=tit,palette='rainbow')
plt.title("age by passenger class,titanic")
```
![image](https://github.com/user-attachments/assets/9e212e08-323d-4c4f-a3f9-bf6c428d397d)
```
sns.violinplot(x='day', y='total_bill', hue='smoker', data=df, linewidth=2, width=0.8)
plt.xlabel("Day of the Week")
plt.ylabel("Total Bill")
plt.title("Violin Plot of Total Bill by Day and Smoking Status")
plt.legend(title="Smoker")
plt.show()
```
![image](https://github.com/user-attachments/assets/1b56a08c-e452-4fc7-918a-c1addcc19f0e)
```
sns.violinplot(x='day',y='tip',data=df)
```
![image](https://github.com/user-attachments/assets/8be97114-a087-486a-8bf2-a1dc4bc8c0ff)
```
sns.violinplot(x=df["total_bill"])
```
![image](https://github.com/user-attachments/assets/8cb03b3d-384a-48c0-8915-9177143ddaac)
```
sns.set(style="whitegrid")
sns.violinplot(x="tip",y="day",data=df)
```
![image](https://github.com/user-attachments/assets/69f66fef-7657-4751-acdc-32140e293f75)
```
sns.kdeplot(data=df, x="total_bill", hue="time", multiple="fill", linewidth=3, palette="deep")
plt.xlabel("Total Bill")
plt.ylabel("Density")
plt.title("KDE Plot of Total Bill by Time")
plt.legend(title="Time")
plt.show()
```
![image](https://github.com/user-attachments/assets/50425d81-9abd-45fc-ba75-d51e4278ce38)
```
sns.kdeplot(data=df, x="total_bill", hue="time", multiple="layer", linewidth=3)
plt.xlabel("Total Bill")
plt.ylabel("Density")
plt.title("KDE Plot of Total Bill by Time")
plt.legend(title="Time")
plt.show()
```
![image](https://github.com/user-attachments/assets/e593794d-5d56-4382-abb2-812e12e335b1)
```
sns.kdeplot(data=df, x="total_bill", hue="time", multiple="stack", linewidth=3)
plt.xlabel("Total Bill")
plt.ylabel("Density")
plt.title("Stacked KDE Plot of Total Bill by Time")
plt.legend(title="Time")
plt.show()
```
![image](https://github.com/user-attachments/assets/946866ff-23f5-4bbe-ac68-56849edbd507)
```
data=np.random.randint(low=1,high=100,size=(10,10))
print("The data to be plotted:\n")
print(data)
```
![image](https://github.com/user-attachments/assets/0d8c7968-3dcf-4d0b-a8c9-73c3bff6fa3b)
```
sns.heatmap(data=data,annot=True)
```
![image](https://github.com/user-attachments/assets/4b685953-23bd-403b-a726-28983c004c18)
```
sns.heatmap(data=data)
```
![image](https://github.com/user-attachments/assets/3960a893-b0cb-4218-bb83-c9e7418d8146)

# Result:
  Thus,Data Visualization using seaborn python library for the given datas is successfully
 performed.
