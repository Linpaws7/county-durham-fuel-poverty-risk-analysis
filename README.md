# County Durham EPC Fuel Poverty Risk

EPC-led fuel poverty risk analysis for County Durham using property energy performance data, local fuel poverty statistics, domestic electricity and gas consumption, and deprivation indicators.

## Project contents

- `notebooks/03_epc_data_clean.ipynb`  
  Pulls and prepares EPC data for County Durham.
- `notebooks/04_join_epc_fuel_poverty.ipynb`  
  Joins EPC postcode risk outputs with local authority fuel poverty data.
- `notebooks/05_join_consumption_iod.ipynb`  
  Adds electricity, gas, and IMD/IOD contextual indicators.
- `notebooks/06_final_analysis_county_durham.ipynb`  
  Produces final summary analysis tables.
- `reports/county_durham_fuel_poverty_risk_report.docx`  
  Final Word report with tables, findings, and formulas.

## Project aim

This project builds a postcode-level risk proxy for fuel poverty in County Durham.  
The main analytical base is EPC data, and the final output combines:

- EPC-derived property efficiency indicators
- Local authority fuel poverty percentage
- Domestic electricity consumption
- Domestic gas consumption
- IMD/IOD deprivation context

## Main workflow

1. Pull EPC domestic records for County Durham.
2. Keep the latest EPC per property.
3. Engineer property-level risk flags:
   - low rating
   - low efficiency
   - improvement gap
4. Aggregate to postcode level.
5. Build a composite postcode risk score.
6. Add local authority context from fuel poverty, energy consumption, and deprivation datasets.
7. Summarise and interpret the results.

## Key outputs used in the report

- Full EPC rows pulled: 299,445
- Latest unique property records retained: 233,972
- Final filtered postcodes ranked: 4,429
- Highest-risk postcode in this model: `DH1 5HG`
- Lowest-risk postcode in this model: `DL14 8FT`

## Data files needed

Place the required raw input files in `data/raw/` before running the notebooks.

Expected files:
- `fuel_poverty_la_2023.xlsx`
- `electricity_la_2005_2024.xlsx`
- `gas_la_2005_2024.xlsx`
- `iod2025_la_summary_v2.xlsx`

## Python packages

Install packages from `requirements.txt`.

## Notes

- This is an EPC-led postcode risk proxy, not a directly observed postcode fuel poverty rate.
- Fuel poverty, electricity, gas, and IMD/IOD values are local-authority-level contextual variables in this version of the project.
