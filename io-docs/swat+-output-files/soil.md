# Soil

The legacy carbon diagnostics can write `hru_begsim_soil_prop.txt/.csv` and `hru_endsim_soil_prop.txt/.csv`. They use the same printed schema and write one row per soil layer, allowing beginning- and end-of-simulation properties to be compared.

These files print the field header but no units row. The units below follow the corresponding soil-property definitions in the source.

| Field | Description | Unit |
| --- | --- | --- |
| [freq](soil/freq.md) | Report marker | n/a |
| [soil_name](soil/soil_name.md) | Soil name | n/a |
| [soil_lyr](soil/soil_lyr.md) | Soil-layer number | n/a |
| [soil_depth](soil/soil_depth.md) | Depth to the bottom of the layer | mm |
| [jday](soil/jday.md), [mon](soil/mon.md), [day](soil/day.md), [yr](soil/yr.md) | Reporting date | n/a |
| [unit](soil/unit.md), [gis_id](soil/gis_id.md), [name](soil/name.md) | HRU identifiers and name | n/a |
| [bd](soil/bd.md) | Bulk density | Mg/m3 |
| [awc](soil/awc.md) | Available water capacity | mm/mm |
| [soil_k](soil/soil_k.md) | Saturated hydraulic conductivity | mm/h |
| [carbon](soil/carbon.md) | Soil carbon | percent |
| [clay](soil/clay.md), [silt](soil/silt.md), [sand](soil/sand.md), [rock](soil/rock.md) | Soil particle and rock fractions | percent |
| [alb](soil/alb.md) | Soil albedo | fraction |
| [usle_k](soil/usle_k.md) | USLE soil erodibility factor | n/a |
| [ec](soil/ec.md) | Electrical conductivity | dS/m |
| [caco3](soil/caco3.md) | Calcium carbonate | percent |
| [ph](soil/ph.md) | Soil pH | n/a |

These files are conditional diagnostics, not the normal daily HRU soil-water report. Other layered carbon and nutrient files are listed under [Carbon](carbon/README.md).
