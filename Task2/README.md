# Weather Time-Series Task 5 — Final revised notebook

- Location: Banha, Qalyubia, Egypt
- Source: NASA POWER Daily Point API
- Intended data window: 2020-01-01 through the latest completed day available at run time
- Target: daily mean temperature (°C)

## Run
1. Install packages: `pip install -r requirements.txt`
2. Open `Weather_Time_Series_Task5_2020_onward_FINAL.ipynb` in Jupyter or Google Colab.
3. Run all cells from top to bottom with an internet connection so the NASA POWER API can be queried.

## Important evaluation correction
The notebook distinguishes the open-loop multi-day SARIMA forecast from a rolling one-step-ahead comparison. Use `outputs/rolling_one_step_metrics.csv` for a fair comparison of persistence, 7-day seasonal-naive, and SARIMA predictions. The LSTM remains optional.

The included 2025 CSV is reference material from Task 4 only; the Task 5 notebook downloads its own extended 2020-onward dataset when run. Outputs are regenerated during execution.
