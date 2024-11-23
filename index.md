---
layout: default
title: "Powering Through"
subtitle: "Analyzing Trends in Major US Power Outages"
---

## Introduction

Power outages have become increasingly frequent in the United States due to the stress of extreme weather, aging infrastructure, and increasing energy demand. The United States, according to the [University of Buffalo's Department of Industrial and Systems Engineering](https://www.popsci.com/story/environment/why-us-lose-power-storms/), has the highest number of power outages among developed nations; it is a problem estimated to cost billions annually across the entire nation. Each US citizen is estimated to experience 2 hours of power outage per year on average.  That is why it is crucial to understand how the characteristics of power outages in the United States have shifted over time and what the main catalysts are.

This study investigates the trends in power outages across the nation, identifies the primary drivers for these events and hopes to provide relevant information that may assist communities and their policy makers in reducing the frequency and impact of this phenomena. The focus of our analysis will be answering the following questions: 


<p style="text-align:center;"><b>Where and when do major outages tend to occur?</b></p>
<p></p>

<p style="text-align:center;"><b>Predict the cause of a major power outage?</b></p>
<p></p>


The data we have used comes from the scientific dataset [Data on major power outage events in the continental U.S](https://www.sciencedirect.com/science/article/pii/S2352340918307182?ref=pdf_download&fr=RR-2&rr=8e45b02bd9d82a8f) and contains the major power outage data in the continental U.S. from January 2000 to July 2016. With this data, we will employ data analysis techniques to determine patterns in power outages, draw conclusions from that analysis, and create a predictive model of what the cause of a major power outage in the United States might be.  


**Project Map:** [Insert your project map here, e.g., flowchart of analysis process]

-------

### Relevant Column Descriptions
The original dataset contained 1534 observations and 55 variables (columns).
For our analysis we will be using a modified version of the dataframe composed of 1534 columns and 18 variables. 
Below is a table with the variables we maintained and a description of what they describe.

| COLUMN                      |    DESCRIPTION                                                              |
|-----------------------------|-----------------------------------------------------------------------------|
| `YEAR`                      | Year the outage occurred                                                    |
| `MONTH`                     | Month the outage occurred                                                   |
| `U.S._STATE`                | State where the outage occurred                                             |
| `POSTAL.CODE`               | State's Postal Code                                                         |
| `CLIMATE.REGION`            | U.S. Climate regions as specified by National Centers for Environmental Information (9 Regions) |
| `ANOMALY.LEVEL`             | Oceanic El Niño/La Niña (ONI) index referring to cold/warm episodes (estimated as a 3-month running mean) |
| `CLIMATE.CATEGORY`          | Represents the climate episodes corresponding to the year                   |
| `OUTAGE.START.DATE`         | Day of the year when the outage event started                               |
| `CAUSE.CATEGORY`            | Categories of all events causing major power outages                        |
| `CAUSE.CATEGORY.DETAIL`     | Detailed description of the event categories causing the power outages      |
| `OUTAGE.DURATION`           | Duration of outage events (in minutes)                                      |
| `DEMAND.LOSS.MW`            | Amount of peak demand lost during an outage event (in Megawatt)             |
| `CUSTOMERS.AFFECTED`        | Number of customers affected by the power outage event                      |
| `RES.SALES`                 | Electricity consumption in the residential sector (megawatt-hour)           |
| `COM.SALES`                 | Electricity consumption in the commercial sector (megawatt-hour)            |
| `IND.SALES`                 | Electricity consumption in the industrial sector (megawatt-hour)            |
| `TOTAL.SALES`               | Total electricity consumption in the U.S. state (megawatt-hour)             |
| `POPULATION`                | Population in the U.S. state in a year                                      |

---

### Data Cleaning and Exploratory Analysis

#### Data Cleaning
Our first step in data cleaning was to discern which columns in the dataset are necessary for the analysis. For example, we removed all the columns regarding regional economic outputs, electricity prices and land area such as; `PC.REALGSP.STATE`, `PC.REALGSP.USA`, `AREAPCT_URBAN`, `AREAPCT_UC.` Moreover, we removed certain colums about the percentage of electricity consumption because we want to use the absolute electricity usage. Another section of columns we found less relevant to our analysis were the customer served variables. However, we kept the states' population to understand how the changes in absolute electricity consumption relate to the population. You can scroll through the image below and look at what out dataset looks like.

Once we narrowed down the variables for our analysis, made some adjustments to the variables:

- Combined `OUTAGE.START.DATE` and `OUTAGE.START.TIME` into a single variable named `OUTAGE.START' using `pd.to_datetime`.
- We actively decided to maintain missing variables as `NaN` or `NaT` until we complete our Missingness Analysis. 
   
<iframe src="assets/images/outages_head.html" width="100%" height="200"></iframe>
<p></p>

#### Univariate Analysis
##### Outages per Year:
<div style="display: flex; align-items: center; width: 100%;">
    <iframe src="assets/images/outages_by_year.html" width="60%" height="300" style="margin-right: 10px;"></iframe>
    <p style="width: 50%; margin: 0;"> Our first univariate analysis was the number of outages per year. Our interest was to decipher if there was a trend in the number of outages over the years recorded. This was a way to see if the worsening of the extreme climate conditions or the increase in electricity consumption had an impact on the number of outages. </p>
</div>

##### Total Customer Affected per Year: 
<div style="display: flex; align-items: center; width: 100%;">
    <iframe src="assets/images/outages_by_state.html" width="70%" height="400" style="margin-right: 10px;"></iframe>
    <p style="width: 50%; margin: 0;"> Our second univariate analysis was the total number of customers affected by outages per year. In relation to our idea of increasing electricity demand and usage over time and population. We quantified these values.  </p>
</div>

#### Bivariate Analysis
##### Total Outages Per Climate Region: 

Our first Bivariate analysis focused on creating a chart that reflected the number of outages per the 7 major climatic regions as defined by the National Center for Environmental Information. The idea to create this plot was to identify regions where more outages occurred and potentially directing our focus to identify the causes why some regions had more power outages than the others. 

  <iframe src="assets/images/outages_by_region_map.html" width="600" height="400" scrolling="yes"> </iframe>


##### Power Outages Per Climate Region and The Cause Distribution:
Our second Bivariate analysis focused on comparing the number of total power outages each region has experienced from January 2000 to July 2016 and what the causes were. As such we created a stacked bar plot where each climate region's bar was distributed in size by the number of outages resulting from a specific cause.

  <iframe src="assets/images/bivariate_stacked_barplot.html" width="600" height="400" scrolling="yes"> </iframe>

#### Interesting Aggregates
##### Pivot Table #1
  <iframe src="assets/images/pivot_table_outages_by_year_&_climate_region.html" width="100%" scrolling="yes"> </iframe>

##### Pivot Table #2
  <iframe src="assets/images/pivot_table_outages.html" scrolling="yes"> </iframe>

##### Pivot Table #3
  <iframe src="assets/images/pivot_table_consumption_vs_outages_per_state.html" width="100%" scrolling="yes"> </iframe>



------

### Assessment of Missingness

#### NMAR Analysis
[Content for NMAR Analysis]

#### Missingness Dependencies
[Content for Missingness Dependencies]

---

### Hypothesis Testing
[Content for Hypothesis Testing]

---

### Final Model
[Content for Final Model]

---

### Fairness Analysis
[Content for Fairness Analysis]

---

