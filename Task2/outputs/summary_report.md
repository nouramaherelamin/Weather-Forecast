# Weather Time-Series EDA Summary

**Region:** Banha, Qalyubia, Egypt (approx. 30.46°N, 31.18°E)  
**Period:** 2025-01-01 to 2025-12-31; 365 daily rows.  
**Source:** NASA POWER Daily Point API; temperature in °C, precipitation in mm/day.

## Main patterns
Monthly mean temperature ranged from about 13.5 °C (February) to 31.4 °C (July), while daily means ranged from 10.1 to 34.5 °C. There were 102 days with precipitation above 0 mm and 43 wet days above 0.1 mm. Maximum daily precipitation was 4.49 mm on 07 September. The contemporaneous temperature–precipitation correlation was -0.02, indicating little linear association at lag 0. Review the cumulative-rainfall plot and lagged correlations for event timing.

## Stationarity
ADF p-value: 0.7624; first-difference ADF p-value: 0.0000. The ADF test does not reject the unit-root null at the 5% level; non-stationarity remains plausible. Differencing may help; confirm the transformed series with both ADF and KPSS before modeling. A single year provides limited evidence for a robust annual seasonal component.

## Data quality and methods
The notebook checks gaps, duplicates, missing values, suspicious ranges, global IQR flags and 30-day rolling z-score outliers. Missing values are reported rather than silently dropped; short internal gaps are interpolated only in a separate analysis copy. STL and classical decomposition are included as exploratory diagnostics.

## Reproducibility and limitations
Endpoint: `https://power.larc.nasa.gov/api/temporal/daily/point`; parameters: `T2M,T2M_MAX,T2M_MIN,PRECTOTCORR,RH2M,WS2M`; dates: `20250101`–`20251231`; community: `RE`; format: JSON. No rate-limit response was observed during the single request (this does not imply that no rate limits exist). NASA POWER is gridded/reanalysis-based rather than a station observation at the exact point; rainfall estimates can be uncertain in dry regions. An optional Open-Meteo comparison is provided as cross-source context, not ground truth.