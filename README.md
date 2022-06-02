# Ex-08-Data-Visualization-

## AIM
To Perform Data Visualization on a complex dataset and save the data to a file. 

# Explanation
Data visualization is the graphical representation of information and data. By using visual elements like charts, graphs, and maps, data visualization tools provide an accessible way to see and understand trends, outliers, and patterns in data.

# ALGORITHM
### STEP 1
Read the given Data
### STEP 2
Clean the Data Set using Data Cleaning Process
### STEP 3
Apply Feature generation and selection techniques to all the features of the data set
### STEP 4
Apply data visualization techniques to identify the patterns of the data.


# CODE:
```
Developed by: M.Vidya Neela
Reg No: 212221230120
```

```
import pandas as pd
import numpy as np
df=pd.read_csv("Superstore.csv")

df.head()

#Data Visualization using Seaborn

import seaborn as sns
from matplotlib import pyplot as plt

#1.Line plot

plt.figure(figsize=(8,5))
sns.lineplot(x="Segment",y="Region",data=df,marker='o')
plt.xticks(rotation = 90)
sns.lineplot(x='Ship Mode',y='Category', hue ="Segment",data=df)
sns.lineplot(x="Category",y="Sales",data=df,marker='o')

#2.Scatterplot

sns.scatterplot(x='Category',y='Sub-Category',data=df)
sns.scatterplot(x='Category', y='Sub-Category', hue ="Segment",data=df)
plt.figure(figsize=(10,7))
sns.scatterplot(x="Region",y="Sales",data=df)
plt.xticks(rotation = 90)

#3.Boxplot

sns.boxplot(x="Sub-Category",y="Discount",data=df)
sns.boxplot( x="Profit", y="Category",data=df)

#4.Violin Plot

sns.violinplot(x="Profit",data=df)

#5.Barplot

sns.barplot(x="Sub-Category",y="Sales",data=df)
plt.xticks(rotation = 90)
sns.barplot(x="Category",y="Sales",data=df)
plt.xticks(rotation = 90)

#6.Pointplot

sns.pointplot(x=df["Quantity"],y=df["Discount"])

#7.Count plot

sns.countplot(x="Category",data=df)
sns.countplot(x="Sub-Category",data=df)

#8.Histogram

sns.histplot(data=df,x ='Ship Mode',hue='Sub-Category')

#9.KDE Plot

sns.kdeplot(x="Profit", data = df,hue='Category')

#Data Visualization Using MatPlotlib

#1.Plot

plt.plot(df['Category'], df['Sales'])
plt.show()

#2.Heatmap

df.corr()
plt.subplots(figsize=(12,7))
sns.heatmap(df.corr(),annot=True)

#3.Piechart

df1=df.groupby(by=["Ship Mode"]).sum()
labels=[]
for i in df1.index:
    labels.append(i)
colors=sns.color_palette("bright")
plt.pie(df1["Sales"],labels=labels,autopct="%0.0f%%")
plt.show()

df3=df.groupby(by=["Category"]).sum()
labels=[]
for i in df3.index:
    labels.append(i) 
plt.figure(figsize=(8,8))
colors = sns.color_palette('pastel')
plt.pie(df3["Profit"],colors = colors,labels=labels, autopct = '%0.0f%%')
plt.show()

#4.Histogram


plt.hist(df["Sub-Category"],facecolor="peru",edgecolor="blue",bins=10)
plt.show()

#5.Bargraph

plt.bar(df.index,df['Category'])
plt.show()

#6.Scatterplot

plt.scatter(df["Region"],df["Profit"], c ="blue")
plt.show()              

#7.Boxplot

plt.boxplot(x="Sales",data=df)
plt.show()
```

