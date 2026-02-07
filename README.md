### EX4 Implementation of Cluster and Visitor Segmentation for Navigation patterns
### DATE: 
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
# Visitor segmentation based on characteristics
# read the data
import pandas as pd
df = pd.read_csv("C:/Users/admin/Downloads/clustervisitor.csv")
df
import matplotlib.pyplot as plt

cluster = {"young" : (df['Age'] <= 30) , "middle" : (df['Age'] > 30) & (df['Age'] <= 50) , "old" : (df['Age'] > 50)}
count = []
for group , condition in cluster.items():
  visitors = df[condition]
  count.append(len(visitors))
  print(f"visitors in {group} age are\n")
  print(visitors)
  print("\n")
  print(count)
# Perform segmentation based on characteristics (e.g., age groups)
pandas_df = pd.DataFrame(df)
np.random.seed(42) # for reproducibility
income = np.random.randint(30, 120, size=len(pandas_df)) * 1000
pandas_df['Income'] = income

# Save the updated DataFrame to a new CSV file
pandas_df.to_csv('C:/Users/admin/Downloads/clustervisitor_with_income.csv', index=False)

print("Added 'Income' column to the DataFrame and saved it as 'clustervisitor_with_income.csv'.")
print("Here's the updated DataFrame:")
display(pandas_df.head())

```
### Output:
<img width="1920" height="1200" alt="image" src="https://github.com/user-attachments/assets/a627ac12-ad8a-4642-9e8c-881eb62a6f2b" />
<img width="695" height="414" alt="image" src="https://github.com/user-attachments/assets/03559b51-781e-4ddb-8351-9a76cb543022" />
<img width="1485" height="1115" alt="image" src="https://github.com/user-attachments/assets/645801d8-e00d-42ee-8160-c446544dd920" />




### Visualization:
```python
# Create a list to store counts of visitors in each age group
plt.figure(figsize=(8, 6))
plt.bar(age_group_labels, visitor_counts, color='skyblue')
plt.xlabel('Age Groups')
plt.ylabel('Number of Visitors')
plt.title('Visitor Distribution Across Age Groups')
plt.show()

# Count visitors in each age group
plt.scatter(df['Age'],df['Income'],c = df['Cluster'])
plt.xlabel('Age')
plt.ylabel('Salary in thousands')
plt.title('Kmeans Cluster')
plt.show()
 


```
### Output:
<img width="1855" height="1138" alt="image" src="https://github.com/user-attachments/assets/39cecc5a-8097-4781-84cc-011375143efb" />

<img width="1879" height="1131" alt="image" src="https://github.com/user-attachments/assets/9d5147e9-37b0-4d13-82aa-9854a792535a" />

### Result:
 To implement Cluster and Visitor Segmentation for Navigation patterns in Python executed succesfully
