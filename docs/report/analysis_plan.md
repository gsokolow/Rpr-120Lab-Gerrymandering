# Title of Study

### Authors

- Grace Sokolow\*, gsokolow@middlebury.edu, @gsokolow, Middlebury College (Undergraduate)

\* Corresponding author and creator

## Abstract

This study is a *replication* of:

> Kimambo, Niwaeli. 2021. *Lec/Lab: Gerrymandering: Maps and political representation* Human Geography with GIS (GEOG 120) at Middlebury College.

The original lab aims to determine whether North Carolina's 2019 congressional districts, which were redrawn by court order, are fairer than the 2016 districts based on geographic compactness and political representation.
First, votes cast in the 2016 presidential election are used to estimate the percentage of Republican voters in the 2016 and 2019 congressional districts.
Then, compactness scores are calculated by multiplying the area by 400π and dividing by the perimeter squared.
The deliverables include summary statistics for the compactness and percentage of Republicans from the 2026 and 2019 districts, as well as 4 maps: 
percentage votes for Republican presidential candidate by voting precinct, percentage votes for the 2016 Republican presidential candidate by 2016 districts, percentage of votes for the 2016 Republican presidential candidate by 2019 districts, and the compactness scores for each 2016 and 2019 district.

This replication shifts the computational environment from QGIS to Python. Several data layers are provided for the original lab, including the 2016 and 2019 congressional district maps and the 2016 North Carolina voting precints and presidential election data. This study uses the originally given data layers. A next step for a reanalysis of this study would be to pull in the data directly from the original sources, but this is outside the scope of this replication study.


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

This study is a **reproduction** of Kimambo's 2021 lab. No changes are planned to the mothodology of the original lab; only the computational environment is different.

Kimambo's original lab is an observational study of partisan gerrymandering in North Carolina. It aims to determine if the court-ordered redistricting of North Carolina's 2016 districts resulted in districts that were more fair in terms of geographic compactness and political representation. An area weighted reaggregation is used to allocate votes for the Republican presidential candidate in 2016 to North Carolina's 2016 and 2019 congressonal districts. To calculate compactness for each district, the following equation is used: compactness = 400 * π * area / perimeter^2.

## Materials and procedure

N/A

### Computational environment

This reproduction study uses Python 3.11.5. 
All imported packages and versions can be found under /procedure/environment/requirements.txt.

### Data and variables

The original data made available for the lab in 2021 is stored under data/raw/public and will be used for the replication. 

### Secondary Data Sources

