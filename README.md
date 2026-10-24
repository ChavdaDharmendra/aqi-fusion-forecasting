# Multi-Source Data Fusion for Air Quality Index Forecasting (CPCB + ERA5)

Companion code for the manuscript *"Multi-Source Data Fusion for Air Quality Index Forecasting Using Time-Series Models"*.

The notebook `AQI_Fusion_Forecasting.ipynb` reproduces all tables and figures of the paper:
leakage-free next-day AQI forecasting for five Indian cities (Delhi, Lucknow, Patna, Chennai, Hyderabad), walk-forward validation,
Diebold-Mariano tests, extreme-day (AQI > 300) analysis, SHAP grouped by data source, and fusion with ERA5 weather.

## How to run (Google Colab)
1. Download `city_day.csv` from Kaggle: *Air Quality Data in India (2015-2020)* (https://www.kaggle.com/datasets/rohanrao/air-quality-data-in-india) and put it in your Google Drive folder `MyDrive`.
2. Open the notebook in Colab and run all cells. Section 9a downloads the daily ERA5 weather from the free Open-Meteo archive and saves `era5_daily.csv` in the same Drive folder.
3. Set `QUICK = True` in the configuration cell for a fast smoke test (first city only).
4. Results are saved as CSV files in `MyDrive/aqi_fusion_results`.

A full run takes roughly 30 minutes on a CPU runtime. The optional GRU cell (Section 10) needs PyTorch and benefits from a GPU runtime; it has not been tested by the authors yet.

## Data and licences
- Air quality: CPCB data as compiled in the Kaggle dataset above (not redistributed here; please follow the dataset's terms).
- Weather: ERA5 reanalysis served by Open-Meteo (https://open-meteo.com), CC BY 4.0. Please cite Open-Meteo and ERA5 (Hersbach et al., 2020).
- Aerosol optical depth and fire counts are not used in the paper (future work); the notebook can load `aod_daily.csv` and `fire_daily.csv` if you provide them.

## Files
- `AQI_Fusion_Forecasting.ipynb` - full pipeline
- `requirements.txt` - Python packages (Colab already has most of them)
- `LICENSE` - MIT licence for the code

## Citation
Please cite the paper once published. Authors: Chavda Dharmendra, Harshwardhansinh Chauhan, Krushal Gohil, Vinayak Pandya, Chavda Jaimin.
