## Ex-04-Multivariate-Analysis
### AIM
To perform Multivariate EDA on the given data set.

### EXPLANATION
Exploratory data analysis is used to understand the messages within a dataset. This technique involves many iterative processes to ensure that the cleaned data is further sorted to better understand the useful meaning.The primary aim with exploratory analysis is to examine the data for distribution, outliers and anomalies to direct specific testing of your hypothesis.

### ALGORITHM
### STEP 1
Import the built libraries required to perform EDA and outlier removal.

### STEP 2
Read the given csv file

### STEP 3
Convert the file into a dataframe and get information of the data.

### STEP 4
Return the objects containing counts of unique values using (value_counts()).

### STEP 5
Plot the counts in the form of Histogram or Bar Graph.

### STEP 6
Use seaborn the bar graph comparison of data can be viewed.

### STEP 7
Find the pairwise correlation of all columns in the dataframe.corr()

### STEP 8
Save the final data set into the file

### PROGRAM:
```
Developed by: D.Vinitha
Registration Number:212221230175
Multivariate EDA - SuperStore.csv
import pandas as pd
import numpy as np
import seaborn as sns
import matplotlib.pyplot as plt
df=pd.read_csv("SuperStore.csv")
df.head(6)
df.info()
df.describe()
df.isnull().sum()
df['Postal Code'] = df["Postal Code"].fillna(df['Postal Code'].mode()[0])
df.isnull().sum()
sns.scatterplot (df['Sales'])
states=df.loc[:,["State","Sales"]]
states=states.groupby(by=["State"]).sum().sort_values(by="Sales")
plt.figure(figsize=(17,7))
sbn.barplot(x=states.index,y="Sales",data=states)
plt.xticks(rotation = 90)
plt.xlabel=("STATES")
plt.ylabel=("SALES")
plt.show()
states=df.loc[:,["State","Postal Code"]]
states=states.groupby(by=["State"]).sum().sort_values(by="Postal Code")
plt.figure(figsize=(17,7))
sns.barplot(x=states.index,y="Postal Code",data=states)
plt.xticks(rotation = 90)
plt.xlabel=("STATES")
plt.ylabel=("Postal Code")
plt.show()
states=df.loc[:,["Segment","Sales"]]
states=states.groupby(by=["Segment"]).sum().sort_values(by="Sales")
#plt.figure(figsize=(10,7))
sbn.barplot(x=states.index,y="Sales",data=states)
plt.xticks(rotation = 90)
plt.xlabel=("SEGMENT")
plt.ylabel=("SALES")
plt.show()
sns.barplot(df['Postal Code'])
df.corr()
sns.heatmap(df.corr(),annot=True)
```
### OUTPUT
### SuperStore.csv
### df.head()
![Screenshot 2023-04-09 214313](https://user-images.githubusercontent.com/121166004/230784196-771e328c-83f9-4e31-8655-640599cc7fcd.png)


### df.info()
![Screenshot 2023-04-09 214326](https://user-images.githubusercontent.com/121166004/230784233-ce0b0588-05de-4544-90d9-7747fca7782d.png)


### df.describe()
![Screenshot 2023-04-09 214338](https://user-images.githubusercontent.com/121166004/230784250-77a4a969-3b47-423b-a569-5f030ffbba28.png)


### df.isnull().sum()
![Screenshot 2023-04-09 214451](https://user-images.githubusercontent.com/121166004/230784271-a7ff66db-6a66-49c1-abf1-27d00690cab2.png)


### AFTER CLEANING
### df.isnull().sum()
![Screenshot 2023-04-09 214458](https://user-images.githubusercontent.com/121166004/230784357-b1575e85-8704-4b1d-b4ab-d8f8d556cca3.png)


### Scatterplot
![Screenshot 2023-04-09 214508](https://user-images.githubusercontent.com/121166004/230784372-5fc747a7-ad35-4078-a92d-b2ad64b29f58.png)


### Barplot
![Screenshot 2023-04-09 214620](https://user-images.githubusercontent.com/121166004/230784398-af82d8e0-6ed7-4e39-8472-ae6ec49d0806.png)
![Screenshot 2023-04-09 214635](https://user-images.githubusercontent.com/121166004/230784416-1d190782-415a-4e0a-b4b8-37df97f095e5.png)
![Screenshot 2023-04-09 214734](https://user-images.githubusercontent.com/121166004/230784428-06244816-f585-4bf5-a18b-2b1e1369d36a.png)


### HeatMap
![Screenshot 2023-04-09 214751](https://user-images.githubusercontent.com/121166004/230784443-06222a2d-2c2e-484f-8249-2f88bfc55c59.png)


### RESULT
Thus the program to perform EDA on the given data set is successfully executed.

