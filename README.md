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
* **LTE/5G Cellular Signaling (LCS) Data:** The Seoul Life Movement Data provided by the Seoul Metropolitan Government.

The original datasets are not included in this repository. Processed person-level records, trip-level records, and derived OD matrices are also not redistributed because they are subject to the respective providers’ access requirements and data-use conditions.

Users must obtain the source data independently and update the local file paths in the notebooks before execution.

#### Notebooks

##### `01_HTS_preprocessing_and_expansion.ipynb`

* Preprocesses the HTS person and trip records.
* Identifies trips whose origins and destinations are both located within Seoul.
* Applies person-level population expansion.
* Constructs analysis-ready HTS OD tables.

##### `02_LCS_preprocessing_and_averaging.ipynb`

* Preprocesses the hourly LCS files.
* Extracts travel flows with origins and destinations within Seoul.
* Constructs average-Thursday travel flows.
* Produces analysis-ready LCS OD tables aligned with the HTS geography.

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
