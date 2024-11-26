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

As mentioned in the article [A multi-hazard approach to assess severe weather-induced major power outage risks in the U.S](https://www.sciencedirect.com/science/article/pii/S0951832017307767), our data contains reporting errors and missing values due to:
- Inadequate reporting causing underreported incidents.
- Changes in regulatory requirements over time, may have caused underestimation of the actual number of incidents that happened during the period.
  
Once we narrowed down the variables for our analysis, made some adjustments to the variables:

- Combined `OUTAGE.START.DATE` and `OUTAGE.START.TIME` into a single variable named `OUTAGE.START' using `pd.to_datetime`.
- We actively decided to maintain missing variables as `NaN` or `NaT` until we complete our Missingness Analysis.
- We also removed extra spaces from categorical columns using `str.strip()`

It is important to note that the abstract of our dataset determines that "A major power outage in this dataset refers to "those that impacted atleast 50,000 customers or caused an unplanned firm load loss of atleast 300 MW."

We investigated the [source](https://www.oe.netl.doe.gov/oe417_annual_summary.aspx) of the power outage reports. Here we noticed that the data contained both NA and 0 for data that is unaccounted for. However, we do not want to assume that all 0 values in numerical variables are null yet given the description above for a major power outage, it seems unlikely that certain outages had 0 megawatt loss **and** 0 customers affected.

As such, we have replaced values of 0 in the `OUTAGE.DURATION` to `NaN` as well as and values of 0 in `DEMAND.LOSS.MW` and `CUSTOMERS.AFFECTED`.
<p></p>

###### Visual of our dataset
<iframe src="assets/images/outages_head.html" width="100%" height="200" frameBorder="0" ></iframe>
<p></p>

#### Univariate Analysis

<div style="display: flex; flex-direction: column; align-items: center; margin-bottom: 20px;">
    <h5 style="margin: 0 0 20px 0; text-align: center; color: darkblue;"> Total Outages per Year: </h5>
    <div style="display: flex; align-items: flex-start; width: 100%; margin-bottom: 20px;">
        <div style="flex: 1; margin-right: 10px;">
            <iframe src="assets/images/outages_by_year.html" style="width: 100%; height: 300px; border: none;"></iframe>
        </div>
        <div style="flex: 1; display: flex; flex-direction: column; align-items: flex-start; justify-content: flex-start;">
            <p style="margin: 0; text-align: justify;"> 

               
               Our first univariate analysis was the number of outages per year. Our interest was to decipher if there was a trend in the number of outages over the years recorded. This was a way to see if the worsening of the extreme climate conditions or the increase in electricity consumption had an impact on the number of outages. 
            </p>
        </div>
    </div>
</div>

<div style="display: flex; flex-direction: column; align-items: center; margin-bottom: 20px; margin-right: 10px">
    <h5 style="margin: 0 2px 20px 0; text-align: center; color: darkblue;">Total Outages per State:</h5>
    <div style="display: flex; align-items: flex-start; width: 100%; margin-bottom: 20px;">
        <div style="flex: 1; margin-right: 10px;">
            <iframe src="assets/images/outages_by_state.html" style="width: 105%; height: 350px; border: none; margin-right: 2px"></iframe>
        </div>
        <div style="flex: 1; display: flex; flex-direction: column; align-items: flex-start; justify-content: flex-start;">
            <p style="margin: 10px; text-align: justify;"> 
            
               
               Our second univariate analysis was the total number of power outages by state. In relation to our idea of increasing electricity demand and usage over time and population, we quantified these values. This is because over time, certain states have become more populated than others. We also wanted to see if certain states were more prone to power outages perhaps due to climate region, electricity usage, crime...etc.
            </p>
        </div>
    </div>
</div>

<div style="display: flex; flex-direction: column; align-items: center; margin-bottom: 20px; margin-right: 10px">
    <h5 style="margin: 0 2px 20px 0; text-align: center; color: darkblue;">Distribution of Power Outage Causes:</h5>
    <div style="display: flex; align-items: flex-start; width: 100%; margin-bottom: 20px;">
        <div style="flex: 1; margin-right: 10px;">
            <iframe src="assets/images/distribution_of_power_outage_cause.html" style="width: 105%; height: 350px; border: none; margin-right: 2px"></iframe>
        </div>
        <div style="flex: 1; display: flex; flex-direction: column; align-items: flex-start; justify-content: flex-start;">
            <p style="margin: 10px; text-align: justify;"> 
            
               
               Our last univariate analysis was to understand the distribution of causes for reported power outages from 2000 to 2016. From this pie chart we can observe that during this time the two most frequent causes of power outages were intentional attacks with a over a quarter of the power outages and extreme weather with almost half of the power outages resulting from it.
            </p>
        </div>
    </div>
</div>


#### Bivariate Analysis

<div style="display: flex; flex-direction: column; align-items: center; margin-bottom: 20px;">
    <h5 style="margin: 0 0 20px 0; text-align: center; color: darkblue; width: 100%;">
        Total Outages Per Climate Region:
    </h5>
    <div style="display: flex; align-items: flex-start; width: 100%; margin-bottom: 20px;">
        <div style="flex: 1; display: flex; flex-direction: column; justify-content: flex-start; margin-right: 10px;">
            <p style="margin: 0; text-align: justify;"> 
               
                Our first Bivariate analysis focused on creating a chart that reflected the number of outages per the 7 major climatic regions as defined by the National Center for Environmental Information. The idea to create this plot was to identify regions where more outages occurred and potentially direct our focus to identify the causes why some regions had more power outages than others.
            </p>
        </div>
        <div style="flex: 1; margin-left: 10px;">
            <iframe src="assets/images/outages_by_region_map.html" style="width: 110%; height: 300px; border: none;"></iframe>
        </div>
    </div>
</div>

<div style="display: flex; flex-direction: column; align-items: center; margin-bottom: 20px;">
    <h5 style="margin: 0 0 20px 0; text-align: center; color: darkblue; width: 100%;">
        Power Outages Per Climate Region and The Cause Distribution:
    </h5>
    <div style="display: flex; align-items: flex-start; width: 100%; margin-bottom: 20px;">
        <div style="flex: 1; display: flex; flex-direction: column; justify-content: flex-start; margin-right: 10px;">
            <p style="margin: 0; text-align: justify;"> 
               
               Our second Bivariate analysis focused on comparing the number of total power outages each region has experienced from January 2000 to July 2016 and what the causes were. As such we created a stacked bar plot where each climate region's bar was distributed in size by the number of outages resulting from a specific cause.
               </p>
                </div>
        <div style="flex: 1; margin-left: 10px;">
           <iframe src="assets/images/bivariate_stacked_barplot.html" style="width: 105%; height: 400px; border: none;"></iframe>
         </div>
    </div>
    
</div>
<div style="display: flex; flex-direction: column; align-items: center; margin-bottom: 20px;">
    <h5 style="margin: 0 0 20px 0; text-align: center; color: darkblue; width: 100%;">
        Number Power Outages Per State and The Cause:
    </h5>
    <div style="display: flex; align-items: flex-start; width: 100%; margin-bottom: 20px;">
        <div style="flex: 1; display: flex; flex-direction: column; justify-content: flex-start; margin-right: 10px;">
            <p style="margin: 0; text-align: justify;"> 
               
              Lastly, and similar to the graph above, we calculated the total number of power outages reported during this time by each state and the cause. As you might see, there is a notoriously large amount of the power outages throughout the different states caused by extreme weather. This could indicate a relationship between extreme weather and weather patterns with power outages. 
               </p>
                </div>
        <div style="flex: 1; margin-left: 10px;">
           <iframe src="assets/images/bivariate_stacked_barplot_by_state.html" style="width: 105%; height: 400px; border: none;"></iframe>
         </div>
    </div>
</div>



#### Interesting Aggregates
<h5 style="margin: 15px 0 10px 0; text-align: center; color: darkblue;"> Pivot Table #1: </h5>
  <iframe src="assets/images/pivot_table_outages_by_year_&_climate_region.html" width="100%" scrolling="yes" frameBorder="0" style="display: block; margin-left: auto; margin-right: auto;"> </iframe>

<h5 style="margin: 15px 0 10px 0; text-align: center; color: darkblue;"> Pivot Table #2: </h5>
  <iframe src="assets/images/pivot_table_outages.html" width="100%" scrolling="yes" frameBorder="0" style="display: block; margin-left: auto; margin-right: auto;"> </iframe>

<h5 style="margin: 15px 0 10px 0; text-align: center; color: darkblue;"> Pivot Table #3: </h5>
  <iframe src="assets/images/pivot_table_consumption_vs_outages_per_state.html" width="100%" scrolling="yes" frameBorder="0" style="display: block; margin-left: auto; margin-right: auto;"> </iframe>


------

### Assessment of Missingness

#### NMAR Analysis
One of the types of missing data that exists is NMAR which stands for **N**ot **M**issing **A**t **R**andom. This instance of missingness in data occurs when the values of the data itself is not disclosed. It depends only on the values themselves and not on other variables (columns). Because NMAR data is unobservable, it has to be analyzed by either collecting more data or reasoning about the data generating 
process. 

As mentioned above, regulatory requirements have fluctuated over the time period. One column that might be NMAR could be the `CAUSE.CATEGORY.DETAIL`. Resons for this include:
1. When the cause is due to something they might get public criticism entities in charge of the electricity might choose not to disclose the specific reason and hide under a mroe vague umbrella such as "system operability disruption".
2. Reporting agencies or electric companies who report the outage may use another affecting reason as the cause and cannot give proper details about the cause. i.e gridlines were old and vulnerable to weather and there was 'extreme weather' that day. 
3. Some categories do not have specific details to provide. i.e public appeals.
  
#### Missingness Dependencies

<h5 style="margin: 0 2px 20px 0; text-align: left; color: darkblue;"> Missingness Dependency of Outage Duration on Cause Category:</h5>
We carried out a permutation test with 1000 permutations using tvd as test statistic where we compared the distribution of `CAUSE.CATEGORY` when `OUTAGE.DURATION` was missing versus when it was not missing. 
- Observed TVD statistic: 0.405
- P-value: 0.0

<iframe src= "assets/images/NMAR_Cause_vs_Duration.html" width="700" height="400" frameBorder="0"></iframe>
<h5 style="margin: 0 2px 20px 0; text-align: left; color: darkblue;"> Missingness Dependency #2:</h5>


---

### Hypothesis Testing
**Null Hypothesis**: The number of power outages is uniformly distributed across all months of the year
**Alternative Hypothesis**: The number of outages is not uniformly distributed across all months of the year
**Test Statistic**: 
**Significance Level**: 

#### Justification: 


---
### Prediction Problem: Predicting the Cause Category

---

### Baseline Model


---

### Final Model
[Content for Final Model]

---

### Fairness Analysis
[Content for Fairness Analysis]

---
