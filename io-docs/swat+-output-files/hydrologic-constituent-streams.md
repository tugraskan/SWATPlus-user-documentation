# Hydrologic Constituent Streams

The `hydin_*` and `hydout_*` constituent files record salts, pesticides, pathogens, and metals on hydrologic connections. Their widths are configuration-dependent because one or more values are written for each configured constituent. Daily, monthly, yearly, and average-annual files use `_day`, `_mon`, `_yr`, and `_aa`.

## Incoming streams

The families are `hydin_salts_*`, `hydin_pests_*`, `hydin_paths_*`, and `hydin_metals_*`.

| Field | Description | Unit |
| --- | --- | --- |
| jday, mon, day, yr | Reporting date | n/a |
| iob, gis_id | Receiving object and GIS identifiers | n/a |
| type, num | Receiving object type and number | n/a |
| obtypin, obtyp_noin | Contributing object type and number | n/a |
| htyp_in | Incoming hydrograph type | n/a |
| frac_in | Fraction of the incoming hydrograph | fraction |
| sol_in | Dissolved constituent value; repeated for configured constituents | constituent-dependent |
| sor_in | Sorbed constituent value; repeated for configured constituents | constituent-dependent |

## Outgoing streams

The families are `hydout_salts_*`, `hydout_pests_*`, `hydout_paths_*`, and `hydout_metals_*`.

| Field | Description | Unit |
| --- | --- | --- |
| jday, mon, day, yr | Reporting date | n/a |
| iob, gis_id | Source object and GIS identifiers | n/a |
| type, num | Source object type and number | n/a |
| obtypout, obtyp_noout | Receiving object type and number | n/a |
| htyp_out | Outgoing hydrograph type | n/a |
| frac_out | Fraction of the outgoing hydrograph | fraction |

The constituent headings that follow are generated from the configured names and therefore cannot be represented by one fixed table. Interpret them together with the matching constituent input configuration.
