# Theft Crime Clustering in City of Chicago: Density Based Algorithm
A [Spatial-Temporal Data Analysis and Data Mining project](https://github.com/AlinZohari/STDM/blob/main/chicago.ipynb)

**Table of Content**
1. [Notebook Content](https://github.com/AlinZohari/STDM/blob/main/README.md#notebook-content)
2. [Abstract](https://github.com/AlinZohari/STDM/blob/main/README.md#abstract)
3. [Data Sources](https://github.com/AlinZohari/STDM/blob/main/README.md#data-sources)
4. [Exploratory Data Analysis](https://github.com/AlinZohari/STDM/blob/main/README.md#exploratory-data-analysis)
5. [Exploratory Spatial-Temporal Data Analysis](https://github.com/AlinZohari/STDM/blob/main/README.md#exploratory-spatial-temporal-data-analysia)
6. [DBSCAN](https://github.com/AlinZohari/STDM/blob/main/README.md#dbscan)
7. [ST-DBSCAN](https://github.com/AlinZohari/STDM/blob/main/README.md#st-dbscan) 


## Notebook Content
The code of this project are in this [jupyter notebook](https://github.com/AlinZohari/STDM/blob/main/chicago.ipynb) which were done step-by-step

1. Data Preprocessing <br>
    1.1 Importing Data <br>
    1.2 Preprocessing the Datasets <br>
    1.3 Preprocessing Shapefile <br>
    
2. Plotting the point to the Shapefile <br>
Change the CRS of both datasets and shapefile to ESPG: 3435 <br>
    
3. EDA <br>
    3.1 Crime Type Distribution <br>
    3.2 Theft by month in the year 2022 <br>
    3.3 Theft by Part of the Day in July 2022 <br>
    
4. ESTDA <br>
    4.1 KDE in July 2022 <br>
    4.2 KDE of Part of the Day in July 2022 <br>
    4.3 3D Scatterplot <br>
    
5. Hyperparameter Tuning of Clustering <br>
    5.1 Preparation for Hyperparameter Tuning and Exploration for the Number of Clusters <br>
    5.2 Hyperparameter Tuning: Epsilon (eps) <br>
    5.3 Hyperparameter Tuning: Minimum Point (MinPts) <br>
    
6. Visualisation of DBSCAN <br>
    6.1 Hyperparameter: eps=7500, MinPts=2 <br>
    6.2 Hyperparameter: eps=4500, MinPts=2 <br>
    
7. Visualisation of ST-DBSCAN <br>
    7.1 Hyperparameter: eps=7500, MinPts=2 <br>
    7.2 Hyperparameter: eps=4500, MinPts=2 <br>
    7.3 Hyperparameter: eps=5000, MinPts=2 <br>

## Abstract
Identifying crime patterns and trends is an essential initial phase in developing effective prevention measures, as it provides law enforcement officials to prioritize their efforts on the areas where crime is most likely to occur (Cohen and Tita, 1999). Hence, it is vital to identify and investigate these crime clusters. Theft has been identified as the most prevalent crime type in Chicago from January to December of 2022, making it an important area of investigation. To analyse the spatial distribution of theft incidents, Kernel Density Estimation (KDE) is employed to estimate the density of theft occurrences throughout the city. DBSCAN and ST-DBSCAN are the method use for identifying clusters in spatial and spatial-temporal data, respectively. The use of Silhouette Score as a performance validation metric ensures the optimal hyperparameter tuned and produce a reliable cluster models.

## Data Sources 
The City of Chicago crime datasets was obtain from an [open source website](https://data.cityofchicago.org/Public-Safety/Crimes-2001-to-Present/ijzp-q8t2)
The data then were filtered and chosen to only from 01/01/2022 00:00:00 to 31/12/2022 11:59:59.

The shapefile of City of Chicago was obtain from [Chicago Data Portal website](https://data.cityofchicago.org/Facilities-Geographic-Boundaries/Boundaries-Community-Areas-current-/cauq-8yn6) where it is divided into 77 Community Areas.
This shapefile was initially  in WGS84 and it is converted to State Plane Illinois East NAD 1984 Projection (EPSG3435). 
A point geometry are then created to the datasets having a Longitude and Latitude in the same projection as the shapefile. 
This is for the ease of applying the clustering (Rahimi & Yazdani-Chamzini, 2019).

## Exploratory Data Analysis
![image](https://github.com/AlinZohari/STDM/assets/89179323/05e23de0-0bef-45fc-9b85-5f619d100888) <br>
From figure above it shows the highest theft rate is in July with 5620 occurrence. Further investigation was conducted to determine the time of day when thefts occurred most frequently in month of July. 
The study found that the highest rate of thefts occurred during the night with a total of 1,694 occurrences. The second-highest rate of thefts occurred in the afternoon with 1,501 occurrences. Hence, this study would be looking at the clustering of theft in July 2022 and further the clustering of Part of Day the crime is happening.
Part of the day is determine as follow:
Morning: 5am to 12pm, Afternoon: 12pm to 5pm, Evening: 5pm to 9pm and Night: 9pm to 4am.

## Exploratory Spatial-Temporal Data Analysis
![image](https://github.com/AlinZohari/STDM/assets/89179323/5b296e15-8d62-4ba3-a7cb-8d3ba7ee1911) <br>
Kernel Density Estimation (KDE) in spatial analysis is use to estimate the high and low density of theft distribution in space using 3D scatterplot <br>
![image](https://github.com/AlinZohari/STDM/assets/89179323/1afde2de-92bf-4bf9-8d1b-1105754371aa) <br>

![image](https://github.com/AlinZohari/STDM/assets/89179323/bd305633-b34a-45fd-9964-49dcd73bf0c2) <br>

## DBSCAN
(Density-Based Spatial Clustering Application with Noise)

![image](https://github.com/AlinZohari/STDM/assets/89179323/07fc61ec-8bc7-4496-bd34-25b88abf6465) <br>
DBSCAN Cluster the Month of July 2022. The cluster shown is 2 with its hyperparameter set to epsilon: 7500, MinPts: 2 and Silhouette Score: 0.4750

![image](https://github.com/AlinZohari/STDM/assets/89179323/eee2bf28-fdd9-4596-8b6e-12802751a15c) <br>
DBSCAN Cluster the Month of July 2022. The cluster shown is 6 with its hyperparameter set to epsilon: 4500, MinPts: 2 and Silhouette Score: 0.1900

## ST-DBSCAN
(Spatial-Temporal Density-Based Spatial Clustering of Applications with Noise)

![image](https://github.com/AlinZohari/STDM/assets/89179323/a56f19a0-fd46-476c-8ecb-3967ad1bbc09) <br>
ST-DBSCAN Clusters of Theft in Chicago for different Part of the Day. From top left temporal_eps 1: Morning, 2: Afternoon, 3: Evening and 4: Night
