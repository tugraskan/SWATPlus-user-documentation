# Hydrologic Constituent Streams

The `hydin_*` and `hydout_*` constituent files record salts, pesticides, pathogens, and metals on hydrologic connections. Their widths are configuration-dependent because one or more values are written for each configured constituent. Daily, monthly, yearly, and average-annual files use `_day`, `_mon`, `_yr`, and `_aa`.

## Incoming streams

The families are `hydin_salts_*`, `hydin_pests_*`, `hydin_paths_*`, and `hydin_metals_*`.

| Field | Description | Unit |
| --- | --- | --- |
| [jday](hydrologic-constituent-streams/jday-incoming-streams.md), [mon](hydrologic-constituent-streams/mon-incoming-streams.md), [day](hydrologic-constituent-streams/day-incoming-streams.md), [yr](hydrologic-constituent-streams/yr-incoming-streams.md) | Reporting date | n/a |
| [iob](hydrologic-constituent-streams/iob-incoming-streams.md), [gis_id](hydrologic-constituent-streams/gis_id-incoming-streams.md) | Receiving object and GIS identifiers | n/a |
| [type](hydrologic-constituent-streams/type-incoming-streams.md), [num](hydrologic-constituent-streams/num-incoming-streams.md) | Receiving object type and number | n/a |
| [obtypin](hydrologic-constituent-streams/obtypin.md), [obtyp_noin](hydrologic-constituent-streams/obtyp_noin.md) | Contributing object type and number | n/a |
| [htyp_in](hydrologic-constituent-streams/htyp_in.md) | Incoming hydrograph type | n/a |
| [frac_in](hydrologic-constituent-streams/frac_in.md) | Fraction of the incoming hydrograph | fraction |
| [sol_in](hydrologic-constituent-streams/sol_in.md) | Dissolved constituent value; repeated for configured constituents | constituent-dependent |
| [sor_in](hydrologic-constituent-streams/sor_in.md) | Sorbed constituent value; repeated for configured constituents | constituent-dependent |

## Outgoing streams

The families are `hydout_salts_*`, `hydout_pests_*`, `hydout_paths_*`, and `hydout_metals_*`.

| Field | Description | Unit |
| --- | --- | --- |
| [jday](hydrologic-constituent-streams/jday-outgoing-streams.md), [mon](hydrologic-constituent-streams/mon-outgoing-streams.md), [day](hydrologic-constituent-streams/day-outgoing-streams.md), [yr](hydrologic-constituent-streams/yr-outgoing-streams.md) | Reporting date | n/a |
| [iob](hydrologic-constituent-streams/iob-outgoing-streams.md), [gis_id](hydrologic-constituent-streams/gis_id-outgoing-streams.md) | Source object and GIS identifiers | n/a |
| [type](hydrologic-constituent-streams/type-outgoing-streams.md), [num](hydrologic-constituent-streams/num-outgoing-streams.md) | Source object type and number | n/a |
| [obtypout](hydrologic-constituent-streams/obtypout.md), [obtyp_noout](hydrologic-constituent-streams/obtyp_noout.md) | Receiving object type and number | n/a |
| [htyp_out](hydrologic-constituent-streams/htyp_out.md) | Outgoing hydrograph type | n/a |
| [frac_out](hydrologic-constituent-streams/frac_out.md) | Fraction of the outgoing hydrograph | fraction |

The constituent headings that follow are generated from the configured names and therefore cannot be represented by one fixed table. Interpret them together with the matching constituent input configuration.
