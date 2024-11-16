<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Powering Through: Analyzing Trends in Major US Power Outages</title>
  
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
    .content-section h1, .content-section h2, .content-section h3, .content-section h4, .content-section h5, .content-section h6 {
      color: black !important;
    }

    /* Navigation Bar Styling */
    nav {
      background-color: #333;
      overflow: hidden;
    }
    nav a {
      float: left;
      display: block;
      color: white;
      text-align: center;
      padding: 14px 20px;
      text-decoration: none;
    }
    nav a:hover {
      background-color: #ddd;
      color: black;
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

    th, td {
      font-family: 'Roboto Mono', monospace;
      font-weight: 500;
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
  <h1>Powering Through: Analyzing Trends in Major US Power Outages</h1>
</div>
<nav>
    <a href="#home">Home</a>
    <a href="#about">About</a>
    <a href="#analysis">Analysis</a>
    <a href="#data">Data</a>
    <a href="#contact">Contact</a>
  </nav>

<div class="content-section">
  <h2 id="home" style="font-weight: bold;">Introduction</h2>
  <p> paragraph1.</p>
  <p> paragraph2.</p>
  <p> Project map</p>
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
          <td>Amount of peak demand lost during an outage event (in Megawatt) [but in many cases, total demand is reported]</td>
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

<div class="content-section">
  <h2 id="home" style="font-weight: bold;">Introduction</h2>
  <p>Welcome to the first page of our power outage analysis! Here, we'll explore key trends and insights into the patterns and impact of power disruptions across the United States.</p>

  <h2 id="data_cleaning">Data Cleaning and Exploratory Analysis</h2>

  <h3 style="font-weight: bold;">Data Cleaning</h3>
  <p>[Description of your data cleaning process, including:
    - Initial dataset overview
    - Steps taken to clean the data
    - Handling of problematic values]</p>

  <h3>Univariate Analysis</h3>
  <p>[Analysis of individual variables, including:
    - Distribution of outage durations
    - Frequency of different causes
    - Geographic distribution]</p>

  <h3>Bivariate Analysis</h3>
  <p>[Analysis of relationships between variables, including:
    - Correlation between factors
    - Key patterns discovered
    - Notable relationships]</p>

  <h2 id="missingness" style="font-weight: bold;">Assessment of Missingness</h2>

  <h3>NMAR Analysis</h3>
  <p>[Content for NMAR Analysis]</p>

  <h3>Missingness Dependencies</h3>
  <p>[Content for Missingness Dependencies]</p>

  <h2 id="hypothesis" style="font-weight: bold;">Hypothesis Testing</h2>
  <p>[Content for Hypothesis Testing]</p>

  <h2 style="font-weight: bold;">Framing a Prediction Problem</h2>
  <p>[Content for Prediction Problem]</p>

  <h2 style="font-weight: bold;">Baseline Model</h2>
  <p>[Content for Baseline Model]</p>

  <h2 id="predictive" style="font-weight: bold;">Final Model</h2>
  <p>[Content for Final Model]</p>

  <h2 style="font-weight: bold;">Fairness Analysis</h2>
  <p>[Content for Fairness Analysis]</p>
</div>
<footer>
    <p>&copy; 2024 Powering Through: All Rights Reserved</p>
  </footer>
</body>
</html>
