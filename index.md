---
layout: default
title: "Powering Through"
subtitle: "Analyzing Trends in Major US Power Outages from 2004 to 2016"
---

## Introduction

This project aims to analyze major power outages in the United States, exploring trends, causes, and their impact across different regions. We will also investigate potential patterns in outage durations, affected populations, and more. The analysis will be based on data covering several years of reported power failures.

By focusing on various factors such as climate anomalies, geographic regions, and cause categories, we aim to uncover key insights into the challenges posed by power outages in different parts of the country. The findings may help in improving preparedness and response strategies for such events.

The project map below illustrates the different stages and data points we will analyze throughout this study.

**Project Map:** [Insert your project map here, e.g., flowchart of analysis process]

---

### Column Descriptions

| Column                      | Description                                                                 |
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

---

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

### Footer

&copy; 2024 Powering Through: All Rights Reserved
