# Soil

The legacy carbon diagnostics can write `hru_begsim_soil_prop.txt/.csv` and `hru_endsim_soil_prop.txt/.csv`. They use the same printed headings and write one row per soil layer. The `carbon` value changes meaning between the two reports, as explained below.

## How to produce these files

Set `carbon` to `2` in [codes.bsn](../../introduction-1/basin-1/codes.bsn/README.md). In [print.prt](../../introduction-1/simulation-settings/print.prt/README.md), use named rows (`use_obj_lbls = y`) and set a daily, monthly, or yearly column of `hru_cb` to lowercase `l`. For example, `hru_cb n n l n` enables the legacy layer diagnostics needed to create both snapshot files. The files record the beginning and end of the simulation. Set `csvout` to `y` for the CSV copies. [Legacy print row](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_print_codes_read.f90#L408), [Snapshot file creation and beginning write](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/carbon_legacy_module.f90#L469), [End-of-simulation caller](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_output.f90#L300)

The opener also checks that at least one daily, monthly, or yearly `hru_cb` setting differs from `n`. The average-annual setting alone, such as `hru_cb n n n l`, opens neither snapshot. The beginning snapshot is written after soil carbon initialization. The ending writer runs once on the final day, from the first full HRU's output call, and loops over all full HRUs. [Legacy open conditions](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/carbon_legacy_module.f90#L469-L537), [startup order](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/main.f90.in#L117-L129), [ending call](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/hru_output.f90#L303-L319).

Both formats have 24 headings and 24 values per data row, with one row per layer per full HRU. They write a simulation identification line and the header, then data rows. The table gives the units because the files omit a units row.

| Field | Description | Unit |
| --- | --- | --- |
| [freq](freq.md) | Report marker | n/a |
| [soil_name](soil_name.md) | Soil name | n/a |
| [soil_lyr](soil_lyr.md) | Soil-layer number | n/a |
| [soil_depth](soil_depth.md) | Cumulative depth to the layer bottom, written as an integer | mm |
| [jday](jday.md) | Day of year at simulation end. The beginning report writes zero. | n/a |
| [mon](mon.md) | Month | n/a |
| [day](day.md) | Day of month | n/a |
| [yr](yr.md) | Calendar year | n/a |
| [unit](unit.md) | Object identifier | n/a |
| [gis_id](gis_id.md) | GIS identifier | n/a |
| [name](name.md) | Object name | n/a |
| [bd](bd.md) | Bulk density | Mg/m3 |
| [awc](awc.md) | Available water capacity per unit layer thickness | mm/mm |
| [soil_k](soil_k.md) | Saturated hydraulic conductivity | mm/h |
| [carbon](carbon.md) | Beginning carbon percentage; ending layer carbon mass | percent (begsim); kg C/ha (endsim) |
| [clay](clay.md) | Soil clay fraction | percent |
| [silt](silt.md) | Soil silt fraction | percent |
| [sand](sand.md) | Soil sand fraction | percent |
| [rock](rock.md) | Soil rock fraction | percent |
| [alb](alb.md) | Soil albedo | fraction |
| [usle_k](usle_k.md) | USLE soil erodibility factor | n/a |
| [ec](ec.md) | Electrical conductivity | dS/m |
| [caco3](caco3.md) | Calcium carbonate | percent |
| [ph](ph.md) | Soil pH | n/a |

## How the model builds the printed layers

The writer uses the full HRU's model profile after soil initialization. Without a custom layer file, the first model layer ends at 10 mm. If the first input layer is deeper than 19.5 mm, the model adds a layer and retains the original first-layer bottom as the second layer bottom. Otherwise it keeps the input layer count and uses 10 mm as the first model layer bottom. With `soil_lyr_depths.sol`, it also starts at 10 mm, uses the configured deeper boundaries subject to the source profile depth, and averages the input properties in 1 mm increments over each resulting interval. Septic biozone setup can change or split the layers for an individual HRU. [Default layering](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/soils_init.f90#L69-L131), [Custom layer boundaries](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/soils_init.f90#L166-L226), [Layer averages](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/soils_init.f90#L243-L273), [Septic biozone setup](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/soils_init.f90#L292-L351)

Matching soil tests can replace bulk density, carbon percentage, sand, silt, and clay before the model copies the profile to the HRU. Initialization can also replace or limit some values. Missing or nonpositive conductivity uses a hydrologic-group default. Near-zero bulk density and available water capacity receive defaults, and both have upper bounds. Rock is capped at 98%. Near-zero calcium carbonate and pH receive defaults of 2.8% and 6.5. The `awc` column is capacity per unit thickness. The model calculates field-capacity water depth separately. Both snapshots print layer albedo, and the initialization floor of 0.1 applies to the separate profile albedo. [Soil-test values](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/soils_test_adjust.f90#L65-L105), [Order of initialization](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/soils_init.f90#L280-L314), [Property defaults and limits](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/soil_phys_init.f90#L50-L101), [Water capacity calculations](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/soil_awc_init.f90#L74-L87)

## Why the carbon values differ

The beginning snapshot prints the model layer's carbon percentage. The initializer copies that percentage into a separate carbon record and floors it at 0.001%. It multiplies the resulting fraction by layer soil mass in kg/ha, calculated as `10000 × layer thickness in mm × bulk density in Mg/m³`. This startup mass calculation uses no rock-fraction adjustment. A beginning row can therefore print 0% even when the initialized model stock is positive. [Initial carbon percentage](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/soil_nutcarb_init.f90#L39-L48), [Initial layer mass](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/soil_nutcarb_init.f90#L113-L125)

The ending snapshot writes the stored total carbon, `soil1(j)%tot(ly)%c`, in kg C/ha. During carbon cycling, the model updates the total from structural residue, metabolic residue, passive humus, slow humus, and microbial carbon. The ending writer copies the stored value directly. Both formats keep the heading `carbon`, so subtracting the beginning value from the ending value mixes two different units. To reconstruct the startup mass on the model's basis, use the 0.001% minimum and the model's unrounded layer thickness. The printed layer-bottom depths are truncated to whole millimetres. [Carbon total update](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cbn_zhang2.f90#L1016-L1026), [Carbon transport update](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/nut_orgnc2.f90#L145-L179), [Snapshot writes](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/soil_nutcarb_write_historical.f90#L76-L117)

## Snapshot dates

The beginning row's month, day of month, and year come from the configured start date. The opener writes this row before the simulation sets `time%day`, so `jday` still has its default of zero. The ending snapshot writes the final simulation date in all four date columns. [Time input](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/time_read.f90#L28-L43), [day default](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/time_module.f90#L18), [simulation start](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/time_control.f90#L88-L101).

See [Modern HRU Soil Snapshots](../carbon/modern-hru-soil-snap.md) for the separate modern diagnostic.
