# ESA-SciHub-2025-Forest-Interpolation
Testing different Interpolation Techniques for forest monitoring as part of ESA Space Challenge Hub 2025. Group work carried out with Mae Evans and Fran O'Leary.

Project website [here] (https://eodashboard.org/story/?id=scienceHub_timeSeries_vegetation)

## Background
Vegetation EO time series are crucial for monitoring ecosystem health, agricultural productivity and climate impacts.
NDVI (Normalised Difference Vegetation Index) time series often suffer from residual cloud presence, even after data pre-processing (see figure)
Depending on land cover type, NDVI time series reconstructions may perform differently due to varying periodicity, amplitude or steepness of transitions (Julien and Sobrino, 2019)
Accurate interpolation is essential to ensure reliable analysis of vegetation dynamics ! 

<img width="501" height="375" alt="image" src="https://github.com/user-attachments/assets/07ede58f-186b-4ce2-994f-853179b66e3c" />


## Use Case
We select 5 forest locations:
- Amazon: Moist tropical forest, Low seasonality, High precipitation, 123 billion tonnes of carbon (NOAA, 2021)
- Caatinga: Moist tropical forest; High Seasonality & precipitation; ~100,000 km2 and large flux of carbon, water, and other compounds with the atmosphere with seasons
- Elmstein: Temperate forest; High Seasonality & medium precipitation
- Muara: Moist tropical forest; High Seasonality & precipitation (monsoonal pattern)
- Rockies: Boreal forest. High seasonality, medium precipitation.

<img width="494" height="371" alt="image" src="https://github.com/user-attachments/assets/a16e7487-eef2-473d-9ea5-5b5b5bc0e971" />
<img width="352" height="255" alt="image" src="https://github.com/user-attachments/assets/835c04fb-2007-44f3-a2a8-3d8253c9dd76" />

## Methods
<img width="301" height="455" alt="Screenshot 2026-03-23 at 22 56 41" src="https://github.com/user-attachments/assets/7f29aa3a-5b74-4fd1-ad9a-38f11eceec42" />


Interpolation techniques tested: 
- Linear
- Cubic Spline: uses piecewise cubic polynomials to create smooth curve passing through a set of points. 
- Gaussian Process Regression: Bayesian ML method that models data as a smooth curve with uncertainty. Smooth trend, seasonality noise accounted for using kernels
-  Climatology Fill (seasonal): average info from similar time in past and previous years


## Results:
- short window →  better interpolation
- GPR processing time takes 2x as much
- Best interpolation technique for seasonal pattern: SHORT: linear, cubicSpline; LONG: Seasonal, GPR
- Best interpolation technique for non-seasonal: linear, or seasonal



