# Project Progress: NAPS PM2.5 Data Analysis & Forecasting

This document tracks the progress of the NAPS PM2.5 Data Analysis & Forecasting project.

## Phases

- [x] **Phase 0: Project Setup & Environment Configuration**
    - [x] Initialize Git repository
    - [x] Create `.gitignore`
    - [x] Create `README.md` (initial)
    - [x] Commit initial project setup
    - [x] Set up remote repository (GitHub)
    - [x] Create directory structure
    - [x] Create `src/__init__.py`
    - [x] Set up virtual environment (`venv`)
    - [x] Install core libraries into `venv`
    - [x] Generate `requirements.txt`
    - [x] Commit dependencies and project structure
    - [x] Update `README.md` (as needed)
    - [x] Push initial project to GitHub

- [ ] **Phase 1: Data Acquisition (PM2.5 data 2000-2023)**
    - [x] Identify Data Source & Download Method (NAPS website) - Data source identified: [https://dbeaudoinfortin.github.io/NAPSDataAnalysis/](https://dbeaudoinfortin.github.io/NAPSDataAnalysis/)
    - [c] Document download process in `notebooks/01_data_download.ipynb` - Notebook created, pending download method details.
    - [ ] Download raw PM2.5 data for 2000-2023 into `data/raw/pm25/`
        - [ ] Automated download script (`src/data_loader.py`) (if feasible)
        - [ ] Manual download (if automation not feasible)
    - [ ] Log any download failures or missing files
    - [ ] Data Selection Notes (Pollutant: PM2.5, Years: 2000-2023, Stations: All initially)
    - [ ] Commit downloaded data (or script/manifest)

- [ ] **Phase 2: Data Cleaning & Aggregation**
    - [ ] Load and Combine Data (from `data/raw/pm25/`)
    - [ ] Standardize Column Names
    - [ ] Filter for PM2.5 (if necessary)
    - [ ] Handle Date and Time columns (create unified `datetime` column)
    - [ ] Ensure Consistent Units (µg/m³)
    - [ ] Handle Data Types (convert `value` to numeric)
    - [ ] Handle Missing Values & Invalid Readings (e.g., -999, negative values)
    - [ ] Remove Duplicates (based on station, datetime, parameter)
    - [ ] Data Aggregation (e.g., daily average per station, national daily average)
    - [ ] Handle NaNs after aggregation
    - [ ] Save Cleaned and Aggregated Data to `data/processed/`
    - [ ] Document cleaning choices in `notebooks/02_data_cleaning_aggregation.ipynb`
    - [ ] Commit cleaning scripts and documentation (and processed data if small)

- [ ] **Phase 3: Exploratory Data Analysis (EDA) & Visualizations**
    - [ ] Load Processed Data (from `data/processed/`)
    - [ ] Time Series Plots (overall trend, seasonal decomposition)
    - [ ] Distribution Plots (histograms, density plots, box plots by year/month)
    - [ ] Station-Specific Analysis (heatmaps, trend comparisons for key stations - if applicable)
    - [ ] Autocorrelation and Partial Autocorrelation (ACF/PACF) Plots
    - [ ] Correlation Matrix (if external data is added)
    - [ ] Save plots to `reports/figures/`
    - [ ] Document EDA findings in `notebooks/03_exploratory_data_analysis.ipynb`
    - [ ] Commit EDA notebook, utility scripts (`src/eda_utils.py`), and figures

- [ ] **Phase 4: Forecasting PM2.5 for 2024 & 2025**
    - [ ] Prepare Data for Modeling (select time series, train/validation/test split)
    - [ ] Feature Engineering (if applicable)
    - [ ] Define Evaluation Metrics (MAE, MSE, RMSE, MAPE)
    - [ ] Model Training & Validation
        - [ ] Baseline: Naive Forecast & Seasonal Naive
        - [ ] ARIMA / SARIMA (using `pmdarima.auto_arima`)
        - [ ] Facebook Prophet
        - [ ] LSTM (Optional, if time and resources permit)
        - [ ] Linear Regression with Lag Features (as another baseline)
    - [ ] Model Selection (based on validation metrics)
    - [ ] Retrain Chosen Model on Full Available Data (Train + Validation)
    - [ ] Final Evaluation on Test Set (e.g., 2023 data)
    - [ ] Generate Forecast for 2024 and 2025 (retrain on all data up to end of 2023)
    - [ ] Save trained models (if applicable)
    - [ ] Save forecast plots to `reports/figures/`
    - [ ] Document modeling process, choices, and results in `notebooks/04_forecasting_modelling.ipynb`
    - [ ] Commit modeling notebook, utility scripts (`src/modelling.py`), figures, and saved models

- [ ] **Phase 5: Export Results & Reporting**
    - [ ] Ensure Cleaned Data is saved (already done in Phase 2)
    - [ ] Ensure Plots are saved (already done in Phase 3 & 4)
    - [ ] Save Forecasts for 2024-2025 to `reports/forecasts/` (e.g., CSV with date, prediction, CIs)
    - [ ] Update `README.md` with project summary, key findings, model performance, and run instructions
    - [ ] Final Report (can be part of `04_forecasting_modelling.ipynb` or a separate document)
    - [ ] Commit final reports and forecast files
    - [ ] Tag final version (e.g., `v1.0`)
    - [ ] Push all changes and tags to GitHub

## Additional Considerations (Ongoing)
- [ ] External Data Integration (Weather, Wildfires, etc.)
- [ ] NAPS Metadata review
- [ ] Computational resource planning
- [ ] Model Interpretability & Limitations documentation
- [ ] Station-Level Forecasting strategy (if pursued) 