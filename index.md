# Welcome to My Final Prodject Page

This is a website built entirely with GitHub Pages and Markdown with HTML snipits for the visualizations!

- [About This Site](#about-this-site)
  - [Key Features](#key-features)
  - [Data Sources/Ideas](#data-sourcesideas)
  - [Where's Schueller?](#wheres-schueller)
    <!-- This is my above and beyond component, this can be used to navigate the website and will be more usefull once more is included on it-->



## Introduction
### Data and Data source
The dataset analyzed in this project is the “Chicago Crime Incidents 2001 to Present”, sourced by Harshdeep Sharma on the website Kaggle, extracted from the Chicago Police Department’s CLEAR (Citizen Law Enforcement Analysis and Reporting) system. This data represents a public record of reported incidents of crime (excluding murders, where data exists for each victim) that occurred in the city of Chicago. The dataset is quite extensive, comprising approximately 8 million records with very few instances of missing data. Each record represents a distinct incident and includes key variables, such as the date and time of the occurrence, block-level address, crime type (following IUCR codes), location description (street, residence), arrest status, and domestic classification. Crucially for our spatial analysis, the data includes latitude and longitude coordinates for the majority of incidents.


### Research Questions
This analysis attempts to answer two questions regarding the evolution of crime in Chicago:
* How have the geographic locations (“Hotspots”) of crimes changed from year to year?
* Has there been a significant change in the overall volume and specific types of crimes (“Trends”) committed over the years?


With the first question, we aim to observe if crime remains concentrated in specific neighborhoods or if it fluctuates due to other confounding variables. With the second question, we aim to identify trends in the most frequently reported crimes and observe how their prevalence has changed over the two decades.


### Analysis Approach
Our approach involves a combination of time-series aggregation and geospatial visualization, for our first research question we used the geospatial visualizations and for the second we focused on time series aggregation and analysis. 


### Question 1

[Link to Google Colab](https://colab.research.google.com/drive/1lOpVAjmulkl0FqykBsH9izfVos_eGKYB#scrollTo=IAPpOe-wae91)

For this first question we used a scatter mapbox in conjunction with binning To create the visualization.

{% include chicago_crime_hotspots.html %}

### Data Preparation Steps:
* Drop rows without coordinates.
* Converting each crime’s location into an H3 hexagon.
* Group incidents by year and by H3 cell.


We initially attempted a standard heatmap using all ~8 million inputs, However we repeatedly ran into memory issues with colab and due to the size of the data every time we had to restart it added about 3 minutes just for it to iterate over the data. Switching to H3 binning enabled us to go through section by section and find like points instead of plotting each of the 8 million points. 





 

