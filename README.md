# Theft Crime Clustering in City of Chicago: Density Based Algorithm
A [Spatial-Temporal Data Analysis and Data Mining project](https://github.com/AlinZohari/STDM/blob/main/chicago.ipynb)

**Table of Content**

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
![image](https://github.com/AlinZohari/STDM/assets/89179323/05e23de0-0bef-45fc-9b85-5f619d100888)
![image](https://github.com/AlinZohari/STDM/assets/89179323/5b296e15-8d62-4ba3-a7cb-8d3ba7ee1911)
![image](https://github.com/AlinZohari/STDM/assets/89179323/1afde2de-92bf-4bf9-8d1b-1105754371aa)







1. Data Preprocessing<br>
    1.1 Importing Data<br>
    1.2 Preprocessing the Datasets<br>
    1.3 Preprocessing Shapefile<br>
    
2. Plotting the point to the Shapefile
    - Change the CRS of both datasets and shapefile to ESPG: 3435
3. EDA
    3.1 Crime Type Distribution
    3.2 Theft by month in the year 2022
    3.3 Theft by Part of the Day in July 2022
4. ESTDA
    4.1 KDE in July 2022
    4.2 KDE of Part of the Day in July 2022
    4.3 3D Scatterplot 
5. Hyperparameter Tuning of Clustering
    5.1 Preparation for Hyperparameter Tuning and Exploration for the Number of Clusters
    5.2 Hyperparameter Tuning: Epsilon (eps)
    5.3 Hyperparameter Tuning: Minimum Point (MinPts)
6. Visualisation of DBSCAN
    6.1 Hyperparameter: eps=7500, MinPts=2
    6.2 Hyperparameter: eps=4500, MinPts=2
7. Visualisation of ST-DBSCAN
    7.1 Hyperparameter: eps=7500, MinPts=2
    7.2 Hyperparameter: eps=4500, MinPts=2
    7.3 Hyperparameter: eps=5000, MinPts=2
   
  



Abstract

Identifying crime patterns and trends is an essential initial phase in developing effective prevention measures, as it provides law enforcement officials to prioritize their efforts on the areas where crime is most likely to occur (Cohen and Tita, 1999). Hence, it is vital to identify and investigate these crime clusters. Theft has been identified as the most prevalent crime type in Chicago from January to December of 2022, making it an important area of investigation. To analyse the spatial distribution of theft incidents, Kernel Density Estimation (KDE) is employed to estimate the density of theft occurrences throughout the city. DBSCAN and ST-DBSCAN are the method use for identifying clusters in spatial and spatial-temporal data, respectively. The use of Silhouette Score as a performance validation metric ensures the optimal hyperparameter tuned and produce a reliable cluster models.
