---
title: "Powering Through: Analyzing Trends in Major US Power Outages"
nav_order: 1
---
<style>
  /* Background Image Section (Placed at the top) */
.background-image {
  background-image: url("images/header_image.jpeg"); /* Corrected to .jpeg extension */
  background-size: cover;   /* Ensures the image covers the entire area */
  background-position: center; /* Centers the background image */
  height: 400px; /* Adjust the height as necessary */
  text-align: center; /* Centers the text inside the banner */
  color: white; /* Makes text white for contrast */
  padding-top: 120px; /* Adds padding to push the title down a bit from the top */
  margin-bottom: 0; /* Removes the bottom margin */
  position: relative;
}

.background-image h1 {
  font-size: 4em;
  text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.7); /* Adds shadow for better visibility */
  font-weight: bold;
  margin: 0; /* Removes any default margin */
}

  /* Navigation Bar - Positioned at the Top Right */
  .navbar {
    position: fixed;
    top: 0;
    right: 0;
    padding: 15px;
    background-color: rgba(0, 0, 0, 0.5); /* Dark background to contrast with white text */
    z-index: 1000;
    display: flex;
    flex-direction: column;
  }

  .navbar ul {
    list-style-type: none;
    padding: 0;
    margin: 0;
  }

  .navbar li {
    margin: 10px 0; /* Vertical spacing between links */
  }

  .navbar a {
    text-decoration: none;
    color: white; /* White text color */
    font-size: 1.2em;
    font-weight: bold;
    padding: 10px;
  }

  .navbar a:hover {
    background-color: #f39c12;
    color: black;
    border-radius: 5px;
  }

  /* Header Style for Sections (e.g., Introduction, Emergency Services, etc.) */
  h2 {
    margin-top: 2em;
    padding-bottom: 0.5em;
    border-bottom: 2px solid #eaecef;
    text-align: center;
    color: black;
    font-size: 2.5em;
    font-weight: bold;
  }

  /* Subsection Titles (h3) - Black Text */
  h3 {
    margin-top: 1.5em;
    color: black;
    text-align: center;
    font-size: 2em;
  }

  /* Body Text - Centered */
  .content-section {
    text-align: center;
    margin-top: 60px; /* To prevent content from being hidden under the navbar */
  }

  /* Add padding for body content to avoid overlap with the fixed navbar */
  body {
    padding-top: 60px; /* Adjusted padding to fit the fixed navbar */
  }

  /* Responsive Design for Mobile and Tablet */
  @media (max-width: 768px) {
    /* Adjust the background image height and title font size for smaller screens */
    .background-image {
      height: 300px; /* Reduce height for smaller devices */
      padding-top: 50px; /* Reduce top padding for mobile */
    }

    .background-image h1 {
      font-size: 2.5em; /* Smaller title font size for mobile */
    }

    /* Adjust navbar to display horizontally on smaller screens */
    .navbar {
      position: static;
      width: 100%; /* Make the navbar full-width */
      flex-direction: row;
      justify-content: space-around; /* Space out navbar links */
      padding: 10px 0;
    }

    .navbar li {
      margin: 0 10px; /* Horizontal spacing between navbar items */
    }

    .navbar a {
      font-size: 1em; /* Smaller text size for navbar links */
    }

    /* Adjust content section margins */
    .content-section {
      margin-top: 20px; /* Less space on top */
    }
  }

  /* Further adjustments for very small screens (mobile-first) */
  @media (max-width: 480px) {
    .background-image h1 {
      font-size: 2em; /* Smaller title font size for very small screens */
    }

    .navbar a {
      font-size: 0.9em; /* Even smaller text size for very small screens */
    }
  }
</style>

<!-- Background Image Section -->
<div class="background-image">
  <h1>Powering Through: Analyzing Trends in Major US Power Outages</h1>
</div>

<!-- Navigation Bar (Fixed at Top Right) -->
<nav class="navbar">
  <ul>
    <li><a href="#home">Home</a></li>
    <li><a href="#emergency_services">Emergency Services</a></li>
    <li><a href="#about_us">About Us</a></li>
    <li><a href="#citations">Citations</a></li>
  </ul>
</nav>

<!-- Content Sections -->
<div class="content-section">
  <h2 id="home">Introduction</h2>
  <p>Welcome to the first page of our power outage analysis! Here, we'll explore key trends and insights into the patterns and impact of power disruptions across the United States.</p>

  <h2 id="data_cleaning">Data Cleaning and Exploratory Analysis</h2>

  <h3>Data Cleaning</h3>
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

  <h2 id="missingness">Assessment of Missingness</h2>

  <h3>NMAR Analysis</h3>
  <p>[Content for NMAR Analysis]</p>

  <h3>Missingness Dependencies</h3>
  <p>[Content for Missingness Dependencies]</p>

  <h2 id="hypothesis">Hypothesis Testing</h2>
  <p>[Content for Hypothesis Testing]</p>

  <h2>Framing a Prediction Problem</h2>
  <p>[Content for Prediction Problem]</p>

  <h2>Baseline Model</h2>
  <p>[Content for Baseline Model]</p>

  <h2 id="predictive">Final Model</h2>
  <p>[Content for Final Model]</p>

  <h2>Fairness Analysis</h2>
  <p>[Content for Fairness Analysis]</p>

</div>
