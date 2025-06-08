# datafun-06-eda

This project uses Jupyter to perform exploratory data analysis (EDA) on the Penguins dataset. This dataset shows the measurements of bills, flippers, and body mass for three species of penguins observed in Palmer Archipelago. The dataset can be found at [penguins](https://github.com/mwaskom/seaborn-data/blob/master/penguins.csv). 

Steps already completed:
1. [Set up the Machine](https://github.com/denisecase/pro-analytics-01/blob/main/01-machine-setup/MACHINE-SETUP.md)
2. [Initialized a new Project](https://github.com/denisecase/pro-analytics-01/blob/main/02-project-initialization/PROJECT-INITIALIZATION.md)

## Before/During Working on the Project
1. Pull the Latest Changes from GitHub 
   
```shell
git pull origin main
```

2. Create Virtual Environment

```powershell
python3 -m venv .venv
```

3. Activate the Project Virtual Environment

```powershell
source .venv/bin/activate
```

4.  Install Dependencies As Needed 

```powershell
source .venv/bin/activate
python3 -m pip install --upgrade pip setuptools wheel
python3 -m pip install -r requirements.txt
```

5. Run Script 

```powershell
source .venv/bin/activate
python3 demo-script.py
```

## Git add-commit-push command 
```shell
git add .
git commit -m "custom message"
git push -u origin main
```

## Create Jupyter Notebook and Select Kernel
- Create new Jupyter notebook: Command + Shift + P then type "Create: New Jupyter Notebook"
- Rename notebook: File -> Save As...
- Set kernel: click "Select Kernel" in top right corner and select local .venv

### Markdown Cells
- text-based content (formatting, lists, headings)

### Code Cells
- write and run programming (e.g. Python) code 

## Exploratory Data Analysis (EDA) on Penguins Dataset
- Import dependencies
```python
import pandas as pd
import seaborn as sns
import matplotlib
import numpy
import jupyterlab
import matplotlib.pyplot as plt
from matplotlib.axes import Axes
```
- Load the Penguins dataset using seaborn's built-in datasets
- Perform initial data inspection 
```python
penguins_df.head(10)
penguins_df.shape
penguins_df.dtypes
penguins_df.info()
```
- Perform initial descriptive statistics
```python
penguins_df.describe()
```
- Create initial data distribution for numerical columns
```python
penguins_df['flipper_length_mm'].hist()
penguins_df.hist()
matplotlib.pyplot.show()
```

- Create initial data distribution for categorical columns
```python
penguins_df['species'].value_counts()
for col in penguins_df.select_dtypes(include=['object', 'category']).columns:
    # Display count plot
    sns.countplot(x=col, data=penguins_df)
    matplotlib.pyplot.title(f'Distribution of {col}')
    matplotlib.pyplot.show()
matplotlib.pyplot.show()
```

- Perform initial data transformation and feature engineering
```python
penguins_df.rename(columns={'flipper_length_mm': 'Flipper Length'}, inplace=True)
penguins_df['Bill Area'] = penguins_df['bill_length_mm'] * penguins_df['bill_depth_mm']
```
- Create initial visualizations 
  - Pairplot
```python
sns.pairplot(penguins_df, hue='species')
matplotlib.pyplot.show()
```
  - Scatterplot
```python
scatter_plt: Axes= sns.scatterplot(
    data=penguins_df, x="Flipper Length", y="body_mass_g", hue="species", style="sex"
)
scatter_plt.set_xlabel("Flipper Length (mm)")
scatter_plt.set_ylabel("Body Mass (g)")
scatter_plt.set_title("Flipper Length vs. Body Mass (by Sex)")
matplotlib.pyplot.show()
```
  - Heatmap
```python
correlation_matrix = penguins_df.corr(numeric_only=True)
print("Correlation Matrix")
print(correlation_matrix)
plt.figure(figsize=(10, 8))
sns.heatmap(correlation_matrix, annot=True, cmap='coolwarm')
plt.title('Penguins Dataset Heatmap')
plt.show()
```
