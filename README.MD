# Fuel Prices and Food Inflation In Nigeria: An Exploratory Analysis (2023-2026)

An exploratory data analysis examining the relationship between fuel prices (petrol and diesel) and food inflation in Nigeria, using monthly data from the Nigeria's National Bureau of Statistics (NBS)

## Key Finding
This project examined the relationship between fuel prices and food inflation in Nigeria from November 2023 to May 2026, using data from Nigeria's National Bureau of Statistics (NBS). While petrol showed the strongest simple correlation with food prices (r=0.793), deeper Granger causality testing revealed that the diesel specifically showed a short-term (1-month) predictive relationship with food prices, while petrol did not. This makes sense given diesel's central role in the food supply chain - powering trucks, generators, and irrigation - while petrol is used mainly for personal transport and has a less direct link to food production and distribution.

## Tools Used

- pandas — data cleaning, merging, and reshaping
- numpy — numerical calculations (rolling averages, percentage changes)
- matplotlib — base plotting (dual-axis charts)
- seaborn — statistical visualizations (heatmaps, distributions, boxplots)
- scipy — correlation testing (Pearson correlation, p-values)
- statsmodels — Granger causality testing

## Data Sources

- Petrol (PMS) prices: NBS Microdata Catalog 157 (https://microdata.nigerianstat.gov.ng/index.php/catalog/157)
- Diesel (AGO) prices: NBS Microdata Catalog 158 (https://microdata.nigerianstat.gov.ng/index.php/catalog/158)
- CPI / Food Index: NBS Microdata Catalog 154 (https://microdata.nigerianstat.gov.ng/index.php/catalog/154)

Data downloaded as monthly "Tables" (.xlsx) files, covering November 2023 – May 2026.

## Project Structure
nigeria_fuel_food_project/
├── README.md
├── data/
│   ├── raw/
│   │   ├── petrol/       # PMS Tables (.xlsx)
│   │   ├── diesel/       # Diesel Tables (.xlsx)
│   │   └── cpi/          # CPI Tables (.xlsx)
│   └── processed/
│       ├── petrol_master.csv
│       ├── diesel_master.csv
│       ├── cpi_food_master.csv
│       └── charts/       # Saved visualizations
└── notebooks/
├── 01_explore_petrol.ipynb
├── 02_explore_cpi.ipynb
├── 03_explore_diesel.ipynb
├── 04_validate_data.ipynb
└── 05_analysis.ipynb

## How to Run It

1. `01_explore_petrol.ipynb` — Extracts and cleans petrol price data from the raw petrol folder, builds petrol_master.csv.
2. `02_explore_cpi.ipynb` — Extracts and cleans CPI/food index data from the raw CPI folder, builds cpi_food_master.csv.
3. `03_explore_diesel.ipynb` — Extracts and cleans diesel price data from the raw diesel folder, builds diesel_master.csv.
4. `04_validate_data.ipynb` — Runs checks (shape, missing values, state counts) to confirm all three datasets were collected correctly with no errors.
5. `05_analysis.ipynb` — Merges all three datasets, runs exploratory analysis, correlation, lag analysis, and Granger causality testing; produces all saved charts.