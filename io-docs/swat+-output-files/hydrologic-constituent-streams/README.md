# Hydrologic Constituent Streams

The `hydin_*` and `hydout_*` constituent layouts below come from dormant routines in SWAT+ revision `6f515368`. The incoming call in the main reporting loop is commented out with an allocation-error note. The pinned source has no active calls to either constituent writer or to `header_cs`, their opener. The active `hydin_output` call handles the separate [water hydrograph reports](../hydrographs/README.md). [Reporting calls](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/command.f90#L626) · [Startup openers](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/proc_open.f90#L12)

The dormant opener defines four constituent groups (`pests`, `paths`, `metals`, and `salts`), four intervals (`day`, `mon`, `yr`, and `aa`), and TXT and CSV variants for both directions. Its checks use the `hyd` interval flags, a positive count for the constituent group, and the CSV flag for the second variant. It writes a basin and program line followed by a list-directed heading line in both formats. The ordinary CSV data write uses commas. There is no units line. [Incoming openers](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/header_cs.f90#L15) · [Outgoing openers](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/header_cs.f90#L237) · [Daily data format and print gate](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hcsin_output.f90#L19)

## Incoming streams

The intended filenames start with `hydin_pests_`, `hydin_paths_`, `hydin_metals_`, and `hydin_salts_`. The header supplies 12 identifying entries, `sol_in`, `sor_in`, and two additional heading entries per constituent. The data write supplies the 12 identifiers followed by one scalar per configured constituent. For eight salts this gives **30 header entries but 20 data values**. Positions 13 and 14 hold constituent 1 and, when present, constituent 2. [Salt header write](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/header_cs.f90#L55) · [Salt data write](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hcsin_output.f90#L54)

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
| [sol_in](sol_in.md) | Printed heading over the first configured scalar | constituent-dependent |
| [sor_in](sor_in.md) | Printed heading over the second configured scalar when present | constituent-dependent |

The routing code scales the upstream constituent record by the incoming fraction and stores that result in `hcsin_d` on the branch used for objects other than HRUs, HRU-LTEs, and routing units. Those other routing branches use separate inflow members. The incoming report routine loops across all objects and their receiving connections. Setup allocates the outer incoming arrays, while the addition operator expects initialized constituent members in the period accumulators. [Routing branch selection](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/command.f90#L109) · [Incoming diagnostic assignment](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/command.f90#L186) · [Outer record allocation](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hyd_connect.f90#L345) · [Constituent addition](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/constituent_mass_module.f90#L632)

## Outgoing streams

The intended filenames start with `hydout_pests_`, `hydout_paths_`, `hydout_metals_`, and `hydout_salts_`. The header supplies 12 identifying entries followed by two entries per constituent. The data write supplies the 12 identifiers followed by one scalar per configured constituent. For eight salts this gives **28 header entries and 20 data values**. The two heading strings have defaults `sol_out` and `sor_out`. The write lists therefore leave the paired headings out of alignment with the scalar values. [Salt header write](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/header_cs.f90#L277) · [Header declarations](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/constituent_mass_module.f90#L597) · [Salt data write](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hcsout_output.f90#L54)

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

The outgoing routine loops over each object's outgoing connections. Daily rows use the shared scratch record `hcs1` and print `frac_out` alongside it. This routine leaves the scratch record unchanged across connections and applies no outgoing fraction to the constituent values. The monthly accumulation uses the same shared record. [Connection loop and daily writes](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hcsout_output.f90#L16) · [Monthly addition](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hcsout_output.f90#L67)

## Period calculations and file exceptions

The daily writes use the day-print flag and interval counter. The month, year, and end-of-simulation writes have their respective boundary checks. Both routines add the running monthly record to the yearly record and the running yearly record to the final accumulator on every call, outside those boundary checks. Their end-of-simulation division by `time%yrs_prt` acts on the water `hin_a` record. The constituent final accumulator is printed without that division. These write lists therefore describe running sums with repeated contributions across calls. [Incoming accumulation](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hcsin_output.f90#L67) · [Incoming yearly and final addition](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hcsin_output.f90#L118) · [Outgoing yearly and final addition](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hcsout_output.f90#L118)

| Intended variant | Source exception |
| --- | --- |
| `hydin_metals_yr.csv` | The opener sends its title and heading writes to the yearly metals TXT unit 2718. The data write targets CSV unit 2734. [Header routing](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/header_cs.f90#L154) · [Data routing](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hcsin_output.f90#L145) |
| `hydout_pests_yr.csv` | The opener uses unit 2758. The yearly pesticide data write instead targets unit 2752, which the opener assigns to daily salt TXT. [Pesticide opener](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/header_cs.f90#L349) · [Salt opener](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/header_cs.f90#L277) · [Data routing](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hcsout_output.f90#L123) |
| `hydout_paths_yr.txt`, `hydout_paths_yr.csv` | Both header writes use the pesticide heading array with the pathogen count and index. [Yearly pathogen headings](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/header_cs.f90#L362) |
| `hydout_paths_aa.txt`, `hydout_paths_aa.csv` | Both header writes use `ipest` to index the pathogen array while the implied loop increments `ipath`. [Final pathogen headings](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/header_cs.f90#L417) |
| Incoming and outgoing salt variants | The opener references `cs_salt_solsor`. The pinned source declares this allocatable heading array, and the trace found no allocation for it. [Heading arrays](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/constituent_mass_module.f90#L613) · [Salt heading write](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/header_cs.f90#L55) |

These are static source findings for the dormant report code. Constituent values in a data write retain the units of the routed records. [Shared constituent record](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/constituent_mass_module.f90#L78)
