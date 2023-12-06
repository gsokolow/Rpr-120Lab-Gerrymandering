# Title of Study

### Authors

- Grace Sokolow\*, gsokolow@middlebury.edu, @gsokolow, Middlebury College (Undergraduate)

\* Corresponding author and creator

## Abstract

This study is a *reproduction/replication* of:

> Kimambo, Niwaeli. 2021. *Lec/Lab: Gerrymandering: Maps and political representation* Human Geography with GIS (GEOG 120) at Middlebury College.

The original lab aims to determine whether North Carolina's 2019 congressional districts, which were redrawn by court order, are fairer than the 2016 districts based on geographic compactness and political representation.
First, votes cast in the 2016 presidential election are used to estimate the percentage of Republican voters in the 2016 and 2019 congressional districts.
Then, compactness scores are calculated by multiplying the area by 400π and dividing by the perimeter squared.
The deliverables include summary statistics for the compactness and percentage of Republicans from the 2026 and 2019 districts, as well as 4 maps: 
percentage votes for Republican presidential candidate by voting precinct, percentage votes for the 2016 Republican presidential candidate by 2016 districts, percentage of votes for the 2016 Republican presidential candidate by 2019 districts, and the compactness scores for each 2016 and 2019 district.

This replication shifts the computational environment from QGIS to Python. Several data layers are provided for the original lab, including the 2016 and 2019 congressional district maps and the 2016 North Carolina voting precints and presidential election data. I will develop the code for this study using the originally given data layers, but once I have it running I will attempt to download them directly from the internet to improve transparency and reproducibility. I will also archive copies of both the originally given data and the newly downloaded data.


## Study Metadata

- `Key words`: gerrymandering, north carolina, area weighted reaggregation, 2016 elections, congressional redistricting
- `Subject`: Social and Behavioral Sciences: Geography
- `Date created`: November 30, 2023
- `Date modified`: November 30, 2023
- `Funding Name`: N/A
- `Course Title`: Open Source GIS (Middlebury College, Fall 2023)
- `Award info URI`: N/A
- `Award number`: N/A


#### Original study spatio-temporal metadata

