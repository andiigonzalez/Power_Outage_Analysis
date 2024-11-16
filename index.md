---
layout: default
title: "Powering Through"
subtitle: "Analyzing Trends in Major US Power Outages from 2004 to 2016"
---

<style>
  /* Global Styles */
  body {
    font-family: Arial, sans-serif;
    margin: 0;
    padding: 0;
    background-color: #f4f4f4;
  }
  .site-header {
    display: none;
  }
  h1, h2, h3, h4, h5, h6 {
  color: black !important;   /* Ensure all headers are black */
  font-weight: bold;         /* Make headers bold */
  }

  /* Specific font sizes for each header */
  h1 {
    font-size: 2.5em !important; /* Larger size for h1 */
  }
  
  h2 {
    font-size: 2.2em !important; /* Slightly larger size for h2 */
  }
  
  h3 {
    font-size: 2em !important;   /* Larger size for h3 */
  }

  /* Custom Banner Styles */
  .custom-banner {
    background-image: url("https://andiigonzalez.github.io/Power_Outage_Analysis/assets/images/header_image.jpeg");
    background-size: cover;
    background-position: center;
    height: 400px;
    text-align: center;
    color: white;
    padding-top: 120px;
    margin-bottom: 0;
    position: relative;
  }

  .custom-banner h1 {
    font-size: 5em !important;
    text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.7);
    font-weight: bold;
    color: white !important;
    margin: 0;
  }

  /* Hide the default title */
  .page-title {
    display: none;
  }
  

  /* Navigation Bar Styles */
  nav {
    overflow: hidden;
  }

  nav a {
    float: left;
    display: block;
    color: white;
    text-align: center;
    padding: 14px 20px;
    text-decoration: none;
    transition: color 0.3s ease;
  }

  nav a:hover {
    color: #ff6347;
  }

  /* Centered Content Styles */
  .content {
    padding: 20px;
    text-align: center;
  }

  /* Table Styling */
  table {
    width: 70%;
    margin: 20px auto;
    border-collapse: collapse;
    background-color: white;
  }

  table, th, td {
    border: 1px solid black;
  }
  tr {
  border-bottom: 1px solid #ddd;  /* Light grey border between rows */
  }

  th, td {
    font-family: serif;
    font-weight: normal;
    padding: 8px;
    text-align: center;
  }

  th {
    background-color: #f4f4f4;
    color: #333;
  }

  td {
    color: #555;
  }

  td.description {
    white-space: nowrap;
    overflow: hidden;
    text-overflow: ellipsis;
    max-width: 300px;
  }

  /* Code Block Styling */
  th code, code {
    font-family: 'Roboto Mono', monospace;
    background-color: #E6FFE3;
    color: #333;
    padding: 2px 4px;
    border-radius: 3px;
  }

  /* Footer Styles */
  footer {
    background-color: #333;
    color: white;
    text-align: center;
    padding: 10px 0;
    position: fixed;
    width: 100%;
    bottom: 0;
  }
</style>

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
