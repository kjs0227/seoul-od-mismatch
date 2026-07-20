# seoul-od-mismatch

# Identifying Systematic OD-Level Mismatches Between Household Travel Surveys and Mobile Phone Data: A Case Study of Seoul

Kim, J., & Kim, E.J. (2026). *Identifying Systematic OD-Level Mismatches Between Household Travel Surveys and Mobile Phone Data: A Case Study of Seoul*. **Transportation Research Record**. In press.

## Overview

This repository contains the code accompanying the paper, **“Identifying Systematic OD-Level Mismatches Between Household Travel Surveys and Mobile Phone Data: A Case Study of Seoul.”**

The study compares origin–destination (OD) travel patterns derived from the 2021 Household Travel Survey (HTS) and LTE/5G cellular signaling (LCS) data for Seoul, South Korea. It examines systematic differences in OD-flow distributions, observed and unobserved OD cells, spatial patterns, and model-based OD structures.

## Getting Started

### Dependencies

* Python 3.11
* Jupyter Notebook or JupyterLab
* Additional Python packages imported at the beginning of each notebook

### Components

#### Datasets

* **Household Travel Survey (HTS):** The 2021 household travel survey provided through the Korea Transport Database (KTDB).
* **LTE/5G Cellular Signaling (LCS) Data:** [The Seoul Life Movement Data provided by the Seoul Metropolitan Government.](https://data.seoul.go.kr/dataVisual/seoul/seoulLivingMigration.do)

The original datasets are not included in this repository. Processed person-level records, trip-level records, and derived OD matrices are also not redistributed because they are subject to the respective providers’ access requirements and data-use conditions.

Users must obtain the source data independently and update the local file paths in the notebooks before execution.

#### Notebooks

##### `01_HTS_preprocessing_and_expansion.ipynb`

* Preprocesses respondent-level HTS person and trip records and retains trips with both origins and destinations within Seoul.
* Derives person-level expansion coefficients based on residential location, gender, and age group.
* Applies each coefficient to all intra-Seoul trips reported by the respondent to construct population-equivalent HTS OD flows.

##### `02_LCS_preprocessing_and_averaging.ipynb`

* Preprocesses the released hourly LCS OD flows and retains trips with both origins and destinations within Seoul.
* Harmonizes age, gender, travel type, and arrival-time classifications with the HTS data.
* Averages flows across the four Thursdays in October 2021 to construct representative Thursday LCS OD flows.

##### `03_Mismatches_in_OD_Trip_Distributions.ipynb`

* Compares HTS and LCS OD trip distributions across subgroups defined by gender, age, travel type, and arrival time.
* Computes standardized root mean square error (SRMSE) to quantify distributional mismatches between the two datasets.
* Computes zero-cell indicators to characterize the sparsity and overlap of observed OD coverage.

##### `04_Data_construction_and_regression.ipynb`

* Constructs the origin-level analytical dataset by linking Origin-SRMSE with spatial, socioeconomic, and survey attributes.
* Applies principal component analysis (PCA) to the four land-use proportions to derive a composite indicator of land-use composition.
* Estimates an OLS regression model to examine associations between origin-level mismatches and the explanatory variables.

##### `05_Gravity_model_analysis.ipynb`

* Identifies the common set of interzonal OD pairs with non-zero flows in both HTS and LCS.
* Estimates comparable log-linear gravity-type trip distribution models using origin and destination totals and average OD travel time.
* Applies iterative proportional fitting (IPF) to the predicted OD matrices and evaluates model performance using R² and the common part of commuters (CPC).

## Notice

* Run the notebooks in numerical order.
* Source-data paths must be modified to match the user’s local directory structure.
* Generated intermediate files and analytical outputs are not tracked in this repository.
* Minor differences may occur when source files, administrative-zone crosswalks, or provider-side data revisions differ from those used in the paper.
* The associated paper has been accepted for publication and is currently in press. Publication details will be updated when the final bibliographic information and DOI become available.

## Authors

* [Jisu Kim](https://github.com/kjs0227)
* [Eui-Jin Kim](https://github.com/Eui-Jin)

## License

The source code developed for this repository is licensed under the MIT License. See [`LICENSE`](LICENSE) for details.

## Acknowledgments

This work was supported by the National Research Foundation of Korea (NRF) grant funded by the Korea government (MSIT) (No. RS-2025-00520515).
