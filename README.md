# Trade

What India exports and imports, every month, in rupees and US dollars: by commodity group, by partner country and by Indian port.

Latest month: 2026-09. Exports from 2000-04, Imports from 2021-04.

## Files

| Path | |
|---|---|
| `data/monthly_totals.csv` | Exports and imports each month |
| `data/monthly/countries.csv` | Each partner country, each month |
| `data/monthly/commodities.csv` | Each commodity group, each month |
| `data/monthly/ports.csv` | Each port, each month |
| `data/yearly/commodity_country/<year>.csv` | Each commodity group with each country, each financial year |
| `data/yearly/commodity_port/<year>.csv` | Each commodity group at each port, each financial year |
| `data/yearly/country_port/<year>.csv` | Each country through each port, each financial year |

The [release](https://github.com/knowmoreindia/trade-data/releases/latest) has the full detail as `trade-<year>.csv.gz`, one file per financial year (2000-01 to 2026-27): 3,75,10,214 rows, one per commodity group, country, port and month, exactly as published, including rows with no trade.

Columns are described in `codebook.csv` and `datapackage.json`.

## Quick start

```python
import pandas as pd

base = "https://raw.githubusercontent.com/knowmoreindia/trade-data/main/data"
countries = pd.read_csv(f"{base}/monthly/countries.csv")
detail = pd.read_csv("https://github.com/knowmoreindia/trade-data/releases/latest/download/trade-2026-27.csv.gz")
```

## Worth knowing

- Figures are DGCI&S's, by principal commodity group. The latest three months are revised, so they change.
- Countries are spelt as DGCI&S printed them at the time. Some names changed over the years (for example `GERMAN F REP` before `GERMANY`).
- Commodity groups changed in April 2009, so older years use a different grouping.
- The summed tables leave out rows with no trade.

## Licence

[CC BY 4.0](https://creativecommons.org/licenses/by/4.0/). Credit: Know More India, from DGCI&S, Ministry of Commerce and Industry.
