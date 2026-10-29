# Soil

The legacy carbon diagnostics can write `hru_begsim_soil_prop.txt/.csv` and `hru_endsim_soil_prop.txt/.csv`. They use the same printed schema and write one row per soil layer, allowing beginning- and end-of-simulation properties to be compared.

These files print the field header but no units row. The units below follow the corresponding soil-property definitions in the source.

| Field | Description | Unit |
| --- | --- | --- |
| [freq](freq.md) | Report marker | n/a |
| [soil_name](soil_name.md) | Soil name | n/a |
| [soil_lyr](soil_lyr.md) | Soil-layer number | n/a |
| [soil_depth](soil_depth.md) | Depth to the bottom of the layer | mm |
| [jday](jday.md) | Day of year | n/a |
| [mon](mon.md) | Month | n/a |
| [day](day.md) | Day of month | n/a |
| [yr](yr.md) | Calendar year | n/a |
| [unit](unit.md) | Object identifier | n/a |
| [gis_id](gis_id.md) | GIS identifier | n/a |
| [name](name.md) | Object name | n/a |
| [bd](bd.md) | Bulk density | Mg/m3 |
| [awc](awc.md) | Available water capacity | mm/mm |
| [soil_k](soil_k.md) | Saturated hydraulic conductivity | mm/h |
| [carbon](carbon.md) | Soil carbon | percent |
| [clay](clay.md) | Soil clay fraction | percent |
| [silt](silt.md) | Soil silt fraction | percent |
| [sand](sand.md) | Soil sand fraction | percent |
| [rock](rock.md) | Soil rock fraction | percent |
| [alb](alb.md) | Soil albedo | fraction |
| [usle_k](usle_k.md) | USLE soil erodibility factor | n/a |
| [ec](ec.md) | Electrical conductivity | dS/m |
| [caco3](caco3.md) | Calcium carbonate | percent |
| [ph](ph.md) | Soil pH | n/a |

These files are conditional diagnostics, not the normal daily HRU soil-water report. Other layered carbon and nutrient files are listed under [Carbon](../carbon/README.md).
