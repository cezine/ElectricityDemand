# New York City Energy Demand

**Author**: Sejin Jang


## Overview 

This project analyzes  


## Business Problem

abc


### The Data

NYC Electricity Consumption Dataset: The dataset was found at the NYC Open Data website. The data was provided by New York City Housing Authority (NYCHA)It contains monthly consumption and cost data from 2010 January to 2021 Feburary by borough and development. It includes features such as utility vendor and meter information. 
* [NYC Electricity] (https://data.cityofnewyork.us/Housing-Development/Electric-Consumption-And-Cost-2010-April-2020-/jr24-e7cr)

NYC Weather Dataset: The dataset was gathered from the National Oceanic and Atmospheric Administration (NOAA), an American scientific and regulatory agency within the United States Department of Commerce. It includes various weather data such as temperature, wind and precipitation. https://www.ncdc.noaa.gov/cdo-web/datasets/GSOM/locations/CITY:US360019/detail

Data was gather from IMDB's public database available for download at IMDB which is an online database of information related to films, television programs, home videos, video games, and streaming content online.

* [IMDB](https://datasets.imdbws.com)


### Methods

This project uses descriptive analysis and visualizations including trends over time. It also provides Microsoft a useful overview of a genre's R.O.I. The Return On Investment metric was heavily utilized for this analysis and to ensure stakeholders are on the same page: the definition for R.O.I. is (Net Profit / Cost of Investment) x 100. In this analysis, Net Profit is Domestic, Foreign, Worldwide gross and Cost of Investment is Production Budget. The four questions explored are:

**1)** Which genres should we create films in? Which genres provide the highest average ROI?

**2)** Does the average ROI by genre follow a similar trend when compared between domestic and foreign markets?

**3)** Is there any relationship between directors' performance and movies' success?

**4)** Is there a correlation between a movie's production budget and their total profit?


### Results


**1)** The 5 genres with the greatest worldwide R.O.I. are Mystery, Animation, Musical, Sci-Fi, and Adventure. We have also forecasted the best, base, and worst case scenario for each top 5 genre. Musicals and Mysteries have negative % worst case scenarios. On base average level, each genre will return at least a 150% R.O.I. and the Mystery genre has the strongest best case scenario with a possible 613% R.O.I. Finally, a boxplot illustrates each genre's R.O.I.'s performance. 

![Q1_case_scenario](./Images/top_5_genre_roi_table.PNG)

![Q1_table](./Images/top_5_case_scenarios.PNG)

![Q1_boxplot](./Images/Q1_avg_worldwide_roi_for_the_top_5_genres.png)


**2)** Exploring the foreign R.O.I. vs. the domestic R.O.I. for each of the top 5 genres, Mystery is the only genre that on average performs on a similar wavelength for domestic and foreign markets. The foreign R.O.I. for the other genres is greater than the domestic R.O.I. to various degrees. The average domestic R.O.I. for Musical, Sci-Fi, and adventure is a negative % return.

![overall_table](./Images/overall_table.png)

![mystery_table](./Images/mystery_table.png)

![animation_table](./Images/animation_table.png)

![musical_table](./Images/musical_table.png)

![sci-fi_table](./Images/scifi_table.png)

![adventure_table](./Images/adventure_table.png)


**3)** There is no strong correlation between the number of movies that directors have been involved in or the specific directors themselves and profits. The director's who made 5 or more movies in our date range did not make the most profitable movies. However, they also did not lose money and made steady and modest profits. The most profitable movies were made by directors who produced 1 to 3 movies in that time. These movies did subtantially better than others, and therefore we could look deeper into them to find more insights.

![Q3_table](./Images/Q3_table.png)

**4)** In this section we analyzed whether or not there is a correlation between production budget and profit to decide if a studio should focus on producing fewer movies with higher production quality than to make more, lower budget films. Based on the appearance of a strong positive correlation between production budget and profit.

![production_profit_scatter](./Images/production_vs_profit.PNG)


## Conclusions


Our four recommendations to Microsoft's Movie Studio is to focus on:

**1)** From what we see in the graphs above and based on worst, base, and best case scenarios for each genre, we should create films in the **adventure and animation** genres. Although their best case ROI predictions are not as high as the mystery and musical genres, their worst case ROI predications are both far above 0%.

All movies, no matter the genre, should be released worldwide and not just domestically, the worst case ROI predictions for each of the top 5 genres with highest average domestic ROI is below -25%

**2)** The average ROI for the top 5 genres over the past decade shows that there is a bigger return on investment in the foreign market vs the domestic market for Adventure, Sci-Fi, Animation, and potentially Musical movies. The Mystery Genre's domestic and foreign ROI follow the same general positive trend over time.

Each genre's domestic ROI hovers around 0% except for Mystery movies that generally maintains a postive trajectory. There are a few outliers in the musical and mystery genre, but the foreign ROI generally performs better than the domestic ROI.

Based on this section of the analysis, Microsoft's movie studios should focus on producing **Adventure, Sci-Fi, and Animation** movies because of their greater foreign ROI potential

**NOTE ON MUSICAL GENRE**:
Initially, the musical genre seems to provide a substantial R.O.I. at first glance, but two caveats that should be named is that 1) There have been only 6 musical movies since 2010 and 2) The last musical movie was released back in 2017 which explains the continued upward trajetory it has which differs from the other genres.  

**3)** There is no strong correlation between director choice and a film's success. Directors who were involved in 5 or more films did not have a higher profits on average. On the other hand, after investigating the directors who made the highest average profit, we see that their movies are mostly Adventure. This confirms the results of the previous analysis on genres choice and a film's success.

More research will need to be done on the characteristics that impact successful films, but from our preliminary research it's clear that the genre choice and the film's reach have a direct impact on success and must be considered when deciding which type of movies we will create.

**4)** We recommend any studio looking to make large returns focus on producing fewer movies with higher production quality, taking a quality over quantity approach.


### Next Steps

Further analyses could yield additional insights for Microsoft's Movie Studios. Some questions to explore given the data available include:

 **-** Is there a correlation between a movie's ratings and their R.O.I.? Is there a difference in correlation when breaking down a movie's ratings by the movie's critic review vs. movie audience review?
 
 **-** What other metrics determine success aside from Profits and R.O.I. What affect does a movie's ratings or the number of times it has been viewed?
 
**-** We might not have had enough data to draw any correlation between director choice and a film's success. It may be interesting to gather more data and create a director profile dataset showing their performance. Perhaps, we could provide a suggested list of potential directors for Microsoft's new movie studio.

**-** What are other key metrics and characteristics of top grossing movies have a direct impact on profit and R.O.I.?

**-** What is the threshold for the dimishing rate of return on production budgets?


### Repository Structure

```
├── .ipynb_checkpoints
├── Data
├── Images
├── zippedData
├── README.md
├── final-data.csv
├── project.ipynb
└── slides.pdf
```

