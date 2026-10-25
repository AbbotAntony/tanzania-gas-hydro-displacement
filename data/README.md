# Data

## `raw/` (tracked)

| File | Content | Source |
|---|---|---|
| `bot_gas.csv` | Natural gas production and consumption by sector, annual and quarterly (MMscf) | Bank of Tanzania, *Consolidated Zonal Economic Report*, multiple editions |
| `bot_electricity.csv` | Electricity generation by source and zone, annual and quarterly (MWh) | Bank of Tanzania, *Consolidated Zonal Economic Report*, multiple editions |

Values were extracted from the published PDF reports. Each row records the source document (`doc_title`, `url`, `pdf_page`, `table_no`), the value as printed, and a `latest_edition` flag, so every figure can be traced back to its page. The same quarter often appears in several report editions; the notebook's edition-aware cleaning step decides which value is used and logs every decision to `outputs/data_issues_log.csv`.

Source reports are publicly available from the Bank of Tanzania website (https://www.bot.go.tz).

## `private/` (NOT tracked)

Holds the Daily News article corpus used only to cross-check the JNHPP turbine commissioning dates. The article text is copyrighted and is excluded by `.gitignore`. The notebook skips that check if the file is absent; all results run without it.
