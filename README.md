### EX4 Implementation of Cluster and Visitor Segmentation for Navigation patterns
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
# read the data
import matplotlib.pyplot as plt
import pandas as pd
visitor_df = pd.read_csv('/content/clustervisitor.csv')

# Perform segmentation based on characteristics (e.g., age groups)
age_groups = {
    'Young': visitor_df['Age'] <= 30,
    'Middle-aged': (visitor_df['Age'] > 30) & (visitor_df['Age'] <= 50),
    'Elderly': visitor_df['Age'] > 50
}

for group, condition in age_groups.items():  
    visitors_in_group = visitor_df[condition] 
    print(f"Visitors in {group} age group:")
    print(visitors_in_group)
```
### Output:
```
Visitors in Young age group:
    User_ID  Age  Gender      Location
0         1   25  Female      New York
2         3   22    Male       Chicago
4         5   30    Male         Miami
6         7   28  Female        Boston
11       12   27    Male        Austin
14       15   29  Female  Philadelphia
17       18   26    Male   Minneapolis
27       28   24  Female    Sacramento
Visitors in Middle-aged age group:
    User_ID  Age  Gender         Location
1         2   40    Male      Los Angeles
5         6   45  Female    San Francisco
7         8   50    Male          Seattle
8         9   35    Male           Dallas
9        10   48  Female          Atlanta
10       11   33  Female  Washington D.C.
12       13   38    Male           Denver
13       14   42  Female          Phoenix
15       16   36    Male         Portland
18       19   31  Female        Charlotte
19       20   47    Male        San Diego
20       21   34    Male         San Jose
21       22   39  Female     Indianapolis
22       23   43    Male        Las Vegas
23       24   32  Female          Orlando
24       25   37    Male            Tampa
25       26   44  Female        St. Louis
26       27   49    Male      Kansas City
28       29   41    Male        Cleveland
29       30   46  Female       Pittsburgh
Visitors in Elderly age group:
    User_ID  Age  Gender Location
3         4   55  Female  Houston
16       17   51  Female  Detroit
```
### Visualization:
```python
# Create a list to store counts of visitors in each age group
visitor_counts=[]

# Count visitors in each age group
for group,condition in age_groups.items():
  visitors_in_group=visitor_df[condition]
  visitor_counts.append(len(visitors_in_group))
    
# Define age group labels and plot a bar chart
age_group_labels=list(age_groups.keys())

plt.figure(figsize=(8, 6))
plt.bar(age_group_labels, visitor_counts, color='skyblue')
plt.xlabel('Age Groups')
plt.ylabel('Number of Visitors')
plt.title('Visitor Distribution Across Age Groups')
plt.show()
```
### Output:
![image](https://github.com/user-attachments/assets/69fffb76-4836-4261-9a38-f13e61abae90)

### Result:
Thus the cluster and visitor segmentation for navigation patterns was implemented successfully in python.
