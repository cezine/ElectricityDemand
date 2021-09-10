# New York City Energy Demand

**Author**: Sejin Jang


## Overview 

According to the UN climate report this year, some of the global warming effects are now irreversible. The effects of this are detrimental, as the sea levels continue to rise, due to the melting of ice in the arctic, areas located below the sea level are at high risk. Furthermore, as the temperature increases, this also results in extreme weather events such as hurricanes, wildfires, and drought. To mitigate global warming, some have already resorted to using clean and renewable energy sources. This can be seen as more communities are trying to replace their traditional energy sources that rely on fossil fuels, with clean energy such as solar and wind. Hence, it is crucial to estimate the future energy demand so that a more clear and realistic goal can be set for the communities.

In this project, I will build a predictive model that estimates the future electricity consumption in New York City based on its weather data. Energy usage is correlated with the temperatures. People are more likely to use more air conditioning in hot weather and more heaters during cold periods. The project aims to help decision makers from all sectors understand the magnitude of the global warming effect and to aid in better preparation as we attempt to meet the future energy demand while adopting more clean and renewable energy.


### Data

NYC Electricity Consumption Dataset: The dataset was found at the NYC Open Data website. The data was provided by New York City Housing Authority (NYCHA). It contains monthly electricity consumption and cost data from 2010 January to 2021 February by borough and development. It includes features such as electricity consumption, utility vendor and meter information. The electricity consumption data was provided in kilowatt (kW) as well as in kilowatt-hours (kWh). The difference between kWh and kW is that kW reflects the rate of electricity you use, and kWh indicates the amount of electricity you use. For this project, kWh will be taken into account. https://data.cityofnewyork.us/Housing-Development/Electric-Consumption-And-Cost-2010-April-2020-/jr24-e7cr

NYC Weather Dataset: The dataset was gathered from the National Oceanic and Atmospheric Administration (NOAA), an American scientific and regulatory agency within the United States Department of Commerce. It contains monthly mean maximum, mean minimum and mean temperatures; monthly total precipitation and snowfall; departure from normal of the mean temperature and total precipitation; monthly heating and cooling degree days; number of days that temperatures and precipitation are above or below certain thresholds; extreme daily temperature and precipitation amounts; number of days with fog; and number of days with thunderstorms. https://www.ncdc.noaa.gov/cdo-web/datasets/GSOM/locations/CITY:US360019/detail


### Methods

NYC Electricity Consumption dataset contains 362,630 records. Each record represents a building and a month. It has data from 195 buildings in Manhattan, 69 buildings in the Bronx, 262 buildings in Brooklyn, 93 buildings in Queens and 10 buildings in Staten Island. This is obviously not all the data in New York City as the number of buildings in the dataset is small. When resampling time series datasets, summing the consumption data for each month would be misleading due to the insufficient data. It makes more sense to use mean value for each month. Therefore, I grouped data by borough and resampled by monthly mean value. This means that the resampled figure represents average building electricity consumption in each borough.

borough image

Staten Island's average building electricity consumption appears much higher than the rest of New York City. As the dataset includes only 10 buildings in Staten Islands, this issue requires further investigation. The dataset also includes rather small number of buildings in Queens and the Bronx. Thus, I decided to focus on Manhattan as a sample for this project. 

boxplot image

The graph above is showing a building’s electricity consumption in Manhattan on average. Except for 2010, which seems rather higher than the other years, and 2011 and 2018 with incomplete and missing data, the Median electricity usage in a year ranges from around 30,000 to 37,000 kilowatt-hours.

In order to obatin the missing data, I have reached out to New York City Housing Authority who provides the data. Until I hear from them, I have made 4 datasets: 2 versions of train set, 1 validation set and 1 test set. The first version of the train set is the seamless data from 2012 to 2017 (6 years). Within this seamless data, I used the first 5 years as the second version of the train set and the next 1 year as a validation set. I also kept data from 2019 as a test set. The reason I seperate the dataset in this way is to compare the results and see if seamlessness and more training data have any effect on model performance.

train val test image

To match the location, I took Central Park’s weather data. I used different types of temperature data. Extreme minimum and maximum temperatures represent the highest daily maximum temperature and the lowest daily minimum temperature for the month. Maximum and minimum temperatures represent average of daily maximum and minimum temperatures. Average temperature is the mean of the maximum and minimum temperatures. 

After merging the two datasets, I can see that weather as well as the electricity consumption have seasonality. The highest consumption is observed in the Summer. The next highest consumption is observed in the Winter. And this is the assumption I used for this project. 

seasonality image

Now, to predict the electricity consumption in any given month, I used models such as Vector Autocorrelation(VAR), Vector Autoregression Moving-Average with Exogenous Regressors(VARMAX) as well as Long Short Term Memory (LSTM) Neural Network. The basis behind this is that the electricity consumption a month ago can definitely affect this month’s consumption. In addition, the last month’s temperature can also influence this month’s electricity consumption. This means that you can predict the future consumption with past values of itself along with past values of temperature. 

The key for VAR and VARMAX modeling is that you have to find the optimal order(lag) value. To find this, you can use an attribute like ".select_order()".

lag value image

After fitting the model with the optimal order, I get the equations for all time series variables. In this case, I only care about the consumption time series so I focus on the equation for the consumption as seen in the image below. The way I interpret this is that first, I observe what variable is most influetial in prediction by looking at p-value. I consider those under 0.05 is the influential variables, so in this case, a, b, c are contributing in predicting consumption the most. My equation is made up of coefficients of all the t

equation image



### Results


**1)** 


images

**2)** 

images


**3)** 

images


**4)** 

images


## Conclusions







### Next Steps




### Repository Structure

```
├── .ipynb_checkpoints
├── Data
├── Images
├── README.md
├── project.ipynb
└── slides.pdf
```

