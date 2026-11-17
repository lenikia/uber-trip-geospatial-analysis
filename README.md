# Uber Trip Geospatial Analysis

A Python-based data science project for analysing Uber pickup locations in New York City using geospatial clustering, temporal analysis, and demand forecasting.

## Features

- Explore and preprocess over 1 million Uber pickup records.
- Identify geographical clusters using K-Means.
- Compare K-Means and DBSCAN clustering algorithms.
- Evaluate clustering using the Elbow Method, Silhouette Score, and Gap Statistic.
- Analyse hourly, daily, and weekly pickup patterns.
- Examine changes in geographical activity over time.
- Forecast daily pickup demand using Seasonal Naïve and Day-of-Week Average methods.
- Evaluate forecasting accuracy using MAE, MSE, and RMSE.
- Generate visualisations and export analysis results.

## Getting Started

### Prerequisites

- Python 3.10 or higher
- pip
- Jupyter Notebook or Visual Studio Code

### Install Dependencies

Navigate to the project directory:

```bash
cd uber-trip-geospatial-analysis
```

Create and activate a virtual environment:

```bash
python3 -m venv .venv
source .venv/bin/activate
```

Install the required libraries:

```bash
pip install pandas numpy matplotlib seaborn scikit-learn pyproj jupyter
```

### Dataset

Place the dataset inside the `data/` folder:

```text
data/uber-data.csv
```

The dataset contains 1,028,136 Uber pickup records from September 2014, with the following columns:

- `Date/Time` — Pickup date and time
- `Lat` — Pickup latitude
- `Lon` — Pickup longitude
- `Base` — Dispatching base identifier

### Run the Analysis

Open the project in Visual Studio Code or Jupyter Notebook.

Run the notebooks in the following order:

1. `01_data_exploration.ipynb` — Data inspection, preprocessing, and initial visualisation.
2. `02_geospatial_clustering.ipynb` — K-Means, DBSCAN, and clustering evaluation.
3. `03_temporal_analysis.ipynb` — Hourly, daily, and weekly activity patterns.
4. `04_demand_forecasting.ipynb` — Forecasting models and performance evaluation.

**Important:** Run the clustering notebook before the temporal and forecasting notebooks, as it generates the dataset containing the cluster assignments.

## Project Structure

```text
uber-trip-geospatial-analysis/
├── data/
│   └── uber-data.csv
├── notebooks/
│   ├── 01_data_exploration.ipynb
│   ├── 02_geospatial_clustering.ipynb
│   ├── 03_temporal_analysis.ipynb
│   └── 04_demand_forecasting.ipynb
├── figures/
│   └── Generated plots (.png)
├── results/
│   └── Processed datasets and results (.csv)
├── report/
│   └── Academic report
├── .gitignore
└── README.md
```

## Methods

### Geospatial Clustering

- **K-Means:** Groups pickup locations based on geographical proximity.
- **DBSCAN:** Identifies density-based clusters and noise observations.
- **Cluster Validation:** Elbow Method, Silhouette Score, and Gap Statistic.

The final analysis uses K-Means with seven geographical clusters.

### Temporal Analysis

Pickup activity is analysed by hour, date, and weekday. Daily mean geographical coordinates are also calculated to examine changes in the location of activity within each cluster.

### Demand Forecasting

Two forecasting models are evaluated:

- **Seasonal Naïve:** Predicts daily activity using the same day of the previous week.
- **Day-of-Week Average:** Predicts activity using historical averages for each weekday.

Training data: September 1–23, 2014.  
Testing data: September 24–30, 2014.

## Results

The clustering analysis identified seven geographical groups, with approximately 78.5% of pickups concentrated in two clusters.

The Day-of-Week Average forecasting method achieved better overall accuracy than Seasonal Naïve.

| Metric | Seasonal Naïve | Day-of-Week Average |
|---|---:|---:|
| MAE | 443.10 | 356.50 |
| MSE | 565,286.78 | 420,257.77 |
| RMSE | 751.86 | 648.27 |

## Output Files

- `figures/` — Generated clustering, temporal analysis, and forecasting visualisations.
- `results/` — Cluster assignments, evaluation metrics, and aggregated activity data.
- `report/` — Academic report documenting the methodology, findings, and limitations.

## Technologies

- Python
- Pandas and NumPy
- Scikit-learn
- Matplotlib and Seaborn
- PyProj
- Jupyter Notebook
- Visual Studio Code

## Author

**Lenikia Ouana**

MSc Data Science and Business Analytics  
University of Warsaw

Unsupervised Learning — Academic Project, 2026
