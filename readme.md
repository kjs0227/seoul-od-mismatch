# seoul-od-mismatch

This repository contains the reproducibility code for the paper:

**“Identifying Systematic OD-Level Mismatches Between Household Travel Surveys and Mobile Phone Data: A Case Study of Seoul.”**

The study compares origin–destination (OD) travel patterns derived from the 2021 Household Travel Survey (HTS) and LTE/5G Cellular Signaling (LCS) data for Seoul, South Korea.

The repository includes code for:

* HTS preprocessing and person-level population expansion
* LCS preprocessing and average-Thursday flow construction
* OD-level distributional mismatch indicators
* Zero-cell and OD-coverage indicators
* Origin- and destination-level regression analyses
* Gravity-model estimation and IPF calibration

## Repository Structure

```text
notebooks/
├── 01_HTS_preprocessing_and_expansion.ipynb
├── 02_LCS_preprocessing_and_averaging.ipynb
├── 03_distributional_mismatch_indicators.ipynb
├── 04_spatial_regression_analysis.ipynb
└── 05_gravity_model_analysis.ipynb

data/
└── README.md

outputs/
└── README.md
```

## Data Availability

The original HTS and LCS datasets are not redistributed in this repository.

The HTS data are available through the Korea Transport Database (KTDB), subject to the provider’s access requirements and data-use conditions.

The LCS data are available through the Seoul Metropolitan Government data platform. Users must obtain and use the source data in accordance with the applicable terms and conditions.

Processed person-level records, trip-level records, and derived OD matrices are also not included in this repository.

The software license provided with this repository applies only to the source code and does not grant any rights to the underlying HTS or LCS datasets.

## Expected Data Structure

After obtaining the required source data, organize the input files as follows:

```text
0_data/
├── 개인통행실태조사(2021년기준)/
│   ├── ①개인특성.csv
│   └── ②이동특성.csv
├── 생활이동_행정동_202110/
│   ├── 생활이동_행정동_2021.10_00시.csv
│   ├── ...
│   └── 생활이동_행정동_2021.10_23시.csv
├── administrative districts (2016-2021).xlsx
├── 202110_연령별인구현황.xlsx
└── 202110_연령별인구현황_서울시.xlsx
```

The notebooks create processed files and analytical outputs locally. These generated files are excluded from version control.

## Environment

Create the Python environment using:

```bash
conda env create -f environment.yml
conda activate seoul-od-mismatch
```

Launch JupyterLab from the repository root:

```bash
jupyter lab
```

## Execution Order

Run the notebooks in numerical order:

1. `01_HTS_preprocessing_and_expansion.ipynb`
2. `02_LCS_preprocessing_and_averaging.ipynb`
3. `03_distributional_mismatch_indicators.ipynb`
4. `04_spatial_regression_analysis.ipynb`
5. `05_gravity_model_analysis.ipynb`

The first two notebooks construct aligned HTS and LCS OD tables. The remaining notebooks reproduce the mismatch indicators, regression results, and gravity-model results reported in the paper.

## Reproducibility Checks

Using the data version analyzed in the paper, the preprocessing notebooks should produce approximately:

* 113,763 observed HTS persons
* 57,007 unweighted intra-Seoul HTS trips
* 20,764,048 expanded intra-Seoul HTS trips
* 14,682,289 average-Thursday LCS trips
* 424 Seoul analysis zones
* 179,776 possible OD pairs

Minor differences may occur if source files, administrative-zone crosswalks, or provider-side data revisions differ from the versions used in the study.

## Citation

Citation information is provided in `CITATION.cff`.

Please cite the associated paper when using this code in academic work.

## License

The source code is released under the license included in the `LICENSE` file. The license does not apply to the original or processed HTS and LCS datasets.