-  `Spatial Coverage`: North Carolina, USA.
- `Spatial Resolution`: Congressional districts, voting precincts
- `Spatial Reference System`: 32119 NAD 1983 North Carolina
- `Temporal Coverage`: [2016](https://www.ncleg.gov/Redistricting/DistrictPlanMap/C2016E) - [2019](https://www.ncleg.gov/Redistricting/DistrictPlanMap/C2019E)
- `Temporal Resolution`: One election cycle


## Study design

This study is a **reproduction** of Kimambo's 2021 lab. No changes are planned prior to getting the lab up and running in python. 

Kimambo's original lab is an observational study of partisan gerrymandering in North Carolina. It aims to determine if the court-ordered redistricting of North Carolina's 2016 districts resulted in districts that were more fair in terms of geographic compactness and political representation. An area weighted reaggregation is used to allocate votes for the Republican presidential candidate in 2016 to North Carolina's 2016 and 2019 congressonal districts. To calculate compactness for each district, the following equation is used: compactness = 400 * π * area / perimeter^2.

## Materials and procedure

N/A

### Computational environment

This reproduction study uses Python 3.11.5. 
All imported packages and versions can be found under /procedure/environment/requirements.txt.

### Data and variables

There are two sets of data used in this replication study: the original files given with the lab, and the newly downloaded files added for improved reproducibility. 
The newly downloaded files *should* contain the same information as the original givens. 
All data sources are secondary.

### Secondary Data Sources

#### 2016_Contingent_Congressional_Plan_Corrected.shp

**Standard Metadata**

- `Abstract`: North Carolina Legislature's version of U.S. Congressional Districts in 2016. These districts were drawn after the Supreme Court found their 2011 districts to be an illegal racial gerrymander. 
- `Spatial Coverage`: North Carolina, USA
- `Spatial Resolution`: U.S. Congressional Districts
- `Spatial Reference System`: 32119 NAD 1983 North Carolina
- `Temporal Coverage`: One election cycle
- `Temporal Resolution`: 2016
- `Lineage`: Retrieved from the [North Carolina General Assembly](https://www.ncleg.gov/Redistricting) and distributed by Professor Niwaeli Kimambo. It is unclear if further processing occured. 
- `Distribution`: Retrieved from the [North Carolina General Assembly](https://www.ncleg.gov/Redistricting) under 'District Plans Enacted by the Court' > 'Enacted 2016'
- `Constraints`: Legal constraints for *access* or *use* to protect *privacy* or *intellectual property rights*: N/A
- `Data Quality`: Quality unknown
- `Variables`: 
  - `Label`: District
  - `Alias`: U.S. Congressional District
  - `Definition`: unique district number
  - `Type`: int64
  - `Accuracy`: N/A
  - `Domain`: 1, 13
  - `Missing Data Value(s)`: N/A
  - `Missing Data Frequency`: N/A

#### C-Goodwin-A-1-TC.shp

**Standard Metadata**

- `Abstract`: North Carolina Legislature's version of U.S. Congressional Districts in 2019. These districts were drawn after the 2016 districts were found to be partisan gerrymanders. 
- `Spatial Coverage`: North Carolina, USA
- `Spatial Resolution`: U.S. Congressional Districts
- `Spatial Reference System`: 32119 NAD 1983 North Carolina
- `Temporal Coverage`: One election cycle
- `Temporal Resolution`: 2019
- `Lineage`: Retrieved from the [North Carolina General Assembly](https://www.ncleg.gov/Redistricting) and distributed by Professor Niwaeli Kimambo. It is unclear if further processing occured. 
- `Distribution`: Retrieved from the [North Carolina General Assembly](https://www.ncleg.gov/Redistricting) under 'District Plans Enacted by the Court' > 'Enacted 2019'
- `Constraints`: Legal constraints for *access* or *use* to protect *privacy* or *intellectual property rights*: N/A
- `Data Quality`: Quality unknown
- `Variables`:
  - `Label`: DISTRICT
  - `Alias`: U.S. Congressional District
  - `Definition`: unique district number
  - `Type`: object
  - `Accuracy`: N/A
  - `Domain`: 1, 13
  - `Missing Data Value(s)`: N/A
  - `Missing Data Frequency`: N/A

#### precincts.shp

**Standard Metadata**

- `Abstract`: North Carolina voting precincts from 2016. 
- `Spatial Coverage`: North Carolina, USA
- `Spatial Resolution`: Voting precincts
- `Spatial Reference System`: 4269 North American Datum 1983
- `Temporal Coverage`: One election cycle
- `Temporal Resolution`: 2016
- `Lineage`: Retrieved from the North Carolina State Board of Elections; [precinct shapefiles](https://www.ncsbe.gov/results-data/voting-maps-redistricting), [tabular voting results](https://er.ncsbe.gov/downloads.html) and distributed by Professor Niwaeli Kimambo. The two data sources appear to have been joined but further information about how is unavailable. 
- `Distribution`: Retrieved from the North Carolina State Board of Elections; [precinct shapefiles](https://www.ncsbe.gov/results-data/voting-maps-redistricting) at Geospatial Files > Precinct Files > Precinct Shapefiles (folder) > SBE_PRECINCTS_20161004.zip; [tabular voting results](https://er.ncsbe.gov/downloads.html) under 11/08/2016
- `Constraints`: Legal constraints for *access* or *use* to protect *privacy* or *intellectual property rights*: N/A
- `Data Quality`: Quality unknown
- `Variables`:

| Label | Alias | Definition | Type | Accuracy | Domain | Missing Data Value(s) | Missing Data Frequency |
| :--: | :--: | :--: | :--: | :--: | :--: | :--: | :--: |
| PREC_ID | Precinct_ID | precinct id| object | N/A | N/A | N/A | N/A |
| COUNTY_NAM | county name| precinct county name | object | N/A | N/A | N/A | N/A |
| dem | democratic votes | votes for Democratic Party candidate in 2016 presidential election | int64 | N/A | 1, 4979 | N/A | N/A |
| rep | republican votes | votes for Republican Party candidate in 2016 presidential election | int64 | N/A | 2, 4808 | N/A | N/A |
| cntyprec | unique precinct identifier | concatenation of county name and precinct id | object | N/A | N/A | N/A | N/A |

### Prior observations  

Prior experience with the study area, prior data collection, or prior observation of the data can compromise the validity of a study, e.g. through p-hacking.
Therefore, disclose any prior experience or observations at the time of study pre-registration here, with example text below:

At the time of this study pre-registration, the author had prior experience with this data having worked through the original lab problem as a student in 2021. During the summer of 2022, the author was a participant at the Spatial Modeling of Electoral Redistricting REU at the University of Puget Sound, where she studied gerrymandering and worked closely with spatial measures including but not limited to compactness scores. The study area for that reseatch was the entire United States and thus included North Carolina. 



For each secondary source, declare the extent to which authors had already engaged with the data:

For the three given datasets (2016_Contingent_Congressional_Plan_Corrected.shp; C-Goodwin-A-1-TC.shp; precincts.shp), the author has observed the full dataset through the original completion of the lab in fall 2021. 

For the three newly downloaded files, the data is available, but only metadata has been observed (following the sources listed in the original lab). 

- [ ] data is not available yet
- [ ] data is available, but only metadata has been observed
- [ ] metadata and descriptive statistics have been observed
- [ ] metadata and a pilot test subset or sample of the full dataset have been observed
- [ ] the full dataset has been observed. Explain how authors have already manipulated / explored the data.
        

### Bias and threats to validity

Given the research design and primary data to be collected and/or secondary data to be used, discuss common threats to validity and the approach to mitigating those threats, with an emphasis on geographic threats to validity.

The original study being replicated is a lab used in Human Geography with GIS, an introductory level vector GIS course at Middlebury College. Thus, the lab has been simplified and makes several stated assumptions:
    1. *We are simplifying voting results as votes cast at a polling station for the Democratic (dem) or Republican (rep) candidate for president in 2016.*
    This presents several threats to validity. First, using votes from a presidential election as a proxy for votes cast in a congressional election can be misleading because some voters, especially in swing states like North Carolina, might vote for a candidate from one party in the presidential election and another in a congressional race. This may be particularly relevant for the 2016 presidential election, which was a contest between two extremely polarizing figures: Hillary Clinton (Dem) and Donald Trump (Rep). This strategy also ignores votes cast for independent or write in candidates in the presidential election, thereby not assigning them to a congressional vote party (which would admittedly, be quite difficult), as well as independent or write in candidates in congressional elections, who get no votes attributed to them because of the simplified two party model. However, for the purposes of teaching GIS to beginning researchers, this is a logical simplification. One way to investigate this threat to validity might be to compare the predicted party winner in each district with the party of the serving Congressmember. However, this will not be undertaken in this replication study. 
    2. *We are assuming that voters are evenly distributed throughout voting precincts.*
    The original study uses area-weighted re-aggregation to assign votes cast in presidential voting precincts to congressional districts based on the percentage of precinct area contained by a given congressional district. This assumes that voters for both parties are evenly distributed throughout the precincts. However, there are multiple possible scenarios in which this would not be the case. For example, the distribution of votes for each party may be evenly distributed throughout the voting population in a given precinct, while the population itself may not be evenly distributed spatially. This could result in the assignment of votes cast in one district to a neighboring district in the same precinct, thereby inflating the vote count in one and decreasing it in another. Depending on the makeup of the voters, this could change the make-up of the voter base in effected districts. Similarly, the opposite scenario could be true: voters might be evenly distributed spatially in the precinct, but their votes aren't. For example, there might be a precinct with a very democratic area and a very republican area. The methodology used in this paper would blend these two areas together and proportionally assign partisan voters to congressional district, which also runs the risk of changing the voter composition in effected districts. And the two are not mutually exclusive. Voters may be unevenly distributed both spatially and politically. In fact, this might be the most likely scenario, as democratic voters tend to be clustered in cities and republican voters in more rural areas. 
    Area weighted reaggregation already aims to address the modifiable areal unit problem, where the scale of analysis significantly influences the results. However, it is an imperfect method. One way to improve this analysis further might be to create a population gradient based on census block or block group population data such that a population based weighted re-aggregation might be implemented. However, this improvement would only be able to address the uneven spatial distribution of voters and not the uneven political distribution. Even if this population gradient was not used to make an alternate weighted re-aggregation, it might be useful in at least identifying congressional districts that may have been effected by this threat to validity. However, this methodological change will not be implemented in this reproduction study. 
    3. *Additionally (not originally stated), using a compactness score as a proxy for electoral fairness may be impacted by boundary effects.*
    Compactness scores in general compare the perimeter of a given polygon to its area. The formula used in the original study essentially compares the district to how circular it is, such that a very circular district would be considered the most fair. Identifying gerrymandering is, as exemplified by the countless courtcases and ongoing discourse, an inherently difficult thing to define. So, the measure of compactness begs the question, what is the geometry of the ideal district? Whatever the answer to that question, measures of compactness are designed to flag districts with long, snaky, or complex borders. However, this means they may also flag otherwise 'compact' districts that have complex borders due to geographic features such as coastlines, islands, or rivers. In this case, the complexity of the border is not indicative of gerrymandering per se, but merely the physical reality of the landscape. Some congressional maps may be drawn with borders that extend into the sea, for example, and are thus more simple than if they hugged the coastline, but this varies by map and is not always possible. 
    *** picking up here -> anything done to mitigate this?
    *** also the failure to pick up cracking v packing
    
    
These include:
  - uneven primary data collection due to geographic inaccessibility or other constraints
  - multiple hypothesis testing
  - edge or boundary effects
  - the modifiable areal unit problem
  - nonstationarity
  - spatial dependence or autocorrelation
  - temporal dependence or autocorrelation
  - spatial scale dependency
  - spatial anisotropies
  - confusion of spatial and a-spatial causation
  - ecological fallacy
  - uncertainty e.g. from spatial disaggregation, anonymization, differential privacy

### Data transformations

Describe all data transformations planned to prepare data sources for analysis.
This section should explain with the fullest detail possible how to transform data from the **raw** state at the time of acquisition or observation, to the pre-processed **derived** state ready for the main analysis.
Including steps to check and mitigate sources of **bias** and **threats to validity**.
The method may anticipate **contingencies**, e.g. tests for normality and alternative decisions to make based on the results of the test.
More specifically, all the **geographic** and **variable** transformations required to prepare input data as described in the data and variables section above to match the study's spatio-temporal characteristics as described in the study metadata and study design sections.
Visual workflow diagrams may help communicate the methodology in this section.

Examples of **geographic** transformations include coordinate system transformations, aggregation, disaggregation, spatial interpolation, distance calculations, zonal statistics, etc.

Examples of **variable** transformations include standardization, normalization, constructed variables, imputation, classification, etc.

Be sure to include any steps planned to **exclude** observations with *missing* or *outlier* data, to **group** observations by *attribute* or *geographic* criteria, or to **impute** missing data or apply spatial or temporal **interpolation**.

### Analysis

Describe the methods of analysis that will directly test the hypotheses or provide results to answer the research questions.
This section should explicitly define any spatial / statistical *models* and their *parameters*, including *grouping* criteria, *weighting* criteria, and *significance thresholds*.
Also explain any follow-up analyses or validations.

## Results

Describe how results are to be presented.

## Discussion

Describe how the results are to be interpreted *vis a vis* each hypothesis or research question.

## Integrity Statement

Include an integrity statement - The authors of this preregistration state that they completed this preregistration to the best of their knowledge and that no other preregistration exists pertaining to the same hypotheses and research.
If a prior registration *does* exist, explain the rationale for revising the registration here.

## Acknowledgements

- `Funding Name`: name of funding for the project
- `Funding Title`: title of project grant
- `Award info URI`: web address for award information
- `Award number`: award number

This report is based upon the template for Reproducible and Replicable Research in Human-Environment and Geographical Sciences, DOI:[10.17605/OSF.IO/W29MQ](https://doi.org/10.17605/OSF.IO/W29MQ)

## References
