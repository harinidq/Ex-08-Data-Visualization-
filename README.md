# Ex-08-Data-Visualization-

## AIM
To Perform Data Visualization on the given dataset and save the data to a file. 

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
NAME:M.D.HARINI

REGISTER NUMBER:212222230043
```
# DATA
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
import seaborn as sbn
df=pd.read_csv("/content/Superstore.csv",encoding='windows-1252')
df.head()

# DATA CLEANING
df.info()

df.isnull().sum()

1.Which Segment has Highest sales?
sbn.barplot(x=df['Segment'],y=df['Sales'])
plt.title("Highest Sales of the segment")

2.Which City has Highest profit?
sbn.barplot(x=df['City'],y=df['Profit'])
plt.title("Highest Profit of cities")

City=df.loc[:,["City","Profit"]]
df.head(5)
City=City.groupby(by=["City"]).sum().sort_values(by="Profit")
plt.figure(figsize=(10,10))
sbn.barplot(x=City.index,y="Profit",data=City)
plt.xticks(rotation = 90)
plt.xlabel=("City")
plt.ylabel=("Profit")
plt.show()

3.Which ship mode is profitable?
sbn.barplot(x=df['Ship Mode'],y=df['Profit'])
plt.title("Profitable Ship Mode")

4.Sales of the product based on region.
sbn.barplot(x=df['Sales'], y=df['Region'])
plt.title("Sales of Product based on Region")

5.Find the relation between sales and profit.
sbn.lineplot(x=df['Sales'], y=df['Profit'])
plt.title("Relation between Sales and Profit")

6.Find the relation between sales and profit based on the following category. i) Segment ii)City iii)States iv)Segment and Ship Mode v)Segment, Ship mode and Region

i) Segment
grouped_data = df.groupby('Segment')[['Sales', 'Profit']].mean()
# Create a bar chart of the grouped data
fig, ax = plt.subplots()
ax.bar(grouped_data.index, grouped_data['Sales'], label='Sales')
ax.bar(grouped_data.index, grouped_data['Profit'], bottom=grouped_data['Sales'], label='Profit')
ax.set_xlabel('Segment')
ax.set_ylabel('Value')
ax.legend()
plt.show()

ii) City
grouped_data = df.groupby('City')[['Sales', 'Profit']].mean()
# Create a bar chart of the grouped data
fig, ax = plt.subplots()
ax.bar(grouped_data.index, grouped_data['Sales'], label='Sales')
ax.bar(grouped_data.index, grouped_data['Profit'], bottom=grouped_data['Sales'], label='Profit')
ax.set_xlabel('City')
ax.set_ylabel('Value')
ax.legend()
plt.show()

iii) States
grouped_data = df.groupby('State')[['Sales', 'Profit']].mean()
# Create a bar chart of the grouped data
fig, ax = plt.subplots()
ax.bar(grouped_data.index, grouped_data['Sales'], label='Sales')
ax.bar(grouped_data.index, grouped_data['Profit'], bottom=grouped_data['Sales'], label='Profit')
ax.set_xlabel('State')
ax.set_ylabel('Value')
ax.legend()
plt.show()

iv)Segment and Ship Mode
grouped_data = df.groupby(['Segment', 'Ship Mode'])[['Sales', 'Profit']].mean()
pivot_data = grouped_data.reset_index().pivot(index='Segment', columns='Ship Mode', values=['Sales', 'Profit'])
# Create a bar chart of the grouped data
fig, ax = plt.subplots()
pivot_data.plot(kind='bar', ax=ax)
ax.set_xlabel('Segment')
ax.set_ylabel('Value')
plt.legend(title='Ship Mode')
plt.show()

v)Segment, Ship mode and Region
grouped_data = df.groupby(['Segment', 'Ship Mode','Region'])[['Sales', 'Profit']].mean()
pivot_data = grouped_data.reset_index().pivot(index=['Segment', 'Ship Mode'], columns='Region', values=['Sales', 'Profit'])
sns.set_style("whitegrid")
sns.set_palette("Set1")
pivot_data.plot(kind='bar', stacked=True, figsize=(10, 5))
plt.legend(title='Region')
plt.show()
```

# OUPUT
![image](https://github.com/harinidq/Ex-08-Data-Visualization-/assets/113497680/63df2bc9-0c25-4959-b936-d8e2e5b565f0)
![image](https://github.com/harinidq/Ex-08-Data-Visualization-/assets/113497680/f7adf004-063a-473d-b9ef-372b955ba323)
![image](https://github.com/harinidq/Ex-08-Data-Visualization-/assets/113497680/7b68a26c-269d-4895-bbb1-e251e9087682)
![image](https://github.com/harinidq/Ex-08-Data-Visualization-/assets/113497680/73c7bb4c-b129-4a7c-a071-fa0b790d9e09)
![image](https://github.com/harinidq/Ex-08-Data-Visualization-/assets/113497680/67364e77-efab-4c1c-8a28-acc1f759c9e0)
![image](https://github.com/harinidq/Ex-08-Data-Visualization-/assets/113497680/15e74830-0200-4dd3-b9f2-95b09c18e237)
![image](https://github.com/harinidq/Ex-08-Data-Visualization-/assets/113497680/080b49fd-01e1-4285-805b-92e721261ad3)
![image](https://github.com/harinidq/Ex-08-Data-Visualization-/assets/113497680/a32ec6da-edf0-425b-9c22-0368bda68871)
![image](https://github.com/harinidq/Ex-08-Data-Visualization-/assets/113497680/8058c566-7766-42ad-bbd2-1c793f945f1a)
![image](https://github.com/harinidq/Ex-08-Data-Visualization-/assets/113497680/911c6400-de87-402b-9114-71c99507570e)
![image](https://github.com/harinidq/Ex-08-Data-Visualization-/assets/113497680/dbf3daae-e455-456e-9fcb-88672b263042)
![image](https://github.com/harinidq/Ex-08-Data-Visualization-/assets/113497680/651c7da6-5387-4058-8dbf-2a2b41647678)
![image](https://github.com/harinidq/Ex-08-Data-Visualization-/assets/113497680/83bc7894-5a60-4c1e-989d-7af6222f7052)
![image](https://github.com/harinidq/Ex-08-Data-Visualization-/assets/113497680/2661ca70-5e58-491c-bd7e-9a1f94c9886e)
![image](https://github.com/harinidq/Ex-08-Data-Visualization-/assets/113497680/34c38542-b917-4489-a1eb-92fa19d0f11e)

# RESULT:
Hence the data visualization method for the given dataset applied successfully.








