# datafun-04-jupyter

## Commands Used

```
git add .
git commit -m "initial commit"
git push -u origin main
```
## External Dependencies

```
jupyterlab: Enables Jupyter notebooks.
pandas: Handles data manipulation and analysis, focusing on structured (tabular/panel) data.
pyarrow: Required by pandas; facilitates interaction between pandas and the Arrow format.
matplotlib: Basic tools for plotting and visualizing data.
seaborn: Simplifies complex visualizations and statistical plots, built on matplotlib.
```

## Import Dependencies

```
import matplotlib.pyplot as plt
import pandas as pd
import seaborn as sns
```

## Data Acquisition
```
# Load the Iris dataset into DataFrame
df = sns.load_dataset('iris')

# Inspect first rows of the DataFrame
print(df.head())
```

## Initial Data Inspection
```
print(df.head(10))
print(df.shape)
print(df.dtypes)
```

## Initial Descriptive Statistic
```
print(df.describe())
```

## Initial Data Distribution for Numerical Columns
```
# Inspect histogram by numerical column
df['sepal_length'].hist()

# Inspect histograms for all numerical columns
df.hist()

# Show all plots
plt.show()
```

## Initial Data Distribution for Categorical Columns
```
# Inspect value counts by categorical column
df['species'].value_counts()

# Inspect value counts for all categorical columns
for col in df.select_dtypes(include=['object', 'category']).columns:
    # Display count plot
    sns.countplot(x=col, data=df)
    plt.title(f'Distribution of {col}')
    plt.show()

# Show all plots
plt.show()
```

## Initial Data Transformation and Data Engineering
```
# Renaming a column
df.rename(columns={'sepal_length': 'Sepal Length'}, inplace=True)

# Adding a new column
df['Sepal Area'] = df['Sepal Length'] * df['sepal_width']
```

## Initial Visualization
```
sns.pairplot(df, hue='species')
plt.show()
```