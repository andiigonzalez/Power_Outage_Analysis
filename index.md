---
layout: default
title: "Powering Through"
subtitle: "Analyzing Trends in Major US Power Outages"
---

## Introduction

Power outages have become increasingly frequent in the United States due to the stress of extreme weather, aging infrastructure, and increasing energy demand. The United States, according to [CITATION], has the highest number of power outages among developed nations; it is a problem estimated to cost billions annually across the entire nation. Each US citizen is estimated to experience 92 minutes of power outage per year on average.  That is why it is crucial to understand how the characteristics of power outages in the United States have shifted over time and what the main catalysts are.

This study investigates the trends in power outages across the nation, identifies the primary drivers for these events and hopes to provide relevant information that may assist communities and their policy makers in reducing the frequency and impact of this phenomena. The focus of our analysis will be answering the following questions: 

<p style="text-align:center;">**How have characteristics of major power outages changed over time?**</p>

<p style="text-align:center;">**Is there a clear trend in the characteristics of power outages?**</p>

The data we have used comes from the scientific dataset “Data on major power outage events in the continental U.S” and contains the major power outage data in the continental U.S. from January 2000 to July 2016. With this data, we will employ data analysis techniques to determine patterns in power outages, draw conclusions from that analysis, and create a predictive model of what the cause of a major power outage in the United States might be.  


**Project Map:** [Insert your project map here, e.g., flowchart of analysis process]

-------

### Relevant Column Descriptions
Below is a description of the columns that we maintained in our dataset as they were relevant to our analysis.

| COLUMN                      |    DESCRIPTION                                                              |
|-----------------------------|-----------------------------------------------------------------------------|
| `YEAR`                      | Year an outage occurred                                                     |
| `MONTH`                     | Month an outage occurred                                                    |
| `U.S._STATE`                | State the outage occurred in                                                |
| `POSTAL.CODE`               | State's Postal Code                                                         |
| `CLIMATE.REGION`            | U.S. Climate regions as specified by National Centers for Environmental Information (9 Regions) |
| `ANOMALY.LEVEL`             | Oceanic El Niño/La Niña (ONI) index referring to cold/warm episodes (estimated as a 3-month running mean) |
| `CLIMATE.CATEGORY`          | Represents the climate episodes corresponding to the year                   |
| `OUTAGE.START.DATE`         | Day of the year when the outage event started                               |
| `OUTAGE.START.TIME`         | Time of the day when the outage event started                               |
| `CAUSE.CATEGORY`            | Categories of all events causing major power outages                        |
| `CAUSE.CATEGORY.DETAIL`     | Detailed description of the event categories causing the power outages      |
| `OUTAGE.DURATION`           | Duration of outage events (in minutes)                                      |
| `DEMAND.LOSS.MW`            | Amount of peak demand lost during an outage event (in Megawatt)             |
| `CUSTOMERS.AFFECTED`        | Number of customers affected by the power outage event                      |
| `RES.SALES`                 | Electricity consumption in the residential sector (megawatt-hour)           |
| `COM.SALES`                 | Electricity consumption in the commercial sector (megawatt-hour)            |
| `IND.SALES  `               | Electricity consumption in the industrial sector (megawatt-hour)            |
| `TOTAL.SALES`               | Total electricity consumption in the U.S. state (megawatt-hour)             |
| `POPULATION`                | Population in the U.S. state in a year                                      |

---

### Data Cleaning and Exploratory Analysis

#### Data Cleaning
Our first step was to discern which columns in the dataset are necessary for the analysis. For example, we removed all the columns regarding regional economic outputs, electricity prices and land area such as; `PC.REALGSP.STATE`, `PC.REALGSP.USA`, `AREAPCT_URBAN`, `AREAPCT_UC.` Moreover, we removed certain colums about the percentage of electricity consumption because we want to use the absolute electricity usage. Another section of columns we found less relevant to our analysis were the customer served variables. However, we kept the states' population to understand how the changes in absolute electricity consumption relate to the population. 

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

