# Trade

What India exports and imports, every month, in rupees and US dollars: by commodity group, by partner country and by Indian port.

Latest month: 2026-09. Exports from 2000-04, Imports from 2021-04.

## At a glance

| Table | Rows | Period | Where |
| --- | ---: | --- | --- |
| monthly-totals | 384 | 2000-04 to 2026-09 | `data/monthly_totals.csv` |
| countries | 80,780 | 2000-04 to 2026-09 | `data/monthly/countries.csv` |
| commodities | 55,889 | 2000-04 to 2026-09 | `data/monthly/commodities.csv` |
| ports | 68,543 | 2000-04 to 2026-09 | `data/monthly/ports.csv` |
| commodity-country | 5,38,483 | 2000-01 to 2026-27 | `data/yearly/commodity_country/` (27 files) |
| commodity-port | 2,88,952 | 2000-01 to 2026-27 | `data/yearly/commodity_port/` (27 files) |
| country-port | 3,17,522 | 2000-01 to 2026-27 | `data/yearly/country_port/` (27 files) |
| detail | 3,75,10,214 |  | release |

## Spreadsheet-friendly files

The same data, one row per item and one column per period, for spreadsheets.

- `data/wide/monthly_totals.csv`: One row per month: exports, imports and the balance, in US dollars and rupees

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

## How to cite

Know More India, *Trade*, version 2026-11-24, https://github.com/knowmoreindia/trade-data. Licensed CC BY 4.0.

```bibtex
@misc{knowmoreindia_trade,
  author = {{Know More India}},
  title = {Trade},
  year = {2026},
  version = {2026-11-24},
  howpublished = {\url{https://github.com/knowmoreindia/trade-data}}
}
```

## Licence

[CC BY 4.0](https://creativecommons.org/licenses/by/4.0/). Credit: Know More India, from DGCI&S, Ministry of Commerce and Industry.
