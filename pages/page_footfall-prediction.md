# Forecasting Footfall on Hampstead Heath

### Description
**Using a mobile phone derived human locaiton dataset, random forest model & interactive R Shiny dashboard to forecast footfall on Hampstead Heath under specified time & wather conditions.**


### The Problem Space & Motivations for Tackling it
I chose this topic because I wanted to combine my passion for the outdoors with data science, and mobile phone location data is increasingly central to business decisions and planning, so I was excited to get some hands on experience with it. 

Whilst my dissertatioin was an extensive exploratory analysis, and an in depth look at the merits of big data versus other more traditional research methods (namely in person observations...), I wanted to explore how more complex modelling might be applied to this dataset, in a way that would enable it to act as a tool that could aid future planning/ logistics/ resource allocation etc.

## The Data
Data for this project was compiled from **3 key sources** [joined and cleaned in R](link/to/code):


#### *Footfall Data*
The human location data for this project was kindly provided by **[WhereData](https://www.wheredata.co.uk/)**
  - this was obviously time stamped...
    
#### *Weather Data*
- Weather (temperature, preicipitation) at hourly intervals from [VisualCrossing.com]

#### *Spatial Features* 
- Physical Features of the Heath (quantified using QGIS)....
-   - QGIS was used to trace the heaths key physical features (according to the literature on park visitation & informed by observations of how people use the space)
      
    SCREENSHOT OF QGIS
    **spatial calculations then applied - to quantify these features realtive to the hex cell granularity of the data**
      - point features (benches, cafes, attractions) → point in polygon calc
      - line feature (paths, boundaries…) → length in polygon calc
      - polygon features → area in polygon overlap calc


## Methodology
**Overview**: Following extensive EDA which formed the bulk of the dissertation, Random Forest model was used to make predictions for the R Shiny dashboard.

This analysis was done using R - due to technical restraints of accessing python and setting up virtual environments on remote desktop connection (required for computing power to handle such a huge dataset)
  - *step 1 was to write a [tracking function](link/to/code) that emulated function of python's mlflow*

## Exploratory Analysis
[link to code here](link/to/code)
- KEY GRAPHS FROM DISS
- HIERARCHICAL CLUSTERING
    - *from this, it was clear that areas with similar spatial features exhibited similar visitation regimes -     distinct between groups (formed good clusters - obvious that spatial features must be included in any good model)*
- main quirk of the data??? → considerations to take forwards to predictive modelling
  - discrepancy in reporting of cross country event...

## Devising a Predictive Model
[link to code here](link/to/code)
Random forest model selected because...

- key steps in modelling...
- just weather, just physical, then combined
- had to remove any cells where more than x% contained non park 
    - this massively improved performance - removed additional noise (bc i hadnt quantified features external to          the park beyond simply being 'non park'
    - **perhaps if i classified the spatial features external to the park then this could be improved… / the
      selection of weather as cruical predictor variables was from extensively consulting the literature… if
      prediciton task weas being done for more urban areas, would have to think carefully about which sort of
      predictors u would use…( like school dropoff times, type of road, classified as residential etc, taking
      account of trainline….)**
    - **but since this exercise/ dataset was designed with parks in mind (and from my own observations of human
      movement in that space), kept just to predictors that were going to be relevant to the park…..**

- once best combination of features selected for modelling, hyperparameter tuning..
    - *manually, because of computing constrains w gridsearch or CV*
 
## final dashboard...



