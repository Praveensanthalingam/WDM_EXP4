### EX4 Implementation of Cluster and Visitor Segmentation for Navigation patterns
### DATE: 07.02.2026
### AIM: To implement Cluster and Visitor Segmentation for Navigation patterns in Python.
### Description:
<div align= "justify">Cluster visitor segmentation refers to the process of grouping or categorizing visitors to a website, 
  application, or physical location into distinct clusters or segments based on various characteristics or behaviors they exhibit. 
  This segmentation allows businesses or organizations to better understand their audience and tailor their strategies, marketing efforts, 
  or services to meet the specific needs and preferences of each cluster.</div>
  
### Procedure:
1) Read the CSV file: Use pd.read_csv to load the CSV file into a pandas DataFrame.
2) Define Age Groups by creating a dictionary containing age group conditions using Boolean conditions.
3) Segment Visitors by iterating through the dictionary and filter the visitors into respective age groups.
4) Visualize the result using matplotlib.

### Program:
```python
PROGRAM 1

# Visitor segmentation based on characteristics
# read the data
import pandas as pd
import matplotlib.pyplot as plt
df = pd.read_csv('clustervisitor (1).csv')
cluster = {"young" : (df['Age'] <= 30) , "middle" : (df['Age'] > 30) & (df['Age'] <= 50) , "old" : (df['Age'] > 50)}
for group, condition in cluster.items():
    visitors = df[condition]
    visitor_count = len(visitors)

    print(f"\nVisitors in {group} group:")
    print(visitors)
    print(f"count: {visitor_count}")

# Perform segmentation based on characteristics (e.g., age groups)
PROGRAM 2

from sklearn.preprocessing import StandardScaler
from sklearn.cluster import KMeans

df1=df['Age']
df2=df['Income']
df3=pd.concat([df1, df2], axis=1)
s=StandardScaler()
newdf=s.fit_transform(df3)
k=KMeans (n_clusters=4, random_state=55)
df3['cluster']=k.fit_predict(newdf)
df3

```
### Output:
PROGRAM 1

<img width="452" height="832" alt="image" src="https://github.com/user-attachments/assets/aa97a4af-2277-467a-8df7-aa0b027c80f9" />

PROGRAM 2

<img width="344" height="868" alt="image" src="https://github.com/user-attachments/assets/64555fee-8a87-40f8-b4ff-06494ac06144" />

### Visualization:
```python
PROGRAM 1
# Create a list to store counts of visitors in each age group
plt.figure(figsize=(8, 6))
plt.bar(cluster.keys(), count, color='skyblue')
plt.xlabel('Age Groups')
plt.ylabel('Number of Visitors')
plt.title('Visitor Distribution Across Age Groups')
plt.show()

PROGRAM 2
# Count visitors in each age group
import matplotlib.pyplot as plt
plt.figure(figsize=(10, 6))
scatter = plt.scatter(df3['Age'], df3['Income'], c=df3['cluster'], cmap='viridis', s=100, edgecolors='k')
plt.xlabel('Age ')
plt.ylabel('Income')
plt.title('Visitor Distribution Across Age Group')
plt.colorbar(scatter, label='Cluster')
plt.show()
    


plt.figure(figsize=(8, 6))
plt.bar(age_group_labels, visitor_counts, color='skyblue')
plt.xlabel('Age Groups')
plt.ylabel('Number of Visitors')
plt.title('Visitor Distribution Across Age Groups')
plt.show()
```
### Output:
PROGRAM 1

<img width="816" height="643" alt="image" src="https://github.com/user-attachments/assets/90e8bc91-69ca-432f-b433-4b31b6701b52" />


PROGRAM 2

<img width="950" height="638" alt="image" src="https://github.com/user-attachments/assets/5abcb3fc-dc3a-4104-aae4-53c7726149f8" />

### Result:
Thus the  implement Cluster and Visitor Segmentation for Navigation patterns in Python is successfull
