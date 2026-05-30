# Airports and Routes Analysis

Exploratory analysis of European airports and airline routes. The notebook answers the following questions:

1. How many airports and routes are in the dataset?
2. Which airports have the most departing routes?
3. Which airports appear most often as destinations?
4. What are the shortest and longest routes (Haversine distance based on coordinates)?
5. What does the distribution of route lengths look like - are short or long flights more common?

## Contents

```
airports-routes-analysis/
├── .venv/                              # Local virtual environment (created on setup)
├── airports.json                       # Airport list with names and coordinates
├── routes.json                         # Routes between airports with source and destination coordinates
├── airports_routes_analysis.ipynb      # Main analysis notebook
├── requirements.txt                    # Python dependencies
├── .gitignore
└── README.md
```

## Prerequisites

- **Python 3.12.10** (recommended).

## Setup

Run these commands from the project folder (PowerShell on Windows):

```powershell
# 1. Create a virtual environment in the project folder
python -m venv .venv

# 2. Upgrade pip and install all dependencies
.\.venv\Scripts\python.exe -m pip install --upgrade pip
.\.venv\Scripts\python.exe -m pip install -r requirements.txt
```

On macOS / Linux:

```bash
python3 -m venv .venv
.venv/bin/python -m pip install --upgrade pip
.venv/bin/python -m pip install -r requirements.txt
```

## Run the notebook

Launch JupyterLab using the local virtual environment:

```powershell
# Windows (PowerShell)
.\.venv\Scripts\jupyter-lab.exe airports_routes_analysis.ipynb
```

```bash
# macOS / Linux
.venv/bin/jupyter-lab airports_routes_analysis.ipynb
```

JupyterLab will open in the default browser. The notebook is already executed, so all tables and charts are visible immediately. To rerun, use `Run > Run All Cells`.

## What the notebook does

1. **Data loading** of both JSON files into pandas DataFrames.
2. **Basic information** (`info()`, `head()`, `describe()`) presented as styled tables.
3. **Question 1**: total counts of airports and routes.
4. **Question 2**: top 10 airports by number of departing routes (table + bar chart).
5. **Question 3**: top 10 airports by number of incoming routes (table + bar chart).
6. **Question 4**: shortest and longest routes computed using the **Haversine formula** for great-circle distance between geographical coordinates.
7. **Question 5**: distribution of route lengths (histogram, box plot, bins by distance category).
8. **Bonus map**: scatter plot of all airports by latitude and longitude, with hub size proportional to total route count.
9. **Summary** with the main findings.

## Cleaning up

To recreate the environment from scratch:

```powershell
Remove-Item -Recurse -Force .venv
python -m venv .venv
.\.venv\Scripts\python.exe -m pip install -r requirements.txt
```
