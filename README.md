# Forecast Direct Normal Irradiance of Solar Energy using Deep Learning Model 

This project uses a deep learning model to forecast short-term and long-term Direct Normal Irradiance, which is crucial in solar energy. Nowadays, the adoption of solar energy into the power grid has increased, and it has become essential to accurate forecasts of direct normal irradiance from solar power for the effective operation and maintenance of power systems, ensuring their ability. Photovoltaic panels track the sun to receive more DNI. DNI accounts for a large portion of PV solar energy.

## Authors
- [Md Mehedi Hasan](https://github.com/mmh52)

## Project Overview

- **Dataset:** In this project, I use a dataset from Lowery Power Station, Denver, Colorado, covering the period from June 2008 to December 2013. This dataset contains Direct Normal irradiance, Globa Horizontal, and other features of Solar Energy. 

- **Preprocess Data:** This dataset contains minute data of direct normal irradiance and has some anomalies. I fixed those anomalies, filled in missing values, and converted it to an hourly dataset.

- **Key performance indicator:** I used RMSE (Root Mean Square Error) metrics to measure the performance of all models based on short-term and long-term forecasting of DNI.

- **Stakeholders:** Accurate DNI predictions help Operation and Maintenance (O&M) Service Providers optimize solar panel orientation for CSP systems and schedule maintenance during low DNI periods to minimize disruption. Forecasting DNI also aids grid operators in managing solar power integration, balancing supply and demand, maintaining grid stability, and reducing fossil fuel reliance. These predictions are also crucial for assessing the financial viability of solar projects, enabling investors to estimate returns and make informed funding decisions.

- **Models:** To forecast Direct Normal Irradiance, we used time series forecasting models and a deep learning model, Temporal Fusion Transformer.
  
     - **Base Models:** In this project, I used two base models: (i) Seasonal Naive and (ii) Seasonal Average. Seasonal naive prediction assumes the value of a 
       time series at a given period will be the same as the value from the corresponding period in the previous cycle, whereas the seasonal average  uses the average values 
       from the same season in previous years to make predictions.
   
     - **Tripple Exponential Smoothing:** The univariate exponential smoothing model uses the rolling average technique, in which the weights of previous time stamps 
       decrease exponentially. In this project, we used an additive version of triple exponential smoothing that can capture the seasonality of time series. 
     
     - **SARIMAX:**  SARIMAX extends SARIMA by including exogenous variables in the model. This model is suitable if other features of the time series data play an important 
       role in forecasting feature values. I pick the Zenith Angle as an exogenous variable to forecast direct normal irradiance in this project.

    - **Temporal Fusion Transformer:** The Temporal Fusion Transformer (TFT) is an attention-based, powerful, and flexible deep learning model designed for multi-horizon 
      time series forecasting. TFT is also known for its ability to provide accurate forecasts while offering interpretability. In this project, I combine TFT with a 
      hyperparameter tuning technique, Optuna, to optimize hyperparameter of TFT.


## Future Work 

- Incorporate weather and cloud cover data, which can be important features for forecasting direct normal irradiance.
- Develop a solar energy-based TFT Model that will give more attention to weather data.


## Sources
[1] Lowery Power Station Dataset: http://dx.doi.org/10.5439/1052550

[2] Hosseini, M.; Katragadda, S.; Wojtkiewicz, J.; Gottumukkala, R.; Maida, A.; Chambers, T.L. Direct Normal Irradiance Forecasting Using Multivariate Gated Recurrent Units. Energies 2020, 13, 3914. https://doi.org/10.3390/en13153914

[3] E. Cogliani. The role of the direct normal irradiance (DNI) forecasting in the operation of solar concentrating plants. https://doi.org/10.1016/j.egypro.2014.03.170

[4] Lim, Bryan, et al. "Temporal fusion transformers for interpretable multi-horizon time series forecasting." International Journal of Forecasting 37.4 (2021): 1748-1764.
