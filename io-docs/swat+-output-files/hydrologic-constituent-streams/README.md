# Hydrologic Constituent Streams

The `hydin_*` and `hydout_*` constituent files record salts, pesticides, pathogens, and metals on hydrologic connections. Their widths are configuration-dependent because one or more values are written for each configured constituent. Daily, monthly, yearly, and average-annual files use `_day`, `_mon`, `_yr`, and `_aa`.

## Incoming streams

The families are `hydin_salts_*`, `hydin_pests_*`, `hydin_paths_*`, and `hydin_metals_*`.

| Field | Description | Unit |
| --- | --- | --- |
| [jday](jday-incoming-streams.md) | Day of year | n/a |
| [mon](mon-incoming-streams.md) | Month | n/a |
| [day](day-incoming-streams.md) | Day of month | n/a |
| [yr](yr-incoming-streams.md) | Calendar year | n/a |
| [iob](iob-incoming-streams.md) | Receiving object identifier | n/a |
| [gis_id](gis_id-incoming-streams.md) | GIS identifier | n/a |
| [type](type-incoming-streams.md) | Receiving object type | n/a |
| [num](num-incoming-streams.md) | Receiving object number | n/a |
| [obtypin](obtypin.md) | Contributing object type | n/a |
| [obtyp_noin](obtyp_noin.md) | Contributing object number | n/a |
| [htyp_in](htyp_in.md) | Incoming hydrograph type | n/a |
| [frac_in](frac_in.md) | Fraction of the incoming hydrograph | fraction |
| [sol_in](sol_in.md) | Dissolved constituent value; repeated for configured constituents | constituent-dependent |
| [sor_in](sor_in.md) | Sorbed constituent value; repeated for configured constituents | constituent-dependent |

## Outgoing streams

The families are `hydout_salts_*`, `hydout_pests_*`, `hydout_paths_*`, and `hydout_metals_*`.

| Field | Description | Unit |
| --- | --- | --- |
| [jday](jday-outgoing-streams.md) | Day of year | n/a |
| [mon](mon-outgoing-streams.md) | Month | n/a |
| [day](day-outgoing-streams.md) | Day of month | n/a |
| [yr](yr-outgoing-streams.md) | Calendar year | n/a |
| [iob](iob-outgoing-streams.md) | Source object identifier | n/a |
| [gis_id](gis_id-outgoing-streams.md) | GIS identifier | n/a |
| [type](type-outgoing-streams.md) | Source object type | n/a |
| [num](num-outgoing-streams.md) | Source object number | n/a |
| [obtypout](obtypout.md) | Receiving object type | n/a |
| [obtyp_noout](obtyp_noout.md) | Receiving object number | n/a |
| [htyp_out](htyp_out.md) | Outgoing hydrograph type | n/a |
| [frac_out](frac_out.md) | Fraction of the outgoing hydrograph | fraction |

The constituent headings that follow are generated from the configured names and therefore cannot be represented by one fixed table. Interpret them together with the matching constituent input configuration.
