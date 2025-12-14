# Bike Sharing Demand Analysis (Exploratory Data Analysis)

## Project Overview
This project performs exploratory data analysis (EDA) on a bike sharing dataset to understand how demand varies with time, weather, and seasonal factors. The goal is to uncover clear, interpretable patterns in ridership that can later be used for forecasting and demand planning.

The analysis focuses on correct aggregation logic, clean visualizations, and future-safe pandas usage.

---

## Dataset Description
The dataset contains daily aggregated bike rental data with environmental and calendar attributes.

**Shape:** 731 rows × 16 columns

### Key Columns
- `dteday` – Date of observation
- `season` – Season (1: Spring, 2: Summer, 3: Fall, 4: Winter)
- `yr` – Year indicator
- `mnth` – Month (1–12)
- `holiday` – Whether the day is a holiday
- `weekday` – Day of week (0–6)
- `workingday` – Working day indicator
- `weathersit` – Weather situation category
- `temp` – Normalized temperature
- `atemp` – Normalized feeling temperature
- `hum` – Humidity
- `windspeed` – Wind speed
- `casual` – Casual users
- `registered` – Registered users
- `cnt` – Total bike rentals (target variable)

---

## Data Cleaning
The following steps were applied:
- Verified numeric columns and handled invalid values
- Used binning (`pd.cut`) for continuous weather variables
- Explicitly set `observed=True` in groupby operations to ensure future compatibility with pandas

---

## Exploratory Data Analysis

### Univariate Analysis
The following distributions were analyzed:
- Total bike rentals (`cnt`)
- Casual vs registered users
- Temperature, humidity, and windspeed
- Monthly and weekday rental patterns

These plots help understand demand spread, skewness, and seasonality.

---

### Bivariate Analysis (Demand vs External Factors)
To study how demand changes with environmental conditions, the following relationships were visualized:

- Average ridership vs temperature
- Average ridership vs feeling temperature
- Average ridership vs humidity
- Average ridership vs windspeed
- Average ridership by season
- Average ridership by weather situation

Continuous variables were binned to avoid noisy groupings and to produce smooth, interpretable trends.

---

## Visualizations
- Implemented using Matplotlib and pandas plotting
- Multiple colormaps used (`viridis`, `plasma`, `cividis`, `magma`, `Set2`)
- All figures saved to the `artifacts/` directory for reporting and GitHub preview

---

## Project Structure
project_bikeshare_eda/
├─ notebooks/
│  └─ EDA_BikeShare.ipynb
├─ data/
│  └─ bikeshare_trips.csv
├─ artifacts/
│  ├─ trip_duration_dist.png
│  ├─ hourly_trips.png
│  ├─ weekday_trips.png
│  ├─ ridership_vs_temp.png
│  └─ bikeshare_cleaned_snapshot.csv
├─ src/
│  └─ utils.py
└─ README.md


---

## Key Insights
- Bike demand increases with moderate temperature and declines at extreme conditions
- High humidity and strong winds negatively impact ridership
- Seasonal effects are significant, with peak demand in warmer seasons
- Weather conditions play a strong role in daily usage variability

---

## Tools & Libraries
- Python 3.x
- pandas
- numpy
- matplotlib
- seaborn
- Jupyter Notebook / JupyterLab / Google Colab

---

## Next Steps
- Feature engineering for predictive modeling
- Time-series analysis using `dteday`
- Demand forecasting using regression or machine learning models
- Interactive visualization using Streamlit

---

## Author
Data Science EDA Project  
Focus: demand analysis, clean aggregation, and interpretable insights

