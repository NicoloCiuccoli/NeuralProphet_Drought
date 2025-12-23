# Hydrogeological Water Balance and AI-Based Drought Forecasting Framework

This repository contains the datasets and Python code associated with the article:

**“On Forecasting Hydrological Drought and Water Balance in central Italy: Assessing Irrigation Deficit and   Water Reuse Opportunities in the Sentina area”**

Authors: *Nicolò Ciuccoli, *, Davide Fronzi, Alberto Tazioli, Anna Laura Eusebi, Francesco Fatone*  
Affiliations: *Università Politecnica delle Marche (UNIVPM), SIMAU Department*  
Contact: Nicolò Ciuccoli*[n.ciuccoli@staff.univpm.it]*  

This work was developed within the European project **TREASURE**, funded under the  
**Water4All Partnership (Horizon Europe, Grant Agreement No. 101060874)**.

---

## Abstract
This repository supports a basin-scale framework integrating a physically based
hydrogeological water balance with artificial intelligence–based forecasting techniques
to analyze drought dynamics and water deficit conditions. The workflow combines
hydro-climatic data derived from the ISPRA BIGBANG model, hydrogeological balance
computations, and data-driven forecasting models based on Neural Prophet.
Scenario-based simulations under extreme climatic conditions (heatwaves and heavy
rainfall) are included to assess model robustness and support adaptive water
management strategies.

---

## Repository Structure
.
├── code/
│   ├── BigBangDataset.ipynb
│   ├── Demand_Index.ipynb
│   ├── Neural_Prophet_Forecasting.ipynb
│   └── modello_neuralprophet.pkl
│
└── dataset/
    ├── Bacino.shp
    ├── SPI3/
    ├── Q_tot.xlsx
    ├── Full_Dataset.xlsx
    ├── Full_Dataset_HeavyRain.xlsx
    ├── Full_Dataset_Heatwave.xlsx
    ├── IDro_Dataset.xlsx
    ├── IDro_Dataset_HeavyRain.xlsx
    └── IDro_Dataset_Heatwave.xlsx



---

## Code Description

### `code/`
This folder contains the Jupyter notebooks implementing the different components of
the proposed framework.

- **`BigBangDataset.ipynb`**  
  Demonstrates how hydro-climatic variables and drought indices from the ISPRA
  BIGBANG model are processed.  
  An example based on the SPI3 index is provided, showing how gridded data are
  spatially aggregated over a user-defined basin using a shapefile and extracted for
  the available time period.

- **`Demand_Index.ipynb`**  
  Implements the hydrogeological water balance and the computation of the
  Demand Index.  
  The notebook highlights periods of water deficit and evaluates the contribution
  of treated wastewater reuse in compensating irrigation shortages.

- **`Neural_Prophet_Forecasting.ipynb`**  
  Contains the full forecasting workflow based on the Neural Prophet model,
  including:
  - training and validation of models for SPI, SPEI, and total available water,
  - one-month-ahead forecasting,
  - scenario-based simulations under **heatwave** and **heavy rainfall** conditions.

- **`modello_neuralprophet.pkl`**  
  Serialized Neural Prophet model trained for forecasting total water availability,
  provided to ensure reproducibility of the results.

---

## Dataset Description

### `dataset/`

- **`Bacino.shp`**  
  Shapefile defining the spatial extent of the analyzed basin.

- **`SPI3/`**  
  Folder containing example SPI3 raster files downloaded from the ISPRA BIGBANG
  platform. These files are used in `BigBangDataset.ipynb` to demonstrate spatial
  extraction and basin averaging.

- **`Q_tot.xlsx`**  
  Spreadsheet containing all intermediate calculations used for the
  hydrogeological water balance and total water availability assessment,
  supporting the analysis presented in `Demand_Index.ipynb`.

- **`Full_Dataset.xlsx`**  
  Complete dataset used to train forecasting models for SPI and SPEI under
  observed conditions.

- **`Full_Dataset_HeavyRain.xlsx`**  
  Dataset representing a heavy rainfall scenario, used for scenario-based
  simulations.

- **`Full_Dataset_Heatwave.xlsx`**  
  Dataset representing a heatwave scenario, used for scenario-based simulations.

- **`IDro_Dataset.xlsx`**  
  Dataset used to train the Neural Prophet model for total water availability.

- **`IDro_Dataset_HeavyRain.xlsx`**  
  Scenario-specific dataset used to simulate heavy rainfall conditions for water
  availability forecasting.

- **`IDro_Dataset_Heatwave.xlsx`**  
  Scenario-specific dataset used to simulate heatwave conditions for water
  availability forecasting.

---

## Dependencies

The notebooks require the following Python libraries:

### Core Libraries
- `pandas`
- `numpy`
- `os`
- `pickle`
- `datetime`
- `dateutil`

### Visualization
- `matplotlib`
- `seaborn`
- `mpl_toolkits.axes_grid1`

### Geospatial and Raster Processing
- `rasterio`
- `shapely`
- `pyproj`
- `pyshp` (shapefile)

### Machine Learning and Forecasting
- `prophet`
- `neuralprophet`
- `scikit-learn`
- `scipy`

---

## Notes on Reproducibility
- All datasets required to reproduce the results presented in the associated paper
  are included in this repository.
- Scenario-based datasets are provided separately to clearly distinguish observed
  conditions from simulated extreme events.
- The workflow can be adapted to other study areas by replacing the basin
  shapefile and the corresponding datasets.

---

## License
Copyright (C) 2025 *[Authors]*  

This repository is distributed for academic and research purposes.
Please cite the associated article if you use this code or the datasets.

---

## Citation
If you use this repository, please cite:

> *[Full paper citation once accepted]*
