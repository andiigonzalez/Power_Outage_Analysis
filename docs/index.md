---
layout: default
title: "Powering Through: Analyzing Trends in Major US Power Outages"
---
<!DOCTYPE html>
<html lang="en">

<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>{{ site.title }} - {{ site.description }}</title>

  <!-- Link to Google Fonts for Roboto Mono Medium -->
  <link href="https://fonts.googleapis.com/css2?family=Roboto+Mono:wght@500&display=swap" rel="stylesheet">

  <!-- Basic Styles for the Page Layout and Navigation -->
  <style>
    body {
      font-family: Arial, sans-serif;
      margin: 0;
      padding: 0;
      background-color: #f4f4f4;
    }

    /* Custom CSS for the Banner Image */
    .custom-banner {
      background-image: url("../assets/images/header_image.jpeg");
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
      font-size: 4em;
      text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.7);
      font-weight: bold;
      margin: 0;
    }

    /* Hide any default title rendered by the layout */
    .page-title {
      display: none;
    }

    /* Make all headers under the banner black */
    .content-section h1,
    .content-section h2,
    .content-section h3,
    .content-section h4,
    .content-section h5,
    .content-section h6 {
      color: black !important;
    }

    /* Navigation Bar Styling */
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

    /* Center Content on the Page */
    .content {
      padding: 20px;
      text-align: center;
    }

    /* Table Styling */
    table {
      width: 80%;
      margin: 20px auto;
      border-collapse: collapse;
      background-color: white;
    }

    th,
    td {
      font-family: serif;
      font-weight: normal;
      padding: 10px;
      text-align: center;
      border: 1px solid #ddd;
    }

    th {
      background-color: #f4f4f4;
      color: #333;
    }

    td {
      color: #555;
    }

    /* Code Block Styling for the first column header */
    th code {
      font-family: 'Roboto Mono', monospace;
      font-weight: 500;
      background-color: rgba(144, 238, 144, 0.7);
      color: #333;
      padding: 2px 4px;
      border-radius: 3px;
    }

    /* Code Block Styling */
    code {
      font-family: 'Roboto Mono', monospace;
      background-color: #f9f9f9;
      padding: 2px 4px;
      border-radius: 3px;
    }

    /* Footer Styling */
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
</head>

<body>
  <div class="custom-banner">
    <h1>{{ site.title }}: {{ site.description }}</h1>
  </div>
  
<nav>
  <!-- Dynamically generated navigation from site.navigation -->
  {% for item in site.navigation %}
    <a href="{{ item.link }}">{{ item.text }}</a>
  {% endfor %}
</nav>

<nav>
  <!-- Custom navigation with hardcoded sections -->
  <a href="#emergency">Emergency Services</a>
  <a href="#about">About Us</a>
  <a href="#data">Citation</a>