# OUPUT:
## Reading the given dataset:
![170985646-ccfbc412-b358-4115-b197-70e373a97404](https://user-images.githubusercontent.com/94169318/171546552-f2187527-f078-47c4-a807-ded0685c2694.png)

## Data Visualization Using Seaborn:
### 1.Lineplot:
![170985803-c6671117-ccfb-4a94-8132-8e1a258d1593](https://user-images.githubusercontent.com/94169318/171546644-effad259-741d-4dce-a77d-b4bdbd074a19.png)

![170985838-de8ed4fd-65a9-43ec-a3a0-9bf04017fe45](https://user-images.githubusercontent.com/94169318/171546689-bf190a42-1c2c-44ae-9804-1004c26fcf3c.png)

## 2.Scatterplot:
![170985871-d2732de8-a729-4e59-af26-0868e29d7f3d](https://user-images.githubusercontent.com/94169318/171546782-69dd4e4f-cb8d-4877-b9f1-cb8b13cba8ba.png)

![170985891-e19a83d9-2cd2-40b0-939f-01ef0decec37](https://user-images.githubusercontent.com/94169318/171546808-a8855db3-eacf-4d61-a286-618a2c4dc214.png)

## 3.Boxplot:
![170985937-0a3b5dae-0306-4d45-b8d4-c278620c2e48](https://user-images.githubusercontent.com/94169318/171546952-80215466-6ecb-41b9-a4db-2c1ca62c5861.png)

![170985949-9876aa03-940d-434c-a5cc-b830845e97b3](https://user-images.githubusercontent.com/94169318/171546971-650a28aa-a657-4b08-b063-ca2c77b0bf64.png)

## 4.Violinplot:
![170985994-1b57705e-e411-43ee-8553-b20656e1a7cd](https://user-images.githubusercontent.com/94169318/171547025-8b5e9369-f957-4ff1-86d9-98a58cb62160.png)

## 5.Barplot:
![170986074-e320e391-d31c-458d-9007-a2a9b4930b71](https://user-images.githubusercontent.com/94169318/171547087-f26a9d2e-26bc-44bf-9a1b-e6a77d67d16d.png)

![170986095-986ef622-5254-4228-ab6c-0cdba8cf389f](https://user-images.githubusercontent.com/94169318/171547102-84e0b288-18df-4abb-93e5-69e3a783c7b5.png)

## 6.Pointplot:
![170986140-34e896cd-9265-4cc1-98ca-73eb1b600028](https://user-images.githubusercontent.com/94169318/171547149-82240e27-b39d-4925-9829-345aa326fcfb.png)

## 7.Countplot:
![170986183-c1fe579c-484c-499a-939f-ea5502ba930b](https://user-images.githubusercontent.com/94169318/171547297-2821188a-dff7-4bd6-8b65-62332ae9e314.png)

## 8.Histogram:
![170986236-7d0f5c48-3caa-4b3b-a44a-2613bd777220](https://user-images.githubusercontent.com/94169318/171547375-4391ebd3-1a46-4ca7-8b47-8ac4cfaa52c0.png)

## 9.KDE Plot:
![170986290-28e2e3f7-1e19-4ca1-bf30-7a9a1e133ac5](https://user-images.githubusercontent.com/94169318/171547427-4a66a515-5d2a-45d3-a6c7-535a89c16416.png)

## Data Visualization Using Matplotlib:
### 1.Plot:
![170986355-98ec623d-13b3-4d26-8448-4d1320ffe290](https://user-images.githubusercontent.com/94169318/171547572-a5ffc5a9-2bcd-40dc-a358-634cdc7145a8.png)

### 2.Heatmap:
![170986395-34027063-a756-4307-a144-7d9e51554528](https://user-images.githubusercontent.com/94169318/171547615-324df923-7547-4001-aefa-84a1f52b05d5.png)

![170986410-eaa8366c-70fc-4bba-b212-8dfd53b39c03](https://user-images.githubusercontent.com/94169318/171547629-9755d65b-6879-4175-98ab-4663ef2669fb.png)

### 3.PieChart:
![170986466-330ceaec-c3f0-40ab-a177-92885454b26b](https://user-images.githubusercontent.com/94169318/171547751-adc3ca06-cd19-4c4b-aa12-de4ae8fffcad.png)

![170986481-42e9f0ec-5223-4a87-a553-a649a30a2384](https://user-images.githubusercontent.com/94169318/171547762-e45d72b8-7f42-49bd-9952-96e635e0f34e.png)

### 4.Histogram:
![170986533-19a5064d-9acf-456a-adc3-ec4ecdb4765b](https://user-images.githubusercontent.com/94169318/171547802-416309bc-556c-4224-9e7b-5ff7f690eb74.png)

### 5.Bargraph:
![170986583-f76c12d8-735f-4f9a-977d-3931e5465ca3](https://user-images.githubusercontent.com/94169318/171547835-38991f75-1d81-49fc-99ea-3a0f9002ba90.png)

### 6.Scatterplot:
![170986638-2d06d57b-9b6c-468f-b992-5ad1107b8982](https://user-images.githubusercontent.com/94169318/171547883-c8c0b9bd-5a07-48d2-ba96-c38e6e8f2f9f.png)

### 7.Boxplot:
![170986701-51425ca2-db20-4b3e-bb79-73c3cfdcd2c8](https://user-images.githubusercontent.com/94169318/171547938-f0407c84-471f-48e1-ab1f-1cf0faf2885d.png)

## RESULT:
Hence,Data Visualization is applied on the complex dataset using libraries like Seaborn and Matplotlib successfully and the data is saved to file.
