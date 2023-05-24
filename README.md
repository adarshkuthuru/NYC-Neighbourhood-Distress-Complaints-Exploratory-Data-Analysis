# An Analysis of Neighbourhood Distress complaints (311 Service Requests) in NYC 
## Predicting the Responding Government Agency

**Author**: Avonlea Fisher -- Modified by Adarsh Kuthuru


<img src="https://github.com/AvonleaFisher/Analyzing-NYC-311-Service-Requests/blob/main/Images/Dashboard_screenshot.png"></a>
   

The information within this repository provides a comprehensive analysis of NYC 311 Service requests and the corresponding community districts where they were documented.

## Abstract:

This project examines extensive data on daily 311 calls in New York City, capturing information on time, location, and content. Its goal is to enhance government response to non-emergency issues by identifying trends and patterns. By analyzing public data on 311 calls and community districts, the project investigates common call types, district-specific call volumes, and the distribution of calls among various government agencies. Using natural language processing and the Keras library, a neural network is developed to classify the responding agency based on call descriptions. The best-performing model achieved a 73% accuracy rate on a random subset of the data. Notably, the New York Police Department (NYPD) handled slightly over 50% of all 311 calls, while a total of 14 government agencies were involved, posing challenges for achieving perfect classifier accuracy. This classifier has the potential to streamline the assignment of non-emergency requests to the appropriate agency in online contexts where requests generate text descriptions, as opposed to the current phone-based handling of most non-emergency service requests.

## Introduction:

The objective of this project is to analyze recent data on NYC 311 calls and develop a neural network capable of classifying the agency that responded to each call. By examining the content, timing, frequency, and location of the issues raised by 311 callers, government agencies and local policy stakeholders can better serve NYC residents. Through exploratory analysis and visualization of public 311 data, this project aims to contribute to this understanding. The modeling section focuses on demonstrating a proof-of-concept tool that efficiently connects residents to the appropriate government services.\

In this analysis, I analyze the 311 service request data for New York city between the years 2010 and 2021. \
The dataset has 25,839,156 rows and 47 columns.


## Data
The project sourced data from two main repositories:

1. [NYC Open Data's 311 Service Requests from 2010 to Present](https://data.cityofnewyork.us/Social-Services/311-Service-Requests-from-2010-to-Present/erm2-nwe9)

This dataset encompasses over 24 million 311 service requests made in New York City over the past decade. It includes details such as location, time, complaint type, and status. For this project, a subset of the data from 2020 was utilized, accessed through the Socrata Open Data (SODA) API.

2. [NYC Department of City Planning’s Community District Profiles](https://communityprofiles.planning.nyc.gov/)

The Community District Profiles website provides access to indicators data by selecting a specific profile and downloading the data. These datasets offer information on development and population for each Community District in New York City. Additionally, the 311 dataset contains community board names, which correspond to the community districts in question.

## Methods and Repository Structure
The project's notebooks follow the [OSEMN](https://people.duke.edu/~ccc14/sta-663/DataProcessingSolutions.html) process and should be followed in the specified order:

* [Obtaining_and_Scrubbing_the_Data.ipynb](https://github.com/AvonleaFisher/Analyzing-NYC-311-Service-Requests/blob/main/Obtaining_and_Scrubbing_the_Data.ipynb) — Accessing data through the SODA API and Community District profiles, handling missing and unnecessary data, ensuring consistent value formatting, and merging the datasets.
* [Exploring_the_Data](https://github.com/AvonleaFisher/Analyzing-NYC-311-Service-Requests/tree/main/Exploring_the_Data) — Generating summary statistics and interactive visualizations. Notably, noise complaints were the most frequent, and the New York Police Department (NYPD) handled the majority of calls. This section is divided into five separate notebooks due to the data size represented in the visuals:
   * Bar Charts
   * Line and Area Charts
   * Mapbox Density Heatmaps
   * Correlation Heatmap and Wordcloud
   * Scatterplots
* [Modeling_and_Interpreting.ipynb](https://github.com/AvonleaFisher/Analyzing-NYC-311-Service-Requests/blob/main/Modeling_and_Interpreting.ipynb) — Preprocessing data for modeling and evaluating different classification models using the Keras library. Performance assessment was conducted on 1) test data from the resampled subset and 2) another random subset of the non-resampled data.

## Results

The best-performing model achieved 92.6% accuracy on the test data and 72.8% accuracy on the random subset. Notably, it showed the highest success rate for calls assigned to the NYPD, HBD, and DPR.

#### Loss and Accuracy Curves
![Loss and Accuracy](https://github.com/AvonleaFisher/Analyzing-NYC-311-Service-Requests/blob/main/Images/acc_loss.png)
> The accuracy and loss curves demonstrate that the model began learning at a mostly consistent rate after approximately 50 epochs.

#### Mapbox Density Heatmap Example
![August](https://github.com/AvonleaFisher/Analyzing-NYC-311-Service-Requests/blob/main/Images/august.gif)
> This animation displays the day-to-day fluctuations in call volume across NYC in August 2020. The yellow areas on the map indicate high call volume.

#### Most Frequent Words in Call Descriptions
<img src="https://github.com/AvonleaFisher/Analyzing-NYC-311-Service-Requests/blob/main/Images/wordcloud.png" width="400" height="400">

> Noise-related complaints dominated the majority of calls each month.
> <sup>Wordcloud mask attribution: Image #19210492 at VectorStock.com<sup>

#### Top 5 Agencies with Highest Number of Calls: Hourly Totals
<img src="https://github.com/AvonleaFisher/Analyzing-NYC-311-Service-Requests/blob/main/Images/Total_Calls_Hour.png" width="400" height="400">

> Calls to the NYPD, including noise complaints, peak during the early and late hours of the day.

## Recommendations:

* Explore the development of similar classification models to connect individuals with non-emergency government services and guide them to the appropriate responding agency. This application would require training on a larger and more diverse set of descriptors.
* Agencies should closely monitor call volume patterns in relation to temporal, geographic, and environmental factors. Certain changes can be anticipated, such as increased tree damage after severe weather events, nighttime peaks in noise complaints, and consistently high call volumes in densely populated areas like Manhattan. With regards to COVID-19, since related complaints have emerged recently, careful attention should be paid to the circumstances surrounding any future spikes.
* Given that the same agency handles the majority of non-emergency and emergency requests, local stakeholders may want to assess whether the current distribution of responsibilities in handling 311 calls effectively meets the needs of city residents. Considering concerns about law enforcement overutilization in non-emergency situations, this area could be explored further.

## Limitations & Next Steps

The input variable, call descriptor, comprised approximately 800 unique string values before preprocessing. Consequently, the model has only been trained to recognize a relatively limited set of words found in service request descriptions. Training on a larger and more diverse range of descriptions could enhance the model's capability to accurately assign descriptions to responding agencies.