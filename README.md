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
- 