### Raw Data
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
- `Distribution`: Retrieved from the North Carolina State Board of Elections; [precinct shapefiles](https://www.ncsbe.gov/results-data/voting-maps-redistricting) at Geospatial Files > Precinct Files > Precinct Shapefiles (folder) > SBE_PRECINCTS_20161004.zip; [tabular voting results](https://er.ncsbe.gov/downloads.html) under 11/08/2016 > Precinct Election Results *cannot be downloaded security
- `Constraints`: Legal constraints for *access* or *use* to protect *privacy* or *intellectual property rights*: N/A
- `Data Quality`: Quality unknown
- `Variables`:

| Label | Alias | Definition | Type | Accuracy | Domain | Missing Data Value(s) | Missing Data Frequency |
| :--: | :--: | :--: | :--: | :--: | :--: | :--: | :--: |
| PREC_ID | Precinct_ID | precinct id| object | N/A | N/A | N/A | N/A |
| COUNTY_NAM | county name | precinct county name | object | N/A | N/A | N/A | N/A |
| dem | democratic votes | votes for Democratic Party candidate in 2016 presidential election | int64 | N/A | 1, 4979 | N/A | N/A |
| rep | republican votes | votes for Republican Party candidate in 2016 presidential election | int64 | N/A | 2, 4808 | N/A | N/A |
| cntyprec | unique precinct identifier | concatenation of county name and precinct id | object | N/A | N/A | N/A | N/A |

#### 07_Lab07_PartisanGerrymandering.pdf
- `Abstract`: Solution summary statistics for the original lab: minimum, mean, maximum compactness scores and percentage Republican votes in 2016 and 2019 
- `Spatial Coverage`: North Carolina, USA
- `Spatial Resolution`: U.S. Congressional Districts
- `Spatial Reference System`: N/A
- `Temporal Coverage`: Two election cycles; 2016 & 2019
- `Temporal Resolution`: 2016; 2019
- `Lineage`: Retrieved from the 2021 Fall GEOG 120 Human Geography with GIS Canvas page (and the author's personal files); Distributed by Professor Niwaeli Kimambo. Entered by hand in analysis code. 
- `Distribution`: Retrieved from the 2021 Fall GEOG 120 Human Geography with GIS Canvas page (not open to the public).
- `Constraints`: Legal constraints for *access* or *use* to protect *privacy* or *intellectual property rights*: N/A
- `Data Quality`: Quality unknown
- `Variables`:
  | Label | Alias | Definition | Type | Accuracy | Domain | Missing Data Value(s) | Missing Data Frequency |
| :--: | :--: | :--: | :--: | :--: | :--: | :--: | :--: |
| N/A | Minimum compactness score 2016 | minimum compactness score from 2016 districts | N/A | 0.01 | N/A | N/A | N/A |
| N/A | Minimum compactness score 2019 | minimum compactness score from 2019 districts | N/A | 0.01 | N/A | N/A | N/A |
| N/A | Mean compactness score 2016 | mean compactness score from 2016 districts | N/A | 0.01 | N/A | N/A | N/A |
| N/A | Mean compactness score 2019 | mean compactness score from 2019 districts | N/A | 0.01 | N/A | N/A | N/A |
| N/A | Maximum compactness score 2016 | maximum compactness score from 2016 districts | N/A | 0.01 | N/A | N/A | N/A |
| N/A | Maximum compactness score 2019 | maximum compactness score from 2019 districts | N/A | 0.01 | N/A | N/A | N/A |
| N/A | Minimum percent Republican 2016 | minimum percent Republican votes in 2016 districts | N/A | 0.01 | N/A | N/A | N/A |
| N/A | Minimum percent Republican 2019 | minimum percent Republican votes in 2019 districts | N/A | 0.01 | N/A | N/A | N/A |
| N/A | Mean percent Republican 2016 | mean percent Republican votes in 2016 districts | N/A | 0.01 | N/A | N/A | N/A |
| N/A | Mean percent Republican 2019 | mean percent Republican votes in 2019 districts | N/A | 0.01 | N/A | N/A | N/A |
| N/A | Maximum percent Republican 2016 | maximum percent Republican votes in 2016 districts | N/A | 0.01 | N/A | N/A | N/A |
| N/A | Maximum percent Republican 2019 | maximum percent Republican votes in 2019 districts | N/A | 0.01 | N/A | N/A | N/A |


### Generated final files

#### D_awr_2016.shp
**Unplanned deviation from analysis plan** Fields made meaningless by geometric transformation were dropped before export. These fields have been strike-throughed.
- `Abstract`: Area weighted reaggregation of 2016 presidential votes in North Carolina's U.S. Congressional Districts in 2016 with geometry, predicted election results, and compactness scores
- `Spatial Coverage`: North Carolina, USA
- `Spatial Resolution`: U.S. Congressional Districts
- `Spatial Reference System`: 32119 NAD 1983 North Carolina
- `Temporal Coverage`: One election cycle
- `Temporal Resolution`: 2016
- `Lineage`: Constructed from data transformations of 2016_Contingent_Congressional_Plan_Corrected.shp and precincts.shp. Constructed variables: pctDRep, dPerim, dArea, dCompact
- `Distribution`: Created during analysis
- `Constraints`: Legal constraints for *access* or *use* to protect *privacy* or *intellectual property rights*: N/A
- `Data Quality`: Quality unknown
- `Variables`: 
  | Label | Alias | Definition | Type | Accuracy | Domain | Missing Data Value(s) | Missing Data Frequency |
| :--: | :--: | :--: | :--: | :--: | :--: | :--: | :--: |
~~| PREC_ID | Precinct_ID | precinct id| object | N/A | N/A | N/A | N/A |
| COUNTY_NAM | county name | precinct county name | object | N/A | N/A | N/A | N/A |
| dem | democratic votes | votes for Democratic Party candidate in 2016 presidential election | int64 | N/A | 1, 4979 | N/A | N/A |
| rep | republican votes | votes for Republican Party candidate in 2016 presidential election | int64 | N/A | 2, 4808 | N/A | N/A |
| cntyprec | unique precinct identifier | concatenation of county name and precinct id | object | N/A | N/A | N/A | N/A |~~
| District | U.S. Congressional District | unique district number | int64 | N/A | 1, 13 | N/A | N/A |
~~| pArea | precinct area | geodesic precinct area | float64 | N/A | not yet known | N/A | N/A |
| pctRep | percent republican votes | percent of votes for the 2016 republican presidential candidate, by precinct | int64 | N/A | not yet known | N/A | N/A |
| fArea | fragment area | geodesic fragment area | float64 | N/A | not yet known | N/A | N/A |
| aw | area weight | percentage of precinct contained by fragment  | float64 | N/A | not yet known | N/A | N/A |~~
| awDem | area weighted democratic votes | number of votes for the 2016 democratic presidential candidate allocated to fragment | float64 | N/A | not yet known | N/A | N/A |
| awRep | area weighted republican votes | number of votes for the 2016 republican presidential candidate allocated to fragment | float64 | N/A | not yet known | N/A | N/A |
| pctDRep | percentage of republican votes by district | percentage of votes for the 2016 republican presidential candidate in each district | float64 | N/A | not yet known | N/A | N/A |
| dPerim | district perimeter | planimetric district perimeter | float64 | N/A | not yet known | N/A | N/A |
| dArea | district area | planimetric district perimeter | float64 | N/A | not yet known | N/A | N/A |
| dCompact | district compactness score | district compactness score = (400*π*dArea)/(dPerim^2) | float64 | N/A | not yet known | N/A | N/A |


#### D_awr_2019.shp
**Unplanned deviation from analysis plan** Fields made meaningless by geometric transformation were dropped before export. These fields have been strike-throughed.
- `Abstract`: Area weighted reaggregation of 2019 presidential votes in North Carolina's U.S. Congressional Districts in 2019 with geometry, predicted election results, and compactness scores
- `Spatial Coverage`: North Carolina, USA
- `Spatial Resolution`: U.S. Congressional Districts
- `Spatial Reference System`: 32119 NAD 1983 North Carolina
- `Temporal Coverage`: One election cycle
- `Temporal Resolution`: 2019
- `Lineage`: Constructed from data transformations of C-Goodwin-A-1-TC.shp and precincts.shp. Constructed variables: pctDRep, dPerim, dArea, dCompact
- `Distribution`: Created during analysis
- `Constraints`: Legal constraints for *access* or *use* to protect *privacy* or *intellectual property rights*: N/A
- `Data Quality`: Quality unknown
- `Variables`: 
  | Label | Alias | Definition | Type | Accuracy | Domain | Missing Data Value(s) | Missing Data Frequency |
| :--: | :--: | :--: | :--: | :--: | :--: | :--: | :--: |
~~| PREC_ID | Precinct_ID | precinct id| object | N/A | N/A | N/A | N/A |
| COUNTY_NAM | county name | precinct county name | object | N/A | N/A | N/A | N/A |
| dem | democratic votes | votes for Democratic Party candidate in 2019 presidential election | int64 | N/A | 1, 4979 | N/A | N/A |
| rep | republican votes | votes for Republican Party candidate in 2019 presidential election | int64 | N/A | 2, 4808 | N/A | N/A |
| cntyprec | unique precinct identifier | concatenation of county name and precinct id | object | N/A | N/A | N/A | N/A |~~
| District | U.S. Congressional District | unique district number | int64 | N/A | 1, 13 | N/A | N/A |
~~| pArea | precinct area | geodesic precinct area | float64 | N/A | not yet known | N/A | N/A |
| pctRep | percent republican votes | percent of votes for the 2019 republican presidential candidate, by precinct | int64 | N/A | not yet known | N/A | N/A |
| fArea | fragment area | geodesic fragment area | float64 | N/A | not yet known | N/A | N/A |
| aw | area weight | percentage of precinct contained by fragment  | float64 | N/A | not yet known | N/A | N/A |~~
| awDem | area weighted democratic votes | number of votes for the 2019 democratic presidential candidate allocated to fragment | float64 | N/A | not yet known | N/A | N/A |
| awRep | area weighted republican votes | number of votes for the 2019 republican presidential candidate allocated to fragment | float64 | N/A | not yet known | N/A | N/A |
| pctDRep | percentage of republican votes by district | percentage of votes for the 2019 republican presidential candidate in each district | float64 | N/A | not yet known | N/A | N/A |
| dPerim | district perimeter | planimetric district perimeter | float64 | N/A | not yet known | N/A | N/A |
| dArea | district area | planimetric district perimeter | float64 | N/A | not yet known | N/A | N/A |
| dCompact | district compactness score | district compactness score = (400*π*dArea)/(dPerim^2) | float64 | N/A | not yet known | N/A | N/A |

#### replication_sstats.xlsx
- `Abstract`: Summary statistics generated during analysis: minimum, mean, maximum compactness scores and percentage Republican votes in 2016 and 2019 
- `Spatial Coverage`: North Carolina, USA
- `Spatial Resolution`: U.S. Congressional Districts
- `Spatial Reference System`: N/A
- `Temporal Coverage`: Two election cycles; 2016 & 2019
- `Temporal Resolution`: 2016; 2019
- `Lineage`: Constructed from data transformations of 2016_Contingent_Congressional_Plan_Corrected.shp, C-Goodwin-A-1-TC.shp and precincts.shp. 
- `Distribution`: Created during analysis
- `Constraints`: Legal constraints for *access* or *use* to protect *privacy* or *intellectual property rights*: N/A
- `Data Quality`: Quality unknown
- `Variables`:
  | Label | Alias | Definition | Type | Accuracy | Domain | Missing Data Value(s) | Missing Data Frequency |
| :--: | :--: | :--: | :--: | :--: | :--: | :--: | :--: |
| N/A | Minimum compactness score 2016 | minimum compactness score from 2016 districts | N/A | N/A | N/A | N/A | N/A |
| N/A | Minimum compactness score 2019 | minimum compactness score from 2019 districts | N/A | N/A | N/A | N/A | N/A |
| N/A | Mean compactness score 2016 | mean compactness score from 2016 districts | N/A | N/A | N/A | N/A | N/A |
| N/A | Mean compactness score 2019 | mean compactness score from 2019 districts | N/A | N/A | N/A | N/A | N/A |
| N/A | Maximum compactness score 2016 | maximum compactness score from 2016 districts | N/A | N/A | N/A | N/A | N/A |
| N/A | Maximum compactness score 2019 | maximum compactness score from 2019 districts | N/A | N/A | N/A | N/A | N/A |
| N/A | Minimum percent Republican 2016 | minimum percent Republican votes in 2016 districts | N/A | 0.01 | N/A | N/A | N/A |
| N/A | Minimum percent Republican 2019 | minimum percent Republican votes in 2019 districts | N/A | 0.01 | N/A | N/A | N/A |
| N/A | Mean percent Republican 2016 | mean percent Republican votes in 2016 districts | N/A | N/A | N/A | N/A | N/A |
| N/A | Mean percent Republican 2019 | mean percent Republican votes in 2019 districts | N/A | N/A | N/A | N/A | N/A |
| N/A | Maximum percent Republican 2016 | maximum percent Republican votes in 2016 districts | N/A | N/A | N/A | N/A | N/A |
| N/A | Maximum percent Republican 2019 | maximum percent Republican votes in 2019 districts | N/A | N/A | N/A | N/A | N/A |



### Prior observations  

Prior experience with the study area, prior data collection, or prior observation of the data can compromise the validity of a study, e.g. through p-hacking.
Therefore, disclose any prior experience or observations at the time of study pre-registration here, with example text below:

At the time of this study pre-registration, the author had prior experience with this data having worked through the original lab problem as a student in 2021. From the onset of this analsysis, the author has had access to the original lab results. During the summer of 2022, the author was a participant at the Spatial Modeling of Electoral Redistricting REU at the University of Puget Sound, where she studied gerrymandering and worked closely with spatial measures including but not limited to compactness scores. The study area for that reseatch was the entire United States and thus included North Carolina. 



For each secondary source, declare the extent to which authors had already engaged with the data:

For the three given datasets (2016_Contingent_Congressional_Plan_Corrected.shp; C-Goodwin-A-1-TC.shp; precincts.shp), the author has observed the full dataset through the original completion of the lab in fall 2021. 

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
    Compactness scores in general compare the perimeter of a given polygon to its area. The formula used in the original study essentially compares the district to how circular it is, such that a very circular district would be considered the most fair. Identifying gerrymandering is, as exemplified by numerous courtcases and an ongoing discourse about it, an inherently difficult thing to define. So, the measure of compactness begs the question, what is the geometry of the ideal district? Whatever the answer to that question, measures of compactness are designed to flag districts with long, snaky, or complex borders. However, this means they may also flag otherwise 'compact' districts that have complex borders due to geographic features such as coastlines, islands, or rivers. In this case, the complexity of the border is not indicative of gerrymandering per se, but merely the physical reality of the landscape. Some congressional maps may be drawn with borders that extend into the sea, for example, and are thus more simple than if they hugged the coastline, but this varies by map and is not always possible. Districts flagged for being potentially gerrymandered on the basis of compactness score could be inspected by hand to determine what if any portion of the non-compactness may be attributable to an acceptable level of complexity due to physical geography. This is not a part of the existing methodology and regardless, is a sub-optimal solution to this issue. 
    4. *Theoretical grounds for a compactness score (not originally stated)*
    Compactness scores in general pose a threat to the validity of gerrymandering research in that they are better at identifying packing as opposed to cracking. Packing occurs when a district is drawn such that a particular group of voters (be it based on race, partisanship, or another factor) is selected for inclusion in a district. This may contribute to the creation of a district that is not compact. Packing thus crams potential voting blocs into one district so that the selected group can exert influence over fewer districts. Conversely, cracking occurs when a district is drawn such that a geographically compact area or contiguous spatial grouping of a particular group of voters is divided into multiple districts. Cracked districts may or may not be compact, thus making them harder for a compactness score to identify. Cracking results in the dilution of the group's voting power; where they may have been the majority group if placed in one district, they are now the minority group in several different districts. Just like packing, cracking reduces the number of seats a particular voting group is likely to win; each type of gerrymandering just uses a different strategy. Compactness scores
    5. *We are assumming that a more circular district would be more fair (not originally stated)*
    By using compactness to identify potential gerrymanders, we run the risk of false positives: districts idendified as having a compactness score indicative of gerrymandering, when their may not be an observable difference in voter makeup whether the district is more compact or not. This is one manifestation of an edge effect; in which the state of the region bordering the study region influences the results attributed to that reason. Joe Holler, Assistant Professor of Geography at Middlebury College, has suggested that the area weighted reaggregation of voters from the 2016 presidential election to the 2016 and 2019 congressional districts could be expanded so that in addition to calculating the likely voter base in each district, one would also calculate the likely voter base in the 'minimum bounding circle' of each district from each year. Comparing the predicted election results for congressional districts with the predicted election results of the corresponding minimum bounding circle would help identify the districts in which compactness is a driving factor of election results (and thus a stronger indicator of a potential gerrymander). This additional analysis could help identify both instances of packing and cracking, though it is outside the scope of this reproduction study.
    
    
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

Steps are based on my personal original solution to this lab from Fall 2021. Note that they are presented in terms of QGIS but the python equivalent will can be found in 01-Jupyter_notebook.ipynb. 

First, I will rename 2016_Contingent_Congressional_Plan_Corrected.shp to cd_2016 and C-Goodwin-A-1-TC.shp to cd_2019 for clarity. Precincts.shp will become pc2016. 
**Deviation from analysis plan:** Not every variable name outlined here is used in the analysis, but changes are explianed in the code. This is for clarity and efficiency's sake.

#### 2016 Districts
1. **geographic** Reproject precincts dataset to CRS: 32119 NAD 1983 North Carolina -> precincts_nad
2. **geographic** Fix precinct_nad geometries -> precincts_fix
3. **variable** New field pArea (*type: float64*\*): Calculate goedsic/ellipsoidal area of geometry in precincts_fix (as opposed to based on the CRS; see [QGIS helpdocs](https://gis.stackexchange.com/questions/347249/using-area-or-area-function-in-qgis-when-the-data-polygon-is-stored-in-utm) for more info on $area v area(); in this case, $area used) -> precincts_area
4. **variable** New field pctRep (*type: float64*\*) : Calculate the percentage of votes cast in each precinct for the republican presidential candidate in 2016 -> precincts_area (variable name can stay the same; just adding a field)
**Deviation from analysis plan** pctDRep must be multiplied by 100 to output a percent rather than a proportion.
5. **geographic** Union: input = precincts_area; overlay = cd_2016 -> frag_2016
**Deviation from analysis plan**: Running a union between 2016 precincts and 2016 congressional districts ran successfully, but took an unusually long time (~10 mins). Substituting an intersection for a union is faster and maintains the desired output: a union generates all possible combinations of precincts not overlapped by districts, districts not overlapped by precincts, and district precinct overlaps. The area-weighted reaggregation is based solely on the transfer of data via an overlap, so the difference between a union and intersection is negligible in this case.
6. **variable** New field fArea (*type: float64*\*): Calculate goedsic/ellipsoidal area of geometry in frag_2016
7. **variable** New field aw (*type: float64*\*): For each fragment (precinct + district combination), calculate the proportion of the precinct contained by the fragment (this determines the proportion of precinct votes allocated to each fragment) = 'fArea'/'pArea' -> frag_2016 (variable name can stay the same, as we are just adding new fields)
8. **variable** New field awDem (*type: float64*\*): Calculate the proportion of democratic votes (from the precinct) to be allocated to each fragment = 'dem' * 'aw' -> frag_2016
9. **variable** New field awRep (*type: float64*\*): Calculate the proportion of republican votes (from the precinct) to be allocated to each fragement = 'rep' * 'aw' -> frag_2016
10. **group by attribute** Group frag_2016 by 'District'; summary fields: 'awDem', 'awRep'; do not dissolve geometry -> grouped_districts_2016
**Deviation from analysis plan:** The type of summary for the group by was not specified, but sum is the correct operation to add the weighted number of voters in each district together.
11. **join by attribute** grouped_districts_2016.xlsx (input layer 2) to cd_2016 (input layer 1) on 'District' (table field); copy 'sumawDem' and 'sumawRep' -> D_awr_2016
12. **variable** New field pctDRep (*type: float64*\*): Calculate the percentage of republican votes in each district = 'sumawrep' / ('sumawRep + 'sumawDem') -> D_awr_2016
13. **variable** New field dPerim (*type: float64*\*): Calculate the planimetric perimeter of the district (based on the projection; perim($geom)) -> D_awr_2016
14. **variable** New field dArea (*type: float64*\*): Calculate the planimetric area of the district (based on the projection; area($geom)) -> D_awr_2016
15. **variable** New field dCompact (*type: float64*\*): Calculate compactness using the equation given in the lab = (400 * π * 'dArea')/(dPerim^2) -> **Export as D_awr_2016.shp**
16. **variable** Create new dataframe -> summary_stats
17. **variable** New variable s2016_pct_min (*type: float64*\*): Calculate the minimum percentage of Republican votes in 2016 Districts (using D_awr_2016) -> summary_stats
**Deviation from analysis plan** pctDRep must be multiplied by 100 to output a percent rather than a proportion.
18. **variable** New variable s2016_pct_mean (*type: float64*\*): Calculate the mean percentage of Republican votes in 2016 Districts (using D_awr_2016) -> summary_stats
19. **variable** New variable s2016_pct_max (*type: float64*\*): Calculate the maximum percentage of Republican votes in 2016 Districts (using D_awr_2016) -> summary_stats
20. **variable** New variable s2016_compactness_min (*type: float64*\*): Calculate the minimum compactness score for 2016 Districts (using D_awr_2016) -> summary_stats
21. **variable** New variable s2016_compactness_mean (*type: float64*\*): Calculate the mean compactness score for 2016 Districts (using D_awr_2016) -> summary_stats
22. **variable** New variable s2016_compactness_max (*type: float64*\*): Calculate the maximum compactness score for 2016 Districts (using D_awr_2016) -> summary_stats

#### 2019 Districts
1. **geographic** Union: input = precincts_area; overlay = cd_2019 -> frag_2019 (note that precincts_area is created in steps 1-4 in 2016 District transformations and does not change across years)
**Unplanned Deviation in Analysis**: Running a union between 2016 precincts and 2019 congressional districts resulted in a GEOSDifference error where 2 linestrings overlapped without a coordinate point between districts 4 and 8. Substituting an intersection for a union works around this issue because a union generates all possible combinations of precincts not overlapped by districts, districts not overlapped by precincts, and district precinct overlaps. The area-weighted reaggregation is based solely on the transfer of data via an overlap, so the difference between a union and intersection is negligible in this case. The intersection runs much faster then the union, but will still be saved as a separate file: export as Intersection_2016_precincts_2019_districts.shp and read back in.
2. **variable** New field fArea (*type: float64*\*): Calculate goedsic/ellipsoidal area of geometry in frag_2019
3. **variable** New field aw (*type: float64*\*): For each fragment (precinct + district combination), calculate the proportion of the precinct contained by the fragment (this determines the proportion of precinct votes allocated to each fragment) = 'fArea'/'pArea' -> frag_2019 (variable name can stay the same, as we are just adding new fields)
4. **variable** New field awDem (*type: float64*\*): Calculate the proportion of democratic votes (from the precinct) to be allocated to each fragment = 'dem' * 'aw' -> frag_2019
5. **variable** New field awRep (*type: float64*\*): Calculate the proportion of republican votes (from the precinct) to be allocated to each fragement = 'rep' * 'aw' -> frag_2019
6. **group by attribute** Group frag_2019 by 'District'; summary fields: 'awDem', 'awRep'; do not dissolve geometry -> grouped_districts_2019
**Deviation from analysis plan:** The type of summary for the group by was not specified, but sum is the correct operation to add the weighted number of voters in each district together.
7. **join by attribute** Join grouped_districts_2019 (input layer 2) to cd_2019 (input layer 1) on 'DISTRICT' (table field); copy 'sumawDem' and 'sumawRep' -> D_awr_2019
8. **variable** New field pctDRep (*type: float64*\*): Calculate the percentage of republican votes in each district = 'sumawrep' / ('sumawRep + 'sumawDem') -> D_awr_2016
9. **variable** New field dPerim (*type: float64*\*): Calculate the planimetric perimeter of the district (based on the projection; perim($geom)) -> D_awr_2019
10. **variable** New field dArea (*type: float64*\*): Calculate the planimetric area of the district (based on the projection; area($geom)) -> D_awr_2019
11. **variable** New field dCompact (*type: float64*\*): Calculate compactness using the equation given in the lab = (400 * π * 'dArea')/(dPerim^2) -> **Export as D_awr_2019.shp**
12. **variable** Create new dataframe -> summary_stats
13. **variable** New variable s2019_pct_min (*type: float64*\*): Calculate the minimum percentage of Republican votes in 2019 Districts (using D_awr_2019) -> summary_stats
**Deviation from analysis plan** pctDRep must be multiplied by 100 to output a percent rather than a proportion.
14. **variable** New variable s2019_pct_mean (*type: float64*\*): Calculate the mean percentage of Republican votes in 2019 Districts (using D_awr_2019) -> summary_stats
15. **variable** New variable s2019_pct_max (*type: float64*\*): Calculate the maximum percentage of Republican votes in 2019 Districts (using D_awr_2019) -> summary_stats
16. **variable** New variable s2019_compactness_min (*type: float64*\*): Calculate the minimum compactness score for 2019 Districts (using D_awr_2019) -> summary_stats
17. **variable** New variable s2019_compactness_mean (*type: float64*\*): Calculate the mean compactness score for 2019 Districts (using D_awr_2019) -> summary_stats
18. **variable** New variable s2019_compactness_max (*type: float64*\*): Calculate the maximum compactness score for 2019 Districts (using D_awr_2019) -> **Export as replication_sstats.xlsx**

#### Comparative Analysis
1. **variable** New data frame original_sstats; populate with minimum, mean, and maximum compactness score and percentage of Republican votes assigned to each district in 2016 and 2019 from 07_Lab07_PartisanGerrymandering.pdf
2. **variable** New data frame agreement (*type: float64*): Subtract original_sstats from replication_sstats.xlsx (rounded to three decimal points) and take the absolute value -> agreement


\* **Deviation from original study:** that the original form of area field was decimal with unspecified precision; the aw field has a specified precision of 6. By default, geopandas' area calculator works in float 64 and that is what is used in this analysis.

### Analysis
Hypothesis 1. *There is no difference between the compactness scores and percent of Republican votes generated for each Congressional district in 2016 and 2019 in this analysis as compared to the original lab handout (see docs/07_Lab07_partisanGerrymandering.pdf).*

If the summary stats generated by this analysis do not agree with the original summary stats given, the null hypothesis will be rejected. If the summary stats do agree, the null hypothesis will not be rejected.


## Results
#### Hypothesis 1
Agreement between the original summary stats and the replication summary stats will be presented in a table. Additionally, I will visualize the data in a series of 5 maps using the same classification breaks and divergent color scheme (centered on 50%) as required in the original lab.
*note:* the original lab requested: "compactness of each 2016 and 2019 district" as one map, which I interpret as two separate maps for the purposes of this replication:
1. percentage of votes for 2016 Republican presidential candidate by voting precinct
2. percentage of votes for 2016 Republican presidential candidate by 2016 Districts
3. percentage of votes for 2016 Republican presidential candidate by 2019 Districts
4. compactness of 2016 districts
5. compactness of 2019 districts
**Deviation from analysis plan:** A new classification method and color scheme are used for the two compactness maps because the numeric values are scores that only have meaning relative to eachother, as opposed to the percentage of republican votes, which translates more concretely to real world conditions. A Jenks classification scheme helps to visualize the uneven distribution of compactness scores.

However, the author no longer has access to the maps she made in Fall 2021, so these visualizations will serve to further investigate and communicate the data rather than serve as a direct comparison with the original results.

## Discussion

If the null hypothesis is rejected, it suggests that the original lab could benefit from a more robust documentation of its solution. However, depending on the magnitude of the difference, a rejection of the null hypothesis could be indicative of an inequivalency between a python command used and the original tool intended for use in QGIS.

## Integrity Statement

Include an integrity statement - The authors of this preregistration state that they completed this preregistration to the best of their knowledge and that no other preregistration exists pertaining to the same hypotheses and research.
If a prior registration *does* exist, explain the rationale for revising the registration here.

## Acknowledgements

- `Funding Name`: N/A
- `Funding Title`: N/A
- `Award info URI`: N/A
- `Award number`: N/A

This report is based upon the template for Reproducible and Replicable Research in Human-Environment and Geographical Sciences, DOI:[10.17605/OSF.IO/W29MQ](https://doi.org/10.17605/OSF.IO/W29MQ)

## References
