# Ex:08 Data Visualization
## AIM
To Perform Data Visualization on a complex dataset and save the data to a file.

## Explanation
Data visualization is the graphical representation of information and data. By using visual elements like charts, graphs, and maps, data visualization tools provide an accessible way to see and understand trends, outliers, and patterns in data.

## ALGORITHM
1. Read the given Data
2. Clean the Data Set using Data Cleaning Process
3. Apply Feature generation and selection techniques to all the features of the data set
4. Apply data visualization techniques to identify the patterns of the data.

## CODE
```
Name: JENISHA.J
Reg.No: 212222230056
```
### Data Visualization using Seaborn
```
import pandas as pd
import seaborn as sns
from matplotlib import pyplot as plt
df=pd.read_csv("/content/Superstore - Superstore.csv (1).csv")
df.head()
df.info()
df.isnull().sum()
```
#### LINE PLOT
```
sns.lineplot(x="Category",y="Sales",data=df,marker='o')

sns.lineplot(x='Ship Mode', y='Category',hue="Segment",data=df)
plt.title("Multiline Plot")
plt.show()
```
#### BAR PLOT
```
sns.barplot(x="Category",y="Sales",data=df)

sns.barplot(x='Region', y='Sales', data=df,palette='Set1')
plt.title("Sales in different Regions")
plt.show()
```
#### SCATTER PLOT
```
sns.scatterplot(x='Category',y='Sub-Category',data=df)
plt.title("Scatterplot")
plt.show()

sns.scatterplot(x='Category',y='Sub-Category',hue='Segment',data=df)
plt.show()
```
#### BOX PLOT
```
sns.boxplot(x="Sub-Category",y="Discount",data=df)
plt.xticks(rotation=90)

sns.boxplot( x="Profit", y="Category",data=df)
```
#### POINT PLOT
```
sns.pointplot(x=df["Quantity"],y=df["Discount"])
```
#### VIOLIN PLOT
```
sns.violinplot(x="Profit",data=df)
```
#### COUNT PLOT
```
sns.countplot(x="Category",data=df)

sns.countplot(x="Sub-Category",data=df)
plt.xticks(rotation=90)
```
#### HISTOGRAM
```
sns.histplot(data=df,x ='Ship Mode',hue='Sub-Category')
```
#### KDE PLOT
```
sns.kdeplot(x="Discount", data = df,hue='Category')
```
### Data Visualization using Matplotlib
#### PLOT
```
plt.plot(df['Region'], df['Sales'])
plt.show()
```
#### HEATMAP
```
df.corr()
plt.subplots(figsize=(12,7))
sns.heatmap(df.corr(),annot=True)
```
#### PIE CHART
```
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
```
#### HISTOGRAM
```
plt.hist(df["Sub-Category"],facecolor="peru",edgecolor="black",bins=10)
plt.xticks(rotation =90)
plt.show()
```
#### BAR PLOT
```
plt.bar(df['Category'],df.index)
plt.show()
```
#### SCATTER PLOT
```
plt.scatter(df["Region"],df["Profit"], c ="red")
plt.show()
```
#### BOX PLOT
```
plt.boxplot(x="Sales",data=df)
plt.show()
```
## OUTPUT
### Data visualization using Seaborn
![image](https://github.com/Jenishajustin/ODD2023-Datascience-Ex-08/assets/119405070/21301f1c-ce45-4cb0-ba54-abde9761419f)
#### Data information
![image](https://github.com/Jenishajustin/ODD2023-Datascience-Ex-08/assets/119405070/2cb8b12e-9bda-4986-b48f-f09a9229b6b9)

#### Null values
![image](https://github.com/Jenishajustin/ODD2023-Datascience-Ex-08/assets/119405070/d97cc080-2301-4294-a5de-c17d29fef4d3)

#### Lineplot
![image](https://github.com/Jenishajustin/ODD2023-Datascience-Ex-08/assets/119405070/867b87cc-d427-4632-8e96-53b317fe441e)
![image](https://github.com/Jenishajustin/ODD2023-Datascience-Ex-08/assets/119405070/9d1fdcc0-b7e2-4790-ab74-af570bb5d9ae)

#### Barchart
![image](https://github.com/Jenishajustin/ODD2023-Datascience-Ex-08/assets/119405070/c361bdb0-cde3-42c3-800b-51c1de36d37d)
![image](https://github.com/Jenishajustin/ODD2023-Datascience-Ex-08/assets/119405070/aa0184a9-eabd-489c-95e0-312c9d4d8674)

#### Scatterplot
![image](https://github.com/Jenishajustin/ODD2023-Datascience-Ex-08/assets/119405070/aa21e9b8-f1a7-4b41-bc36-fdddad2388be)
![image](https://github.com/Jenishajustin/ODD2023-Datascience-Ex-08/assets/119405070/15b982c5-7ea2-469c-83fc-048337fb4cd8)

#### Boxplot
![image](https://github.com/Jenishajustin/ODD2023-Datascience-Ex-08/assets/119405070/34b0d239-eccf-4689-a66a-dc134a50e8b5)
![image](https://github.com/Jenishajustin/ODD2023-Datascience-Ex-08/assets/119405070/a4b90cd0-71d1-42fb-8a5e-ce1144ddda84)

#### Pointplot
![image](https://github.com/Jenishajustin/ODD2023-Datascience-Ex-08/assets/119405070/0e0a66f2-0461-42aa-9b9a-06a31c3935e4)

#### Violinplot
![image](https://github.com/Jenishajustin/ODD2023-Datascience-Ex-08/assets/119405070/60f1f757-287f-4a84-b209-a803acd1e25b)

#### Countplot
![image](https://github.com/Jenishajustin/ODD2023-Datascience-Ex-08/assets/119405070/94c094db-7cb4-4c26-ad57-ca533a808df0)

#### Histogram
![image](https://github.com/Jenishajustin/ODD2023-Datascience-Ex-08/assets/119405070/27382ce7-df2d-4410-8c88-a6080d74b487)
![image](https://github.com/Jenishajustin/ODD2023-Datascience-Ex-08/assets/119405070/5ba408b8-7489-401a-bb94-5c007cd62459)

#### KDEplot
![image](https://github.com/Jenishajustin/ODD2023-Datascience-Ex-08/assets/119405070/3510accc-3739-4814-acd2-863b6f409fe4)

### Data visualization using Matplot
#### Plot
![image](https://github.com/Jenishajustin/ODD2023-Datascience-Ex-08/assets/119405070/78f257ce-ba27-4870-be04-51f2be086bad)

#### Heatmap
![image](https://github.com/Jenishajustin/ODD2023-Datascience-Ex-08/assets/119405070/ac72f7dd-1316-43c7-a05d-ff4ad0f50989)

#### Piechart
![image](https://github.com/Jenishajustin/ODD2023-Datascience-Ex-08/assets/119405070/64c4c8a8-e592-46fb-810b-4945124ba40e)
![image](https://github.com/Jenishajustin/ODD2023-Datascience-Ex-08/assets/119405070/80f03fca-e4c3-4d37-942b-9214d2658bac)

#### Histogram
![image](https://github.com/Jenishajustin/ODD2023-Datascience-Ex-08/assets/119405070/ddc521c0-0882-4414-b203-e027c76d9e37)

#### Barplot
![image](https://github.com/Jenishajustin/ODD2023-Datascience-Ex-08/assets/119405070/8ecbf086-33f0-4742-9c91-28a3961d8bf7)

#### Scatterplot
![image](https://github.com/Jenishajustin/ODD2023-Datascience-Ex-08/assets/119405070/2347c245-da0e-4231-a0eb-13eb0148b9a2)

#### Boxplot
![image](https://github.com/Jenishajustin/ODD2023-Datascience-Ex-08/assets/119405070/98874de6-f8f5-4b18-bdbe-9ff67e0790c1)

## RESULT
Hence, Data Visualization is applied on the complex dataset using libraries like Seaborn and Matplotlib successfully and the data is saved to file.
