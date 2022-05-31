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


# CODE
```
#Reading the given dataset

import pandas as pd
df=pd.read_csv("Superstore.csv",encoding='unicode_escape')

df.head()

#Data Visualization using Seaborn

import seaborn as sns
from matplotlib import pyplot as plt

#1.Line Plot

plt.figure(figsize=(9,6))
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
# OUPUT
## Reading the given dataset
<img width="595" alt="171088128-126c7176-a343-4f0d-9775-be64ef025be9" src="https://user-images.githubusercontent.com/93427923/171088688-3cb36399-113e-4c56-b8e7-362e88e1c4a4.png">

## Data Visualization Using Seaborn:
### 1.Line Plot
<img width="336" alt="171088148-00745931-00a9-4e77-9652-bde07ec58041" src="https://user-images.githubusercontent.com/93427923/171088693-3673dcf4-9b16-40c4-b55b-76b08006e6cf.png">
<img width="314" alt="171088166-0622ed0d-983e-4fbb-9a07-ffde6ae73fbf" src="https://user-images.githubusercontent.com/93427923/171088704-d615feba-1bc4-4aee-a601-7986c9b5b0af.png">
<img width="258" alt="171088179-9468b1ae-1975-4ddd-8c7d-15a62cde1105" src="https://user-images.githubusercontent.com/93427923/171088711-5cbb8d92-f378-4f15-887b-a0ba937b88db.png">

### 2.Scatterplot
<img width="293" alt="171088199-43c1ab2b-8c36-4787-a25b-9fb447afb27a" src="https://user-images.githubusercontent.com/93427923/171088718-7c0932fe-0ff7-4ec4-bc9d-959027e9605b.png">
<img width="284" alt="171088208-7f3a8cdd-e757-4d86-8366-8e7795a10be1" src="https://user-images.githubusercontent.com/93427923/171088724-2122388a-df03-4353-9b94-c0b8ebfefe9e.png">
<img width="408" alt="171088221-0b5ce909-ea1b-4d11-b544-02a182ae71f8" src="https://user-images.githubusercontent.com/93427923/171088736-e163a68f-6c66-47a1-a517-c14cea8a761e.png">

### 3.Boxplot
<img width="252" alt="171088266-a16dba86-8fc1-4f39-a43e-8946245952ed" src="https://user-images.githubusercontent.com/93427923/171088754-3890f6c2-367e-445c-a765-06d00d3ddaac.png">
<img width="283" alt="171088275-5fc74eac-6c9c-4751-9a25-a6bb396b51b0" src="https://user-images.githubusercontent.com/93427923/171088761-15fda74d-be7f-4608-850a-7a1eefda3794.png">
<img width="229" alt="171088288-b57cfa86-14ca-4da3-be85-2aedda3ef070" src="https://user-images.githubusercontent.com/93427923/171088767-3318d409-e3c4-4fe0-bdeb-2d15b065ca2e.png">

### 4.Violin Plot
<img width="362" alt="171088300-2f65fe18-2157-4408-93b9-621db48d3fe5" src="https://user-images.githubusercontent.com/93427923/171088782-b324b7
f6-e83d-4c0f-8e7d-c7b94e6e357d.png">

### 5.Barplot
<img width="248" alt="171088309-f8fc728a-98de-46da-af45-5504501865a5" src="https://user-images.githubusercontent.com/93427923/171088791-30d986fc-d0d2-4bd4-b8da-599a4722ecec.png">
<img width="258" alt="171088319-54fd42f2-c10d-4696-ab1d-cf26b67876ab" src="https://user-images.githubusercontent.com/93427923/171088795-c4cc4476-1f10-4843-8cda-f216d4248e80.png">


<img width="267" alt="171088340-ac5e9f66-7ecd-4fbc-b58f-0e8a9c854f58" src="https://user-images.githubusercontent.com/93427923/171088801-48de7684-d930-4dc4-bd14-cc40c9876d2a.png">

6.Pointplot
<img width="258" alt="171088373-3b644c23-eb34-4c62-9854-7beedc247c8e" src="https://user-images.githubusercontent.com/93427923/171088806-655d8df7-f27d-4105-a695-d58d9a93b093.png">

7.Count plot
<img width="281" alt="171088392-27dc5b70-ca70-4069-ac16-50edbcb51fb0" src="https://user-images.githubusercontent.com/93427923/171088816-69928057-e5ef-462a-a7a6-6f7955b9d16b.png">
<img width="252" alt="171088402-28a45721-eef1-44ae-8a71-8f1cdfc84371" src="https://user-images.githubusercontent.com/93427923/171088822-cf2696bf-22fd-4c57-b866-2ebf36774f94.png">







