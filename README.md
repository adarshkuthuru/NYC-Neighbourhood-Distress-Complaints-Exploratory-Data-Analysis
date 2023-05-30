# An Analysis of Neighbourhood Distress complaints (311 Service Requests) in NYC 

**Author**:  Adarsh Kuthuru


The information within this repository provides a comprehensive analysis of NYC 311 Service requests and the corresponding community districts where they were documented.

## Introduction:

The primary goal of this project is to conduct a comprehensive analysis of current NYC 311 call data. By carefully examining the details encompassing the nature of the issues, the timing and frequency of the calls, as well as their geographical distribution, government agencies and local policymakers can enhance their provision of services to NYC residents. Through extensive exploratory analysis and insightful data visualization of the publicly available 311 Service Requests data, this project endeavors to contribute to the existing understanding of the call landscape. Moreover, the modeling section aims to present a practical tool that serves as a proof-of-concept, efficiently facilitating residents' connection with the appropriate government services.

## Data
The project sourced data from two main repositories:

1. [NYC Open Data's 311 Service Requests from 2010 to Present](https://data.cityofnewyork.us/Social-Services/311-Service-Requests-from-2010-to-Present/erm2-nwe9)

This dataset encompasses over 24 million 311 service requests made in New York City over the past decade. It includes details such as location, time, complaint type, and status. For this project, a subset of the data from 2023 was utilized, accessed through the Socrata Open Data (SODA) API.

2. [NYC Department of City Planning’s Community District Profiles](https://communityprofiles.planning.nyc.gov/)

The Community District Profiles website provides access to indicators data by selecting a specific profile and downloading the data. These datasets offer information on development and population for each Community District in New York City. Additionally, the 311 dataset contains community board names, which correspond to the community districts in question.

## Understanding the code (311_service_requests_EDA_Google_Colab.ipynb):

The provided Python code represents an extensive data analysis project focused on 311 service requests data in New York City. The code showcases a structured and comprehensive approach to exploring the dataset, employing various analytical techniques and visualization methods. It exhibits a thorough understanding of data retrieval, data cleaning, and data visualization processes -- follows the [OSEMN](https://people.duke.edu/~ccc14/sta-663/DataProcessingSolutions.html) process.

The code begins with an organized table of contents, allowing for easy navigation and referencing of specific sections. It demonstrates a disciplined and systematic approach to code organization, promoting code readability and maintainability, which are essential in corporate settings.

Throughout the code, the use of informative section headings and subheadings helps create a clear and logical flow of analysis. The inclusion of comments further enhances comprehension and aids in understanding the rationale behind specific code blocks and analysis steps.

The code incorporates diverse data sources, including the Socrata Open Data API (Soda), Google Drive, JSON objects, and local CSV files, indicating a sophisticated understanding of data integration techniques. Additionally, the code employs appropriate data cleaning methodologies to ensure the integrity and quality of the dataset.

By leveraging various visualizations, such as plots and charts, the code presents insights and analysis of the 311 service requests data. It showcases a thoughtful selection of visual representations to effectively communicate findings, supporting data-driven decision-making in corporate environments.

Furthermore, the code demonstrates a robust exploratory data analysis process, examining different dimensions of the dataset over time. Time series analysis, anomaly detection, and comparative analysis across boroughs highlight the code's comprehensive approach to uncovering patterns and trends within the data.

Overall, the provided Python code exemplifies a professional and meticulous approach to data analysis, adhering to corporate standards of clarity, organization, and attention to detail.

## Sample results of the analysis:

![1](https://github.com/adarshkuthuru/NYC-Neighbourhood-Distress-Complaints-Exploratory-Data-Analysis/blob/main/images/img1.jpg)

![2](https://github.com/adarshkuthuru/NYC-Neighbourhood-Distress-Complaints-Exploratory-Data-Analysis/blob/main/images/img5.1.2.jpg)

![3](https://github.com/adarshkuthuru/NYC-Neighbourhood-Distress-Complaints-Exploratory-Data-Analysis/blob/main/images/img5.1.4.jpg)

![4](https://github.com/adarshkuthuru/NYC-Neighbourhood-Distress-Complaints-Exploratory-Data-Analysis/blob/main/images/img5.2.6.jpg)

![5](https://github.com/adarshkuthuru/NYC-Neighbourhood-Distress-Complaints-Exploratory-Data-Analysis/blob/main/images/img5.3.4.jpg)

![6](https://github.com/adarshkuthuru/NYC-Neighbourhood-Distress-Complaints-Exploratory-Data-Analysis/blob/main/images/img6.1.5.jpg)

![7](https://github.com/adarshkuthuru/NYC-Neighbourhood-Distress-Complaints-Exploratory-Data-Analysis/blob/main/images/img6.2.2.jpg)

![8](https://github.com/adarshkuthuru/NYC-Neighbourhood-Distress-Complaints-Exploratory-Data-Analysis/blob/main/images/img6.2.3.jpg)