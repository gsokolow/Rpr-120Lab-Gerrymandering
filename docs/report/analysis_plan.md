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

Describe the **data sources** and **variables** to be used.
Data sources may include plans for observing and recording **primary data** or descriptions of **secondary data**.
For secondary data sources with numerous variables, the analysis plan authors may focus on documenting only the variables intended for use in the study.

Primary data sources for the study are to include ... .
Secondary data sources for the study are to include ... .

Each of the next subsections describes one data source.

#### Primary data source1 name

**Standard Metadata**

- `Abstract`: Brief description of the data source
- `Spatial Coverage`: Specify the geographic extent of your study. This may be a place name and link to a feature in a gazetteer like GeoNames or OpenStreetMap, or a well known text (WKT) representation of a bounding box.
- `Spatial Resolution`: Specify the spatial resolution as a scale factor, description of the level of detail of each unit of observation (including administrative level of administrative areas), and/or or distance of a raster GRID size
- `Spatial Reference System`: Specify the geographic or projected coordinate system for the study
- `Temporal Coverage`: Specify the temporal extent of your study---i.e. the range of time represented by the data observations.
- `Temporal Resolution`: Specify the temporal resolution of your study---i.e. the duration of time for which each observation represents or the revisit period for repeated observations
- `Lineage`: Describe and/or cite data sources and/or methodological steps planned to create this data source.
  - sampling scheme, including spatial sampling
  - target sample size and method for determining sample size
  - stopping criteria for data collection and sampling (e.g. sample size, time elapsed)
  - de-identification / anonymization
  - experimental manipulation
- `Distribution`: Describe who will make the data available and how?
- `Constraints`: Legal constraints for *access* or *use* to protect *privacy* or *intellectual property rights*
- `Data Quality`: State any planned quality assessment
- `Variables`: For each variable, enter the following information. If you have two or more variables per data source, you may want to present this information in table form (shown below)
  - `Label`: variable name as used in the data or code
  - `Alias`: intuitive natural language name
  - `Definition`: Short description or definition of the variable. Include measurement units in description.
  - `Type`: data type, e.g. character string, integer, real
  - `Accuracy`: e.g. uncertainty of measurements
  - `Domain`: Expected range of Maximum and Minimum of numerical data, or codes or categories of nominal data, or reference to a standard codebook
  - `Missing Data Value(s)`: Values used to represent missing data and frequency of missing data observations
  - `Missing Data Frequency`: Frequency of missing data observations: not yet known for data to be collected

| Label | Alias | Definition | Type | Accuracy | Domain | Missing Data Value(s) | Missing Data Frequency |
| :--: | :--: | :--: | :--: | :--: | :--: | :--: | :--: |
| variable1 | ... | ... | ... | ... | ... | ... | ... |
| variable2 | ... | ... | ... | ... | ... | ... | ... |

#### Primary data source2 name

... same form as above...

#### 2016_Contingent_Congressional_Plan_Corrected

**Standard Metadata**

- `Abstract`: North Carolina Legislature's version of U.S. Congressional Districts in 2016. These districts were drawn after the Supreme Court found their 2011 districts to be an illegal racial gerrymander. 
- `Spatial Coverage`: North Carolina, USA
- `Spatial Resolution`: U.S. Congressional Districts
- `Spatial Reference System`: 32119 NAD 1983 North Carolina
- `Temporal Coverage`: Specify the temporal extent of your study---i.e. the range of time represented by the data observations.
- `Temporal Resolution`: 2016
- `Lineage`: Retrieved from the [North Carolina General Assembly](https://www.ncleg.gov/Redistricting) and distributed by Professor Niwaeli Kimambo. It is unclear if further processing occured. 
- `Distribution`: Retrieved from the [North Carolina General Assembly](https://www.ncleg.gov/Redistricting) under 'District Plans Enacted by the Court' > 'Enacted 2016'
- `Constraints`: Legal constraints for *access* or *use* to protect *privacy* or *intellectual property rights*: N/A
- `Data Quality`: Quality unknown
- `Variables`: For each variable, enter the following information. If you have two or more variables per data source, you may want to present this information in table form (shown below)
  - `Label`: DISTRICT
  - `Alias`: unique district number
  - `Definition`: Short description or definition of the variable. Include measurement units in description.
  - `Type`: int64
  - `Accuracy`: N/A
  - `Domain`: 1, 13
  - `Missing Data Value(s)`: N/A
  - `Missing Data Frequency`: N/A

| Label | Alias | Definition | Type | Accuracy | Domain | Missing Data Value(s) | Missing Data Frequency |
| :--: | :--: | :--: | :--: | :--: | :--: | :--: | :--: |
| variable1 | ... | ... | ... | ... | ... | ... | ... |
| variable2 | ... | ... | ... | ... | ... | ... | ... |

#### Secondary data source2 name

... same form as above...

### Prior observations  

Prior experience with the study area, prior data collection, or prior observation of the data can compromise the validity of a study, e.g. through p-hacking.
Therefore, disclose any prior experience or observations at the time of study pre-registration here, with example text below:

At the time of this study pre-registration, the authors had _____ prior knowledge of the geography of the study region with regards to the ____ phenomena to be studied.
This study is related to ____ prior studies by the authors

For each primary data source, declare the extent to which authors had already engaged with the data:

- [ ] no data collection has started
- [ ] pilot test data has been collected
- [ ] data collection is in progress and data has not been observed
- [ ] data collection is in progress and __% of data has been observed
- [ ] data collection is complete and data has been observed. Explain how authors have already manipulated / explored the data.

For each secondary source, declare the extent to which authors had already engaged with the data:

- [ ] data is not available yet
- [ ] data is available, but only metadata has been observed
- [ ] metadata and descriptive statistics have been observed
- [ ] metadata and a pilot test subset or sample of the full dataset have been observed
- [ ] the full dataset has been observed. Explain how authors have already manipulated / explored the data.

If pilot test data has been collected or acquired, describe how the researchers observed and analyzed the pilot test, and the extent to which the pilot test influenced the research design.

### Bias and threats to validity

Given the research design and primary data to be collected and/or secondary data to be used, discuss common threats to validity and the approach to mitigating those threats, with an emphasis on geographic threats to validity.

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
