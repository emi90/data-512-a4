# DATA 512 Assignment A4
Emily Yamauchi


## Introduction

### Objective

During the last two years we all have been experiencing a global pandemic. This has been tragic and disruptive to many countries and has taken a deep personal toll on many individuals and their families. 
One aspect that has been hard to miss in the last two years is the datafication of the pandemic. That is, many aspects of the individual toll of the pandemic have been collected, aggregated and re-represented as data. 
This datafication gives us the privilege to examine the pandemic from potentially many different perspectives to understand how it has changed lives and how it has changed society.   

This analysis is focusing specifically on data from Montgomery County, MD.  
We would like to answer:  
- How did masking policies change the progression of confirmed COVID-19 cases from February 1, 2020 through October 15, 2021?

### Data Source

Data is collected from three separate sources:   
- The `RAW_us_confirmed_cases.csv` file from the Kaggle repository of [John Hopkins University COVID-19 data](https://www.kaggle.com/antgoldbloom/covid19-data-from-john-hopkins-university?select=RAW_us_confirmed_cases.csv).
- The CDC dataset of [masking mandates by county](https://data.cdc.gov/Policy-Surveillance/U-S-State-and-Territorial-Public-Mask-Mandates-Fro/62d6-pm5i).
- The New York Times [mask compliance survey data](https://github.com/nytimes/covid-19-data/tree/master/mask-use).  

The majority of this data is by US County by Day. 
The mask compliance is a single shot estimator that gives you a compliance estimate for every County in the US.  

The three data sources are filtered to data which pertains to only Montgomery County, MD.

Additionally, we were given population and county area data seperately.  

### Data Processing

The `cases` dataset and `mask_mandate` dataset are merged on date column.  
Daily cases are calculated by taking the difference between total cases for each day.  
The 7-day and 14-day rolling average of daily cases are also calculated and captured.  

Mask compliance rate was recalculated as magnitude in terms of population, but this dataset was not used in this part of the analysis.  


### Folder Structure

```
 data-512-a4
    ├── LICENSE
    ├── README.md
    ├── data_raw
    │   ├── country.zip
    │   └── RAW_us_confirmed_cases.csv.zip
    ├── data_clean
    │   ├── no_scores.csv
    │   ├── politicians.csv
    │   ├── populations.csv
    │   ├── subregions.csv
    │   ├── wp_wpds_countries_no_match.csv
    │   └── wp_wpds_politicians_by_country.csv
    └── data-512-a2.ipynb
```