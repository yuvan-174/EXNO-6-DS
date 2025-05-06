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
```py
import seaborn as sns
import matplotlib.pyplot as plt
import pandas as pd
import numpy as np
x = [1, 2, 3, 4, 5]
y = [3, 6, 2, 7, 1]
sns.lineplot(x=x,y=y)
```
![image](https://github.com/user-attachments/assets/a63ab8da-6ca6-4b67-af72-42402280da60)

```py
df = sns.load_dataset("tips")
df
```
![image](https://github.com/user-attachments/assets/80d9e0f9-1a99-483b-a97e-7ac246b6dcb3)

```py
sns.lineplot(x="total_bill",y="tip", data=df, hue="sex", linestyle='solid', legend="auto")
```
![image](https://github.com/user-attachments/assets/2438f84d-b0f5-4c09-98ef-e12b63745434)

```py
x=[1, 2, 3, 4, 5]
y1=[3, 5, 2, 6, 1]
y2=[1, 6, 4, 3, 8]
y3=[5, 2, 7, 1, 4]

sns.lineplot(x=x, y=y1)
sns.lineplot(x=x, y=y2)
sns.lineplot(x=x, y=y3)
plt.title("Multi-Line Plot")
plt.xlabel('X Label')
plt.ylabel("Y Label")
```
![image](https://github.com/user-attachments/assets/8a49575d-bd81-47a1-9433-ca73b1d4c289)

```py
tips=sns.load_dataset('tips')
avg_total_bill = tips.groupby('day')['total_bill'].mean()
avg_tip = tips.groupby('day')['tip'].mean()
plt.figure(figsize=(8, 6))
p1 = plt.bar(avg_total_bill.index, avg_total_bill, label='Total Bill')
p2 = plt.bar(avg_tip.index, avg_tip, bottom=avg_total_bill, label='Tip')
plt.xlabel('Day of the Week')
plt.ylabel('Amount')
plt.title('Average Total Bill and Tip by Day')
plt.legend()
```
![image](https://github.com/user-attachments/assets/ce1a55d3-032e-4e7c-a056-ef88a4b3a086)

```py
avg_total_bill = tips.groupby('time')['total_bill'].mean()
avg_tip=tips.groupby('time') ['tip'].mean()
p1= plt.bar(avg_total_bill.index, avg_total_bill, label='Total Bill', width=0.4)
p2 = plt.bar(avg_tip.index,avg_tip,bottom=avg_total_bill,label='Tip', width=0.4)
```
![image](https://github.com/user-attachments/assets/9922e277-0830-4c78-b26e-5ab7835eda22)

```py
years=range(2000, 2012)
apples=[0.895, 0.91, 0.919, 0.926, 0.929, 0.931, 0.934, 0.936, 0.937, 0.9375, 0.9372, 0.939]
oranges = [0.962, 0.941, 0.930, 0.923, 0.918, 0.908, 0.907, 0.904, 0.901, 0.898, 0.9, 0.896, ]

plt.bar(years, apples)
plt.bar(years, oranges, bottom=apples)
```
![image](https://github.com/user-attachments/assets/343fec59-27cc-4e1a-9a7c-a347ace6c687)

```py
import seaborn as sns
dt= sns.load_dataset('tips')
sns.barplot(x='day', y='total_bill', hue='sex', data=dt, palette='Set1')
plt.xlabel('Day of the Week')
plt.ylabel("Total Bill")
plt.title('Total Bill by Day and Gender')
```
![image](https://github.com/user-attachments/assets/e1fc1594-5571-4d8b-b614-dc5945b33688)

```py
tit=pd.read_csv("/content/titanic_dataset.csv")
tit
```
![image](https://github.com/user-attachments/assets/940f0f07-cab6-4c70-a41c-e976ca3e18fd)

```py
plt.figure(figsize=(8,5))
sns.barplot(x='Embarked', y='Fare', data=tit, palette='rainbow')
plt.title("Fare of Passenger by Embarked Town")
```
![image](https://github.com/user-attachments/assets/9df51d0b-e0ac-42fe-9c66-88b2e16be0fe)

```py
plt.figure(figsize=(8,5))
sns.barplot(x='Embarked', y='Fare', data=tit, palette='rainbow', hue='Pclass')
plt.title("Fare of Passenger by Embarked Town, Divided by Class")
```
![image](https://github.com/user-attachments/assets/41cd5b1e-7d7e-4872-a45a-465ebb6574f3)

```py
tips=sns.load_dataset('tips')
sns.scatterplot(x='total_bill', y='tip', hue='sex', data=tips)
plt.xlabel('Total Bill')
plt.ylabel("Tip Amount")
plt.title('Scatter Plot of Total Bill vs. Tip Amount')
```
![image](https://github.com/user-attachments/assets/2d170264-05a8-461c-8cb2-b010621ceb7f)

```py
num_var = np.random.randn(1000)
num_var=pd.Series(num_var, name = "Numerical variable")
num_var
```
![image](https://github.com/user-attachments/assets/8da1cc1b-8bbf-4f74-b80e-e2a87f2d879e)

```py
sns.histplot(data = num_var, kde = True)
```
![image](https://github.com/user-attachments/assets/d1f39840-27ea-4188-935f-887dae88d71e)

```py
df=pd.read_csv("/content/titanic_dataset.csv")
sns.histplot(data=df,x="Pclass", hue="Survived", kde=True)
```
![image](https://github.com/user-attachments/assets/d97369e9-e6c2-4ff3-990d-4d2edd9ccf19)

```py
tips=sns.load_dataset('tips')
sns.boxplot(x=tips['day'], y=tips ['total_bill'], hue=tips['sex'])
```
![image](https://github.com/user-attachments/assets/9d1c5778-d056-45be-b417-0c9c63da7152)

```py
sns.boxplot(x="day", y="total_bill", hue="smoker", data=tips, linewidth=2, width=0.6, boxprops={"facecolor": "lightblue", "edgecolor": "darkblue"},
whiskerprops={"color": "black", "linestyle": "--", "linewidth": 1.5}, capprops={"color": "black", "linestyle": "--", "linewidth": 1.5})
```
![image](https://github.com/user-attachments/assets/c242e0a1-36b2-4e17-b61c-a36778b4c2f9)

```py
sns.violinplot(x="day", y="total_bill", hue="smoker", data=tips, linewidth=2, width=0.6, palette="Set3", inner="quartile")
plt.xlabel("Day of the Week")
plt.ylabel("Total Bill")
plt.title("Violin Plot of Total Bill by Day and Smoker Status")
```
![image](https://github.com/user-attachments/assets/07a51b3c-c423-4d8d-b6a0-326eb22776d1)

```py
mart=pd.read_csv("/content/titanic_dataset.csv")
mart
```
![image](https://github.com/user-attachments/assets/43cc7738-4598-4594-8b5a-b04d982b6ed4)

```py
mart=mart[['PassengerId', 'Survived', 'Age', 'Name', 'Ticket', 'Embarked']]
mart.head(10)
```
![image](https://github.com/user-attachments/assets/a4c18553-0c9b-420a-a05e-07c46a44cd7c)

```py
sns.kdeplot(data=mart,x='PassengerId')
```
![image](https://github.com/user-attachments/assets/12821a65-ad65-4ed1-a35b-66ad6f884de8)

```py
sns.kdeplot(data=mart,x='Age')
```
![image](https://github.com/user-attachments/assets/5b2e797d-254d-4ecc-88c1-3c48e7e779cb)

```py
sns.kdeplot(data=mart)
```
![image](https://github.com/user-attachments/assets/7eb1cf5d-1ed5-44da-9381-a270961b96a8)

```py
sns.kdeplot(data=mart,x='PassengerId',hue='Survived',multiple='stack')
```
![image](https://github.com/user-attachments/assets/1514b5a6-3232-4069-99ca-d2eb57936277)

```py
sns.kdeplot(data=mart,x='PassengerId',y='Survived')
```
![image](https://github.com/user-attachments/assets/944d2dc2-e286-4757-adee-2d71ccacf321)

```py
data = np.random.randint(low = 1, high = 100, size = (10,10))
hm=sns.heatmap(data=data,annot=True)
```
![image](https://github.com/user-attachments/assets/dc2d67d7-0412-46db-9c5d-ac2bf5f3715f)

```py
hm=sns.heatmap(data=data)
```
![image](https://github.com/user-attachments/assets/a4d9c49a-82cd-4f18-a7d2-051684c007d5)

# Result:
 Successfully Performed Data Visualization using seaborn python library for the given datas.
