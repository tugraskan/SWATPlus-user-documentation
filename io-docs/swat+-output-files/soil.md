# Soil

The legacy carbon diagnostics can write `hru_begsim_soil_prop.txt/.csv` and `hru_endsim_soil_prop.txt/.csv`. They use the same printed schema and write one row per soil layer, allowing beginning- and end-of-simulation properties to be compared.

These files print the field header but no units row. The units below follow the corresponding soil-property definitions in the source.

| Field | Description | Unit |
| --- | --- | --- |
| freq | Report marker | n/a |
| soil_name | Soil name | n/a |
| soil_lyr | Soil-layer number | n/a |
| soil_depth | Depth to the bottom of the layer | mm |
| jday, mon, day, yr | Reporting date | n/a |
| unit, gis_id, name | HRU identifiers and name | n/a |
| bd | Bulk density | Mg/m3 |
| awc | Available water capacity | mm/mm |
| soil_k | Saturated hydraulic conductivity | mm/h |
| carbon | Soil carbon | percent |
| clay, silt, sand, rock | Soil particle and rock fractions | percent |
| alb | Soil albedo | fraction |
| usle_k | USLE soil erodibility factor | n/a |
| ec | Electrical conductivity | dS/m |
| caco3 | Calcium carbonate | percent |
| ph | Soil pH | n/a |

These files are conditional diagnostics, not the normal daily HRU soil-water report. Other layered carbon and nutrient files are listed under [Carbon](carbon/README.md).
