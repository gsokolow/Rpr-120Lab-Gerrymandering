If you use this template for research, please [cite it](template_reference.bib):
> Kedron, P., & Holler, J. (2023). Template for Reproducible and Replicable Research in Human-Environment and Geographical Sciences. https://doi.org/10.17605/OSF.IO/W29MQ

# Reproduction of Geography 120 Gerrymandering and Area-Weighted Reaggregation Lab

## Contributors

- Grace Sokolow\*, gsokolow@middlebury.edu, @gsokolow, Middlebury College (Undergraduate)

\* Corresponding author and creator

## Abstract

Write a brief abstract about your research project.
If the project is a reproduction or replication study, include the full citation with a statement
This study is a *reproduction/replication* of:

> Kimambo, Niwaeli. 2021. *Lec/Lab: Gerrymandering: Maps and political representation* Human Geography with GIS (GEOG 120) at Middlebury College.

The original lab aims to determine whether North Carolina's 2019 congressional districts, which were redrawn by court order, are fairer than the 2016 districts based on geographic compactness and political representation.
First, votes cast in the 2016 presidential election are used to estimate the percentage of Republican voters in the 2016 and 2019 congressional districts.
Then, compactness scores are calculated by multiplying the area by 400π and dividing by the perimeter squared.
The devliverables include summary statistics for the compactness and percentage of Republicans from the 2026 and 2019 districts, as well as 4 maps: 
percentage votes for Republican presidential candidate by voting precinct, percentage votes for the 2016 Republican presidential candidate by 2016 districts, percentage of votes for the 2016 Republican presidential candidate by 2019 districts, and the compactness scores for each 2016 and 2019 district.


## Study Metadata

- `Key words`: gerrymandering, north carolina, area weighted reaggregation, 2016 elections, congressional redistricting
- `Subject`: Social and Behavioral Sciences: Geography
- `Date created`: November 30, 2023
- `Date modified`: November 30, 2023
- `Spatial Coverage`: North Carolina, USA.
- `Spatial Resolution`: Congressional districts, voting precincts
- `Spatial Reference System`: [SPCS "default" NC (Lambert Conformal Conic 1-parallel)](https://ncgs.state.nc.us/docs/2022_Datum_WG_June_2018_2.pdf)
- `Temporal Coverage`: [2016](https://www.ncleg.gov/Redistricting/DistrictPlanMap/C2016E) - [2019](https://www.ncleg.gov/Redistricting/DistrictPlanMap/C2019E)
- `Temporal Resolution`: One election cycle
- `Funding Name`: N/A
- `Course Title`: Open Source GIS (Middlebury College, Fall 2023)
- `Award info URI`: N/A
- `Award number`: N/A

## Related to

- `OSF Project`:
- `Pre-analysis Registration`:
- `Post-analysis Report Registration`:
- `Preprint`:
- `Conference Presentation`:
- `Publication`:
- `Prior Study`:
- `...`:

## Metadata for access

- `Rights`: [LICENSE](LICENSE): BSD 3-Clause "New" or "Revised"
- `Resource type`: Collection
- `Resource language`: English
- `Conforms to`: Template for Reproducible and Replicable Research in Human-Environment and Geographical Sciences version 1.0, DOI:[10.17605/OSF.IO/W29MQ](https://doi.org/10.17605/OSF.IO/W29MQ)

## Compendium structure and contents

This research compendium is structured with four main directories:

- `data`: contains subdirectories for `raw` data and `derived` data.
- `docs`: contains subdirectories for `manuscript`, `presentation`, and `report`
- `procedure`: contains subdirectories for `code` or software scripts, information about the computational `environment` in which the research was conducted, and non-code research `protocols`
- `results`: contains subdirectories for `figures`, formatted data `tables`, or `other` formats of research results.

The data, procedures, and results of this repository are outlined in three tables:
- Data: [data/data_index.csv](data/data_index.csv)
- Procedures: [procedure/procedure_index.csv](procedure/procedure_index.csv)
- Results: [results/results_index.csv](results/results_index.csv)

Important local **documents** include:
- Pre-analysis plan: [docs/report/preanalysis.pdf](docs/report/preanalysis.pdf)
- Study report: [docs/report/report.pdf](docs/report/report.pdf)
- Manuscript: [docs/manuscript/manuscript.pdf](docs/manuscript/manuscript.pdf)
- Presentation: [docs/presentation/presentation.pdf](docs/presentation/presentation.pdf)

#### Compendium reference

The [template_readme.md](template_readme.md) file contains more information on the design of this template and references used in the design.
The [Template_LICENSE](Template_LICENSE) file provides the BSD 3-Clause license for using this template.
To cite the template, please use [template_reference.bib](template_reference.bib) or:
> Kedron, P., & Holler, J. (2023). Template for Reproducible and Replicable Research in Human-Environment and Geographical Sciences. https://doi.org/10.17605/OSF.IO/W29MQ
