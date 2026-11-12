# Monthly Rainfall Forecasting in Pakistan

**Status: In Progress**

This project forecasts **next-month rainfall (mm)** for 22 locations across Pakistan using 45 years of monthly climate data (1981–2026). Four models are compared, and the project also looks at how well they handle extreme rainfall months (flood-risk analysis).

## Dataset

- **File:** `pakistan_flood_locations_monthly_weather_1981_2026.csv`
- **Size:** 12,012 rows, 12 columns
- **Coverage:** 22 locations, 4 provinces (Sindh, Punjab, Khyber Pakhtunkhwa, Balochistan), monthly data from 1981 to 2026
- **Main columns:** location, province, latitude, longitude, year, month, monthly_rainfall_mm, avg_temperature_c, avg_max_temperature_c, avg_min_temperature_c, avg_relative_humidity, and others

## Initial Observations

- Rainfall is highly right-skewed: the median monthly rainfall is about 7 mm, while the maximum is about 1,032 mm.
- Because of this skew, both RMSE and MAE will be reported.

## Roadmap

### Phase 1: Data understanding and cleaning
- [x] Load the dataset and check its shape and summary statistics
- [x] Check missing values and duplicates
- [x] Sort data by location and date
- [x] Exploratory data analysis (seasonality, rainfall distribution, extreme months)

### Phase 2: Features and split
- [ ] Create lag features per location (previous month, same month last year, 3-month average)
- [ ] Encode `month` cyclically (sin/cos)
- [ ] Time-based train/test split (train: 1981–2018, test: 2019–2026)

> Only past information is used as features. Same-month weather values are not used, to avoid data leakage.

### Phase 3: Models
- [ ] Seasonal Naive (baseline)
- [ ] Linear Regression
- [ ] Random Forest (with feature importance)
- [ ] LSTM

### Phase 4: Evaluation
- [ ] Compare all models on the same test set using RMSE and MAE
- [ ] Plot actual vs predicted rainfall for selected locations

### Phase 5: Flood-risk analysis
- [ ] Define extreme rainfall months (for example, above the 95th percentile)
- [ ] Evaluate how each model performs on extreme months
- [ ] Compare locations by number of extreme months

### Phase 6: Documentation
- [ ] Add results table and graphs to this README
- [ ] Add limitations and conclusions

## Technologies

Python, Pandas, NumPy, Scikit-learn, TensorFlow/Keras, Matplotlib, Jupyter Notebook

## Results

*Coming soon.*
