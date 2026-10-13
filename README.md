# Toronto Bus Delays vs. Weather (January 2024)

A Python analysis of whether weather is related to bus delays in Toronto. The notebooks clean and combine TTC bus delay records with hourly weather observations for **January 2024**, then compare them day by day.

## Notebooks (run in this order)

| Notebook | What it does |
|----------|--------------|
| `weather_files_merge.ipynb` | Combines the daily January weather CSV files into one table and keeps four columns: date/time, temperature, precipitation, relative humidity |
| `preprocessing1.ipynb` | Renames columns to consistent names, splits date and time, saves intermediate Excel files |
| `preprocessing2.ipynb` | Fixes data types, lower-cases text fields, drops delay rows with no route, labels missing directions as "unknown", saves the cleaned files |
| `analysis1.ipynb` | Summary statistics for weather and delays, daily aggregation, a merge of the two datasets on date, a scatter plot and a correlation heatmap |

**Tools:** Python, pandas, NumPy, matplotlib, seaborn.

## What the analysis found (from the notebook output)

- Route 32 had the most delays in January (149), and the peak delay hour was 17:00.
- Most delays were recorded at Kennedy Station, and northbound was the most affected direction.
- Across the 31 days, total daily precipitation and total daily delay minutes had a correlation of about **0.31**, a weak-to-moderate positive relationship. Daily average temperature was close to unrelated (about 0.07).

## Limitations

- One month of data, so only 31 daily observations. A correlation of 0.31 on 31 points is suggestive, not conclusive, and does not show that weather causes delays.
- This is descriptive analysis; no predictive model is built.
- The raw data files are not included in this repository. File paths in the notebooks point to a local drive and need to be changed to run them elsewhere.
- The notebooks do not all use the same file names for the intermediate Excel files, so the output of `preprocessing2.ipynb` may need renaming before `analysis1.ipynb` reads it.

## Author

Sharad Patel, https://github.com/SharadPatel1703
