
# The (In)Accessibility of Hospitals in Belgium

This repository contains replication material for the following publication:  
**Daenekindt, Stijn (2025). De (On)Bereikbaarheid van Ziekenhuizen in België, *Tijdschrift Sociologie*, 6: 65–75. doi: https://doi.org/10.38139/ts.94750**  

If you use this repository or any of the code/materials, please cite the reference above.

---

## a. Code

This folder contains the quarto scripts (`.qmd`; written in R) necessary to prepare the data and reproduce the visualizations. 

- **`1. Preprocessing.qmd`** to prepare the input data and calculate the travel times.
- **`2. Visualization.qmd`** suffices to reproduce all final figures (located in the `/Output` folder). You do not need to run the other script unless you want to replicate the full data processing (the estimation of the travel times takes a looooooooooong time).

### Summary of scripts

**`1. Preprocessing.qmd`**  
- Geocodes the hospital addresses.  
- Constructs indicators for income and age.  
- Calculates centroids of statistical sectors.  
- Creates a 15-minute isochrone (combined for all hospitals).  
- Generates the hospital–centroid matrix used for travel time calculation.  
- Computes travel times between statistical sectors and hospitals based on the hospital-centroid matrix. For the calculation you need an API-key (cf. 'hereR'-package)  

> Preprocessed outputs are saved in the `/Preprocessed` folder, and the calculated travel times are in `/Preprocessed/Batches`.  

**`2. Visualization.qmd`**  
- Reproduces all figures used in the publication.  
- Only requires the shape file of statistical sectors (see script 1 for the source) and the files in the folder 'preprocessed' as input files.

---

## b. Preprocessed

Contains intermediate data produced during preprocessing.

- **`Batches/`**: the calculated travel times.  
- **`Isochrones/`**: the isochrone polygons (15-minute accessibility).  
- **`Sites/`**: locations of the hospitals and of the statistical sector centroids.  
- **`Geocoded_hospitals.csv`**: geocoded addresses of the hospital campuses.  
- **`Inkomengegevens_per_StatS.csv`** & **`Leeftijdgegevens_per_StatS.csv`**: income and age data per statistical sector.  
- **`Batch_info_Rank1.xlsx`** to **`Batch_info_Rank5.xlsx`**: hospital–centroid matrix      
  - E.g., `Batch_info_Rank1.xlsx` contains for each statistical sector the closest hospital, `Batch_info_Rank2.xlsx` the second closest, etc.  

---

## c. Source

This folder is empty by default.

The scripts reference several external source files that are not included in this repository (due to potential copyright or distribution restrictions). However, all file names and download instructions are provided in the code.

The required files include:

- `sh_statbel_statistical_sectors_3812_20240101.shp`: shapefile of statistical sectors  
- `12_2024_Adressenlijst AZ en PZ_Liste d'adresses HG et HP.xls`: hospital address list  
- `TF_CENSUS_2021_S01.xlsx`: census data (age)  
- `TF_PSNL_INC_TAX_SECTOR (1).xlsx`: income data per statistical sector  

> To reproduce the visualizations only, you only need the shapefile and `2. Visualization.qmd`.  
> For full replication, download all source files as instructed in the script 1.

---

## d. Output

Contains all generated plots used in the publication.




