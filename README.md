# Machine-Learning-Projects

Coursework completed as part of the *Introduction to Machine Learning* lectures
by Prof. Dr. Mingchen Gao at the University at Buffalo (course CSE 587, Data
Intensive Computing).

## Overview

This repository contains a two-phase data analysis project that explores
global land and surface temperature data to investigate long-term warming
trends. Phase 1 focuses on exploratory data analysis (EDA) and visualization,
while Phase 2 builds a time-series forecasting model to study temperature
trends over time. The notebooks are written to run in Google Colab.

## Dataset

The project uses the
[Climate Change: Earth Surface Temperature Data](https://www.kaggle.com/datasets/berkeleyearth/climate-change-earth-surface-temperature-data)
dataset from Berkeley Earth (via Kaggle). The notebooks read the following CSV
files (mounted from Google Drive in Colab):

- `GlobalTemperatures.csv` — global average land/ocean temperatures over time
- `GlobalLandTemperaturesByCity.csv`
- `GlobalLandTemperaturesByCountry.csv`
- `GlobalLandTemperaturesByMajorCity.csv`
- `GlobalLandTemperaturesByState.csv`

The CSV files are **not** committed to this repository. Download them from
Kaggle and update the file paths in the notebooks to point to your local copy
(the notebooks currently expect them under
`/content/drive/MyDrive/Colab Notebooks/Datasets/`).

## Notebooks

### `CSE_587_ProjectPhase1.ipynb` — Exploratory Data Analysis

Surveys all five temperature datasets to identify the most relevant one and
performs EDA on the global temperatures data. Operations include:

- Summary statistics (mean, standard deviation, min, max) and inspection of
  data types
- Counting null values and unique values per column
- Missing-value visualization (`missingno`)
- Average temperature aggregated by country, by month, and by latitude
- Geospatial visualization of data-point locations on a map, including data
  binned by latitude (`plotly`)

### `Phase_2.ipynb` — Time-Series Analysis and Forecasting

Builds on the cleaned data to study warming trends over the years:

- Groups data by year to surface long-term trends
- Tests the series for stationarity using the Augmented Dickey-Fuller test
  (`adfuller`) and inspects constant mean / standard deviation
- Examines autocorrelation and partial autocorrelation (`plot_acf`,
  `plot_pacf`)
- Fits an **ARIMA** model (`statsmodels`) to the temperature time series
- Evaluates predictions with mean squared error and mean absolute percentage
  error

## Methods and Algorithms

- Exploratory data analysis and aggregation with pandas
- Data visualization with matplotlib, seaborn, plotly, and missingno
- Stationarity testing (Augmented Dickey-Fuller)
- ACF / PACF analysis
- ARIMA time-series forecasting
- Error metrics: MSE, MAPE

## Tech Stack

- Python 3 (Jupyter / Google Colab notebooks)
- pandas, numpy
- matplotlib, seaborn, plotly, missingno
- statsmodels (ARIMA, stationarity tests, ACF/PACF)
- scikit-learn (evaluation metrics)

## How to Run

### Google Colab (recommended)

Each notebook includes an "Open in Colab" badge at the top. Open it, mount your
Google Drive, place the Kaggle CSV files under the expected `Datasets`
directory, and run the cells top to bottom.

### Locally

1. Clone the repository:
   ```bash
   git clone https://github.com/JayeshSuryavanshi/Machine-Learning-Projects.git
   cd Machine-Learning-Projects
   ```
2. (Optional) create and activate a virtual environment.
3. Install dependencies:
   ```bash
   pip install pandas numpy matplotlib seaborn plotly missingno statsmodels scikit-learn jupyter
   ```
4. Download the dataset from Kaggle and update the CSV paths in the notebooks.
5. Launch Jupyter and run the notebooks:
   ```bash
   jupyter notebook
   ```
   Run `CSE_587_ProjectPhase1.ipynb` first, then `Phase_2.ipynb`.

## Repository Structure

```
.
├── CSE_587_ProjectPhase1.ipynb   # Phase 1: exploratory data analysis
├── Phase_2.ipynb                 # Phase 2: time-series analysis (ARIMA)
└── README.md
```

## Acknowledgements

Completed as coursework for the *Introduction to Machine Learning* lectures by
Prof. Dr. Mingchen Gao, University at Buffalo. Dataset courtesy of Berkeley
Earth via Kaggle.
