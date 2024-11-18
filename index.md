---
layout: default
title: "Powering Through"
subtitle: "Analyzing Trends in Major US Power Outages"
---

# Introduction

Power outages have become increasingly frequent in the United States due to the stress of extreme weather, aging infrastructure, and increasing energy demand. The United States, according to [CITATION], has the highest number of power outages among developed nations; it is a problem estimated to cost billions annually across the entire nation. Each US citizen is estimated to experience 92 minutes of power outage per year on average.  That is why it is crucial to understand how the characteristics of power outages in the United States have shifted over time and what the main catalysts are.

This study investigates the trends in power outages across the nation, identifies the primary drivers for these events and hopes to provide relevant information that may assist communities and their policy makers in reducing the frequency and impact of this phenomena. The focus of our analysis will be answering the following questions: 

**How have characteristics of major power outages changed over time?**
**Is there a clear trend in the characteristics of power outages?**

The data we have used comes from the scientific dataset “Data on major power outage events in the continental U.S” and contains the major power outage data in the continental U.S. from January 2000 to July 2016. With this data, we will employ data analysis techniques to determine patterns in power outages, draw conclusions from that analysis, and create a predictive model of what the cause of a major power outage in the United States might be.  


**Project Map:** [Insert your project map here, e.g., flowchart of analysis process]

-------

### Column Descriptions

| COLUMN                      |    DESCRIPTION                                                       |
|-----------------------------|-----------------------------------------------------------------------------|
| `YEAR`                     | Year an outage occurred                                                     |
| `MONTH`                    | Month an outage occurred                                                    |
| `U.S._STATE`               | State the outage occurred in                                                |
| `NERC.REGION`              | North American Electric Reliability Corporation (NERC) regions involved     |
| `CLIMATE.REGION`           | U.S. Climate regions as specified by National Centers for Environmental Information (9 Regions) |
| `ANOMALY.LEVEL`            | Oceanic El Niño/La Niña (ONI) index referring to cold and warm episodes    |
| `OUTAGE.START.DATE`        | Day of the year when the outage event started                               |
| `OUTAGE.START.TIME`        | Time of the day when the outage event started                               |
| `OUTAGE.RESTORATION.DATE`  | Day of the year when power was restored                                     |
| `OUTAGE.RESTORATION.TIME`  | Time of the day when power was restored                                     |
| `CAUSE.CATEGORY`           | Categories of all events causing major power outages                        |
| `OUTAGE.DURATION`          | Duration of outage events (in minutes)                                      |
| `DEMAND.LOSS.MW`           | Amount of peak demand lost during an outage event (in Megawatt)             |
| `CUSTOMERS.AFFECTED`       | Number of customers affected by the outage                                  |
| `TOTAL.PRICE`              | Average monthly electricity price in the U.S. state (cents/kilowatt-hour)  |
| `TOTAL.SALES`              | Total electricity consumption in the U.S. state (megawatt-hour)             |
| `TOTAL.CUSTOMERS`          | Annual number of total customers served in the U.S. state                   |
| `POPPCT_URBAN`             | Percentage of the total population of the U.S. state represented by urban areas (in %) |
| `POPDEN_URBAN`             | Population density of urban areas (persons per square mile)                 |
| `AREAPCT_URBAN`            | Percentage of the land area of the U.S. state represented by urban areas (in %) |

---

### Data Cleaning and Exploratory Analysis

#### Data Cleaning
[Description of your data cleaning process]

#### Univariate Analysis
[Analysis of individual variables]

#### Bivariate Analysis
[Analysis of relationships between variables]

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

