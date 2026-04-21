# Barcelona Housing Affordability Analysis

Analysis of housing affordability in Barcelona (2018–2022) using open data from the Barcelona City Council. The project explores the relationship between cadastral property values, dwelling size distribution, and household income across the city's 10 districts and 73 neighbourhoods.

## Motivation

Housing affordability is one of the most pressing social issues in Barcelona. This project uses publicly available data to quantify and visualise the structural inequality in access to housing across the city, identifying which districts and neighbourhoods face the greatest affordability pressure.

## Data Sources

All datasets are sourced from [Open Data Barcelona](https://opendata-ajuntament.barcelona.cat) (Ajuntament de Barcelona) under a Creative Commons Attribution 4.0 licence.

| Dataset | Description | Period |
|---|---|---|
| Cadastral values of housing premises | Unit and total cadastral value (€/m²) by census section | 2018–2022 |
| Housing premises by surface area | Number of dwellings by size range per census section | 2018–2022 |
| Household disposable income per capita | Estimated income per person (€) by census section | 2018–2022 |

> **Note:** Cadastral values are fiscal estimates updated infrequently and sit below market prices. They serve as a relative proxy for comparing districts rather than as absolute market indicators.

## Tech Stack

- **Python** — pandas, numpy, sqlite3
- **SQL** — SQLite (joins, aggregations, subqueries, CASE expressions)
- **Visualisation** — matplotlib, seaborn *(notebooks 03–04)*
- **Environment** — Jupyter Notebook

## Project Structure
```
barcelona-housing-affordability-analysis/
│
├── data/
│   ├── raw/
│   │   ├── cadastral_values/
│   │   ├── housing_surface/
│   │   └── household_income/
│   └── processed/
│
├── notebooks/
│   ├── 01_data_loading_and_sql.ipynb
│   ├── 02_eda_and_cleaning.ipynb
│   ├── 03_affordability_analysis.ipynb
│   └── 04_clustering.ipynb
│
├── README.md
└── requirements.txt
```
## Notebooks

| Notebook | Status | Description |
|---|---|---|
| 01 · Data Loading & SQL | ✅ Complete | Data ingestion, column standardisation, SQLite database creation, SQL exploration queries |
| 02 · EDA & Cleaning | 🔄 In progress | Missing value analysis, outlier detection, feature engineering |
| 03 · Affordability Analysis | 🔄 In progress | Affordability index, district and neighbourhood visualisations |
| 04 · Clustering | 🔄 In progress | K-Means clustering of neighbourhoods by affordability profile |

## Key Findings (Notebook 01)

- **Cadastral values are structurally stable** across all districts (+0.06% to +0.66% over 2018–2022), confirming their nature as fiscal rather than market indicators.
- **Income growth is unequal.** Lower-income districts show higher relative growth (Ciutat Vella +11.2%) but from a much lower base. Sarrià-Sant Gervasi, the wealthiest district, grew only +1.6%.
- **Small dwelling concentration reveals residential segregation.** Ciutat Vella (52.9%) and Nou Barris (42.9%) have the highest share of dwellings under 60m² — and also the lowest household incomes. La Barceloneta is the most extreme case at 76.9%.
- **This pattern is structurally persistent.** The share of small dwellings barely changed across any district over five years.

## How to Run

```bash
git clone https://github.com/oscarrhdatascience/barcelona-housing-affordability-analysis.git
cd barcelona-housing-affordability-analysis
pip install -r requirements.txt
```

Download the raw datasets from [Open Data Barcelona](https://opendata-ajuntament.barcelona.cat) and place them in the corresponding folders under `data/raw/` before running the notebooks.

## Author

**Óscar Rodríguez Hernández**  
[LinkedIn](https://www.linkedin.com/in/oscar-rh-data-science) · [GitHub](https://github.com/oscarrhdatascience)