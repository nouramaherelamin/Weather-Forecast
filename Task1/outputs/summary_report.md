# Weather Time-Series EDA Summary

**Area/period/source:** Banha, Qalyubia, Egypt (30.46°N, 31.18°E), 2025-01-01 to 2025-12-31 (365 daily records). NASA POWER Daily Point API was chosen because it is free, requires no API key, and provides long historical coverage. Temperature is in °C and precipitation in mm/day.

**Patterns:** Monthly mean temperature ranged from 13.5 °C (February) to 31.4 °C (July); daily means ranged from 10.1 to 34.5 °C. Rain occurred on 102 days; 43 days exceeded 0.1 mm. The maximum was 4.49 mm on 07 September. Lag-0 temperature–rainfall correlation was -0.02.

**Stationarity:** The original series is non-stationary (ADF p=0.762; KPSS p=0.01). After first differencing, ADF p=1.43e-14 and KPSS p=0.0503; differencing reduces the evidence of non-stationarity, though KPSS is borderline. One year is insufficient to establish a robust annual seasonal component.

**Quality/limitations:** Checks cover missing dates/values, duplicates, fill value -999, suspicious ranges, global IQR and 30-day rolling z-score outliers. Missingness is reported; limited interpolation is confined to a separate analysis copy. NASA POWER is gridded/reanalysis-based, not a direct station measurement, and rainfall estimates may be uncertain in dry regions.