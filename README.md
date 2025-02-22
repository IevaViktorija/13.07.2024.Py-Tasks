# 13.07.2024.Py-Tasks
Data frames, PANDAS, MATPLOTLIBS

# 1st Task:

# V1
```py
dataset = pd.read_csv('/content/transaction_dataset (1).csv')

gender_counts = dataset['Gender'].value_counts(dropna=False).reset_index()
gender_counts.columns = ['Gender', 'Count']
colors = []
for gender in gender_counts['Gender']:
    if gender == 'F':
        colors.append('red')
    elif gender == 'M':
        colors.append('darkblue')
    else:
        colors.append('gray')  

plt.bar(gender_counts['Gender'].astype(str), gender_counts['Count'], color=colors)
plt.title('Count of customers by Gender')
plt.xlabel('Gender')
plt.ylabel('Count')
plt.grid(True)
plt.show()
```

# V2
```py
gender_counts = dataset['Gender'].value_counts(dropna=False)
#Create a bar chart that shows the count of customers for each unique value in the 'Gender' column (including NaN values)
gender_counts.plot(kind='bar', color='purple')
plt.xlabel('Gender')
plt.ylabel('Count')
plt.title('Count of Customers by Gender')
plt.grid(True)
plt.show()
```

# 2nd Task:
```py
import pandas as pd
import matplotlib.pyplot as plt

file_path = '/content/transaction_dataset.csv'
df = pd.read_csv(file_path)

name_df = df['Name'].value_counts()

top_5_names = name_df.iloc[:5]

top_5_names.plot(kind='barh', color='purple')
plt.xlabel('Count')
plt.ylabel('Name')
plt.title('5 most popular names in dataset')
plt.gca().invert_yaxis()  #most polular name
plt.show()
```

# 3rd Task:
```py
import pandas as pd

file_path = '/content/transaction_dataset.csv'
df = pd.read_csv(file_path)

# Apply filter
filter_df = df[(df['Category'] == 'Clothing') & (df['Gender'] == 'M')]

# rows - number rows in filter_df
rows = len(filter_df)

print(f'The DataFrame has {rows} rows after filtering.')
```
