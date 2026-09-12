# sgsc-smartmeter-mirror
Mirror of the Smart Grid Smart City (SGSC) customer trial smart-meter data (Newcastle, Australia, 2011–2014; Ausgrid / Australian Government, CC-BY 3.0 AU) for the deviation-score (D) electricity instance.
# SGSC smart-meter mirror (Newcastle, Australia, 2011–2014)

Mirror of the **Smart-Grid Smart-City Customer Trial Data** published by the
Australian Government on data.gov.au, kept here so that the deviation-score (D)
electricity analysis can be reproduced from a fixed copy.

- Source: https://data.gov.au/data/dataset/smart-grid-smart-city-customer-trial-data
- Publisher: Australian Government Department of Climate Change, Energy, the
  Environment and Water; trial led by Ausgrid (2010–2014)
- Licence: Creative Commons Attribution 3.0 Australia (CC-BY 3.0 AU)
- Coverage: Newcastle (NSW), 2011-10-10 to 2014-02-13, 30-min interval readings
- Downloaded: 2026-09-12 (dataset last updated on data.gov.au: 2022-04-11)

No file in this repository has been modified from the source, except the
derived daily table described below. Files are redistributed under the same
CC-BY 3.0 AU licence with attribution to the publisher above.

## Files (Release `sgsc-v1`)

| File | Source resource | Notes |
|---|---|---|
| `sgsc-ct_electricity-use-interval-readings.7z` (split `.001`, `.002`, …) | Electricity Use Interval Reading | 30-min GENERAL_SUPPLY_KWH, CONTROLLED_LOAD_KWH, GROSS/NET_GENERATION_KWH per CUSTOMER_KEY |
| `sgsc-ct_customer-household-data.csv` | Customer Household Data | tariff product, control-group flag, assumed income group, dwelling type, PV meter counts, service status, exit reason |
| `sgsc-ct_peak-events.csv` | Peak Events | DPR/DPP event timestamps, EVENT_KEY |
| `sgsc-ct_peak-event-response.csv` | Peak Event Response | actual vs baseline kWh, rebate per event |
| `sgsc-ct_datagov_revised-data-dictionary.xlsx` | Customer Trial Data Dictionary | column definitions for all resources |
| `daily_dataset_sgsc.csv` | **derived** | one row per customer-day: `CUSTOMER_KEY, day, energy_count, energy_sum, pv_flag`; `energy_sum` = GENERAL_SUPPLY_KWH + CONTROLLED_LOAD_KWH; built by `make_daily.py` |

MD5 checksums of the source files are in `MD5SUMS`.
To reassemble the split archive: `7z x sgsc-ct_electricity-use-interval-readings.7z.001`.

## Use in the D-score project

Third instance of the deviation score (D) — household electricity, second site
after Low Carbon London. Pre-registration: OSF 9zfye (v1 2026-09-11; update 1
2026-09-12, written before any SGSC file was opened). Analysis code lives in
the `dscore` repository; this repository holds data only.

Related mirrors: `lcl-smartmeter-mirror` (London).

## Citation

Australian Government Department of Climate Change, Energy, the Environment and
Water. *Smart-Grid Smart-City Customer Trial Data*. data.gov.au, 2015 (updated
2022). CC-BY 3.0 AU.
