# STDM (CEGE0042 - Spatial-Temporal Data Analysis and Data Mining)
## THEFT CRIME CLUSTERING IN CITY OF CHICAGO USING DENSITY BASED ALGORITHM
*The code can be found in chicago.ipynb*


Content
1. Data Preprocessing
    1.1 Importing Data
    1.2 Preprocessing the Datasets
    1.3 Preprocessing Shapefile
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
