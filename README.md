# ARPA-E PERFORM Datasets produce by NREL

## ARPA-E PERFORM

The ARPA-E PERFORM Program is an ARPA-E funded program that aim to use
time-coincident power and load seeks to develop innovative management systems
that represent the relative delivery risk of each asset and balance the
collective risk of all assets across the grid. A risk-driven paradigm allows
operators to: (i) fully understand the true likelihood of maintaining a
supply-demand balance and system reliability, (ii) optimally manage the system,
and (iii) assess the true value of essential reliability services. This
paradigm shift is critical for all power systems and is essential for grids
with high levels of stochastic resources. Projects will propose methods to
quantify and manage risk at the asset level and at the system level. Additional
descriptions about the ARPA-E PERFORM program can be found on the
[ARPA-E website](https://arpa-e.energy.gov/technologies/programs/perform).

In support of the ARPA-E PERFORM project, NREL has produced a set of
time-coincident load, wind, and solar generation profiles, including actual and
forecasting time series. Both actuals and forecasts are provided in form of
time-series with high temporal and spatial fidelity. Both deterministic and
probabilistic forecasts are contained in the dataset.

## Datasets

### Actuals

Actuals data are provided with a 5-min resolution for two years at the
site-level (only for solar and wind), zone-level, and system-level.

#### Solar

Actuals solar generation data are generated based on the National Solar
Radiation Database (NSRDB) at the site-level, the zone-level, and the
system-level, respectively. Solar power time series is simulated by the NREL's
System Advisor Model (SAM) with meteorological data and meta configuration at
the site-level. Then, zone-level and system-level actual time series are
obtained by aggregating site-level data accordingly.

#### Wind

Meteorological wind resource data is generated using the Weather Research and
Forecasting model (WRF). This data is then used to produce actuals wind
generation data using the methodology discussed above for solar actuals.

#### Load

Load data are collected from ISO's websites.

### Forecasts

Forecasting data are provided at three temporal scales with different
operational characterstics. Day-ahead forecasts are generated with a
11-hour-ahead lead time, a 48-hour horizon, an hourly resolution, and a daily
update rate. Intra-day forecasts are generated with a 6-hour-ahead lead time,
a 6-hour horizon, an hourly resolution, and a 6-hour update rate. Intra-hour
forecasts are generated with a 1-hour-ahead lead time, a 2-hour horizon, a
15-minute resolution, and a hourly update rate. Probabilistic forecasts are in
the form of 1-99 percentiles.

#### Solar and Wind

Day-ahead and intra-day forecasting relies on the European Centre for
Medium-Range Weather Forecasts(ECMWF) output that consists of deterministic
forecasts from 51 members. The Bayesian Model Averaging is used to generate
probabilistic forecasts on top of the deterministic forecasts from the 51 ECMWF
members. Intra-hour forecasting relies on the Machine Learning-based
Multi-Model (M3) and the historical synthetic actual data.

#### Load

Load forecasting at three time-scales are generated by the deep learning
ensemble. Recurrent neural network, convolutional neural network, and extreme
gradient boosting are used to generate deterministic forecasts, which are
converted to probabilistic forecasts by the adaptive Gaussian model.

## ISOs
- The Electric Reliability Council of Texas (ERCOT)

## Directory structure

The ARPA-E PERFORM data is made available as a series of .h5 files and can be
found at:
`s3://arpa-e-perform/`
- ERCOT/
  - MetaData/
    - solar_meta.xlxs
    - wind_meta.xlxs
    - load_meta.xlxs
  - 2018/
    - Solar/
      - Actuals/
        - Site_level/{Site}_solar_actuals_2018.h5
        - BA_level/{BA}_solar_actuals_2018.h5
        - Zone_level/{Zone}_solar_actuals_2018.h5
      - Forecasts
        - Day-ahead
          - Site_level/{Site}_solar_day-ahead_fcst_2018.h5
          - BA_level/{BA}_solar_day-ahead_fcst_2018.h5
          - Zone_level/{Zone}_solar_day-ahead_fcst_2018.h5
        - Intra-day
          - Site_level/{Site}_solar_intra-day_fcst_2018.h5
          - BA_level/{BA}_solar_intra-day_fcst_2018.h5
          - Zone_level/{Zone}_solar_intra-day_fcst_2018.h5
        - Intra-hour
          - Site_level/{Site}_solar_intra-hour_fcst_2018.h5
          - BA_level/{BA}_solar_intra-hour_fcst_2018.h5
          - Zone_level/{Zone}_solar_intra-hour_fcst_2018.h5
    - Wind/
      - Actuals/
        - Site_level/{Site}_wind_actuals_2018.h5
        - BA_level/{BA}_wind_actuals_2018.h5
        - Zone_level/{Zone}_wind_actuals_2018.h5
      - Forecasts
        - Day-ahead
          - Site_level/{Site}_wind_day-ahead_fcst_2018.h5
          - BA_level/{BA}_wind_day-ahead_fcst_2018.h5
          - Zone_level/{Zone}_wind_day-ahead_fcst_2018.h5
        - Intra-day
          - Site_level/{Site}_wind_intra-day_fcst_2018.h5
          - BA_level/{BA}_wind_intra-day_fcst_2018.h5
          - Zone_level/{Zone}_wind_intra-day_fcst_2018.h5
        - Intra-hour
          - Site_level/{Site}_wind_intra-hour_fcst_2018.h5
          - BA_level/{BA}_wind_intra-hour_fcst_2018.h5
          - Zone_level/{Zone}_wind_intra-hour_fcst_2018.h5
    - ECMWF/
      - Control/
        - Day-ahead/
        - Intra-day/
    - Load/
      - Actuals/
        - BA_level/{BA}_load_actuals_2018.h5
        - Zone_level/{Zone}_load_actuals_2018.h5
      - Forecasts
        - Day-ahead
          - BA_level/{BA}_load_day-ahead_fcst_2018.h5
          - Zone_level/{Zone}_load_day-ahead_fcst_2018.h5
        - Intra-day
          - BA_level/{BA}_load_intra-day_fcst_2018.h5
          - Zone_level/{Zone}_load_intra-day_fcst_2018.h5
        - Intra-hour
          - BA_level/{BA}_load_intra-hour_fcst_2018.h5
          - Zone_level/{Zone}_load_intra-hour_fcst_2018.h5
  - 2017/
    - Solar/
      - Actuals/
        - Site_level/{Site}_solar_actuals_2017.h5
        - BA_level/{BA}_solar_actuals_2017.h5
        - Zone_level/{Zone}_solar_actuals_2017.h5
    - Wind/
      - Actuals/
        - Site_level/{Site}_wind_actuals_2017.h5
        - BA_level/{BA}_wind_actuals_2017.h5
        - Zone_level/{Zone}_wind_actuals_2017.h5
    - ECMWF/
      - Control/
        - Day-ahead/
        - Intra-day/
    - Load/
      - Actuals/
        - BA_level/{BA}_load_actuals_2017.h5
        - Zone_level/{Zone}_load_actuals_2017.h5

## File Format

The data is provided in high density data file format HDF5 (.h5). The files
contain the following datasets with following shapes:

### Actuals
  - actuals (time-steps, sites)
  - meta (sites, )
  - time_index (time-steps, )

### Forecasts
  - forecasts (time-steps, 100 # percentiles)
  - meta (1,) # Forecasts are provided by size, zone, or BA
  - issue_time (time-steps, )
  - forecast_time (time-steps, )