</nav>

  <main>
    <div class="content-section">
      <h2 id="home" style="font-weight: bold;">Introduction</h2>
      <p>This project aims to analyze major power outages in the United States, exploring trends, causes, and their impact across different regions. We will also investigate potential patterns in outage durations, affected populations, and more. The analysis will be based on data covering several years of reported power failures.</p>

      <p>By focusing on various factors such as climate anomalies, geographic regions, and cause categories, we aim to uncover key insights into the challenges posed by power outages in different parts of the country. The findings may help in improving preparedness and response strategies for such events.</p>

      <p>The project map below illustrates the different stages and data points we will analyze throughout this study.</p>

      <!-- Project map placeholder -->
      <p><strong>Project Map:</strong> [Insert your project map here, e.g., flowchart of analysis process]</p>

      <!-- Table with column descriptions -->
      <table>
        <thead>
          <tr>
            <th>Column</th>
            <th>Description</th>
          </tr>
        </thead>
        <tbody>
          <tr>
            <td><code>'YEAR'</code></td>
            <td>Year an outage occurred</td>
          </tr>
          <tr>
            <td><code>'MONTH'</code></td>
            <td>Month an outage occurred</td>
          </tr>
          <tr>
            <td><code>'U.S._STATE'</code></td>
            <td>State the outage occurred in</td>
          </tr>
          <tr>
            <td><code>'NERC.REGION'</code></td>
            <td>North American Electric Reliability Corporation (NERC) regions involved in the outage event</td>
          </tr>
          <tr>
            <td><code>'CLIMATE.REGION'</code></td>
            <td>U.S. Climate regions as specified by National Centers for Environmental Information (9 Regions)</td>
          </tr>
          <tr>
            <td><code>'ANOMALY.LEVEL'</code></td>
            <td>Oceanic El Niño/La Niña (ONI) index referring to the cold and warm episodes by season</td>
          </tr>
          <tr>
            <td><code>'OUTAGE.START.DATE'</code></td>
            <td>Day of the year when the outage event started</td>
          </tr>
          <tr>
            <td><code>'OUTAGE.START.TIME'</code></td>
            <td>Time of the day when the outage event started</td>
          </tr>
          <tr>
            <td><code>'OUTAGE.RESTORATION.DATE'</code></td>
            <td>Day of the year when power was restored to all the customers</td>
          </tr>
          <tr>
            <td><code>'OUTAGE.RESTORATION.TIME'</code></td>
            <td>Time of the day when power was restored to all the customers</td>
          </tr>
          <tr>
            <td><code>'CAUSE.CATEGORY'</code></td>
            <td>Categories of all the events causing the major power outages</td>
          </tr>
          <tr>
            <td><code>'OUTAGE.DURATION'</code></td>
            <td>Duration of outage events (in minutes)</td>
          </tr>
          <tr>
            <td><code>'DEMAND.LOSS.MW'</code></td>
            <td>Amount of peak demand lost during an outage event (in Megawatt)</td>
          </tr>
          <tr>
            <td><code>'CUSTOMERS.AFFECTED'</code></td>
            <td>Number of customers affected by the power outage event</td>
          </tr>
          <tr>
            <td><code>'TOTAL.PRICE'</code></td>
            <td>Average monthly electricity price in the U.S. state (cents/kilowatt-hour)</td>
          </tr>
          <tr>
            <td><code>'TOTAL.SALES'</code></td>
            <td>Total electricity consumption in the U.S. state (megawatt-hour)</td>
          </tr>
          <tr>
            <td><code>'TOTAL.CUSTOMERS'</code></td>
            <td>Annual number of total customers served in the U.S. state</td>
          </tr>
          <tr>
            <td><code>'POPPCT_URBAN'</code></td>
            <td>Percentage of the total population of the U.S. state represented by the urban population (in %)</td>
          </tr>
          <tr>
            <td><code>'POPDEN_URBAN'</code></td>
            <td>Population density of the urban areas (persons per square mile)</td>
          </tr>
          <tr>
            <td><code>'AREAPCT_URBAN'</code></td>
            <td>Percentage of the land area of the U.S. state represented by the land area of the urban areas (in %)</td>
          </tr>
        </tbody>
      </table>
    </div>

    <section id="data_cleaning">
      <h2>Data Cleaning and Exploratory Analysis</h2>
      <h3>Data Cleaning</h3>
      <p>[Description of your data cleaning process]</p>
      
      <h3>Univariate Analysis</h3>
      <p>[Analysis of individual variables]</p>
      
      <h3>Bivariate Analysis</h3>
      <p>[Analysis of relationships between variables]</p>
    </section>

    <section id="missingness">
      <h2>Assessment of Missingness</h2>
      <h3>NMAR Analysis</h3>
      <p>[Content for NMAR Analysis]</p>

      <h3>Missingness Dependencies</h3>
      <p>[Content for Missingness Dependencies]</p>
    </section>

    <section id="hypothesis">
      <h2>Hypothesis Testing</h2>
      <p>[Content for Hypothesis Testing]</p>
    </section>

    <section id="predictive">
      <h2>Final Model</h2>
      <p>[Content for Final Model]</p>
    </section>

    <section>
      <h2>Fairness Analysis</h2>
      <p>[Content for Fairness Analysis]</p>
    </section>
  </main>

  <!-- Footer -->
  <footer>
    <p>&copy; 2024 Powering Through: All Rights Reserved</p>
  </footer>

</body>
</html>
