# Hydro displacement of natural gas in Tanzania's power sector

Interrupted time series analysis of how the commissioning of the Julius Nyerere Hydropower Project (JNHPP, 2,115 MW) changed natural gas use in Tanzania's electricity sector, using quarterly Bank of Tanzania statistics.

> **Status:** work in progress, unpublished. Please do not cite or reuse results without contacting the author.

## Questions

1. Did gas burned for electricity fall when JNHPP came online, and by how much?
2. Does the fall scale with the number of JNHPP turbines operating?
3. Are Tanzania's official gas and electricity statistics physically consistent with each other?

## Methods

- Edition-aware cleaning of BoT quarterly tables (handles repeated quarters and revisions across report editions)
- Interrupted time series (segmented regression, Newey–West standard errors), with log, seasonal and alternative-break variants
- Dose-response on the number of JNHPP turbines operating
- Physical consistency checks: implied heat rate and gas displaced per GWh of hydro
- Unknown-break scan (sup-F)

## Repository structure

```
├── hydro_displacement_its.ipynb   # full analysis, run top to bottom
├── data/
│   ├── raw/                       # BoT gas and electricity tables (tracked)
│   ├── private/                   # copyrighted news corpus (not tracked)
│   └── README.md                  # data sources and provenance
├── outputs/                       # figures and tables (generated, not tracked)
└── requirements.txt
```

## How to run

```bash
git clone https://github.com/AbbotAntony/tanzania-gas-hydro-displacement.git
cd tanzania-gas-hydro-displacement
pip install -r requirements.txt
jupyter lab hydro_displacement_its.ipynb
```

Run the notebook from the repository root. All figures, tables and regression summaries are written to `outputs/`.

## Data

See [`data/README.md`](data/README.md). The gas and electricity series are extracted from the Bank of Tanzania's *Consolidated Zonal Economic Reports*.

## Author

Abbot Josephat Antony, Department of Agricultural Economics and Business, University of Dar es Salaam
