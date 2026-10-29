# Reservoir

The printing of reservoir output is controlled by entering "y" or "n" in the _reservoir_ line in [print.prt](../../introduction-1/simulation-settings/print.prt). In addition, a basin average of all reservoirs can be printed by entering "y" in the _basin\_res_ line in [print.prt](../../introduction-1/simulation-settings/print.prt). Reservoir output can be printed at daily, monthly, yearly, and average annual time steps. The names of the reservoir output files are as follows:&#x20;

* reservoir\_day.txt
* reservoir\_mon.txt
* reservoir\_yr.txt
* reservoir\_aa.txt
* basin\_res\_day.txt
* basin\_res\_mon.txt
* basin\_res\_yr.txt
* basin\_res\_aa.txt

| Field      | Description                                                     | Unit |
| ---------- | --------------------------------------------------------------- | ---- |
| [jday](jday.md)       | Julian Day                                                      | n/a  |
| [mon](mon.md)        | Month                                                           | n/a  |
| [day](day.md)        | Day of the month                                                | n/a  |
| [yr](yr.md)         | Year                                                            | n/a  |
| [unit](unit.md)       | ID of the object                                                | n/a  |
| [gis\_id](gis_id.md)    | Object ID in GIS                                                | n/a  |
| [name](name.md)       | Name of the object or SWAT+ setup (basin outputs)               | n/a  |
| [area](area.md)       | Area of the reservoir                                           | ha   |
| [precip](precip.md)     | Precipitation on the reservoir surface                          | ha-m |
| [evap](evap.md)       | Evaporation from the reservoir surface                          | ha-m |
| [seep](seep.md)       | Seepage out of the reservoir bottom                             | ha-m |
| [flo\_stor](flo_stor.md)  | Flow storage in the reservoir                                   | m3   |
| [sed\_stor](sed_stor.md)  | Sediment storage in the reservoir                               | tons |
| [orgn\_stor](orgn_stor.md) | Organic nitrogen storage in the reservoir                       | kg   |
| [sedp\_stor](sedp_stor.md) | Sediment phosphorus storage in the reservoir                    | kg   |
| [no3\_stor](no3_stor.md)  | Nitrate nitrogen storage in the reservoir                       | kg   |
| [solp\_stor](solp_stor.md) | Soluble phosphorus storage in the reservoir                     | kg   |
| [chla\_stor](chla_stor.md) | Chlorophyll-a storage in the reservoir                          | kg   |
| [nh3\_stor](nh3_stor.md)  | Ammonia nitrogen storage in the reservoir                       | kg   |
| [no2\_stor](no2_stor.md)  | Nitrite nitrogen storage in the reservoir                       | kg   |
| [cbod\_stor](cbod_stor.md) | Carbonaceous Biochemical Oxygen Demand storage in the reservoir | kg   |
| [dox\_stor](dox_stor.md)  | Dissolved oxygen storage in the reservoir                       | kg   |
| [san\_stor](san_stor.md)  | Sand storage in the reservoir                                   | tons |
| [sil\_stor](sil_stor.md)  | Silt storage in the reservoir                                   | tons |
| [cla\_stor](cla_stor.md)  | Clay storage in the reservoir                                   | tons |
| [sag\_stor](sag_stor.md)  | Small aggregate storage in the reservoir                        | tons |
| [lag\_stor](lag_stor.md)  | Large aggregate storage in the reservoir                        | tons |
| [grv\_stor](grv_stor.md)  | Gravel storage in the reservoir                                 | tons |
| [null](null.md)       |                                                                 |      |
| [flo\_in](flo_in.md)    | Flow into the reservoir                                         | m3   |
| [sed\_in](sed_in.md)    | Sediment entering the reservoir                                 | tons |
| [orgn\_in](orgn_in.md)   | Organic nitrogen entering the reservoir                         | kg   |
| [sedp\_in](sedp_in.md)   | Sediment phosphorus entering the reservoir                      | kg   |
| [no3\_in](no3_in.md)    | Nitrate nitrogen entering the reservoir                         | kg   |
| [solp\_in](solp_in.md)   | Soluble phosphorus entering the reservoir                       | kg   |
| [chla\_in](chla_in.md)   | Chlorophyll-a entering the reservoir                            | kg   |
| [nh3\_in](nh3_in.md)    | Ammonia nitrogen entering the reservoir                         | kg   |
| [no2\_in](no2_in.md)    | Nitrite nitrogen entering the reservoir                         | kg   |
| [cbod\_in](cbod_in.md)   | Carbonaceous Biochemical Oxygen Demand entering the reservoir   | kg   |
| [dox\_in](dox_in.md)    | Dissolved oxygen entering the reservoir                         | kg   |
| [san\_in](san_in.md)    | Sand entering the reservoir                                     | tons |
| [sil\_in](sil_in.md)    | Silt entering the reservoir                                     | tons |
| [cla\_in](cla_in.md)    | Clay entering the reservoir                                     | tons |
| [sag\_in](sag_in.md)    | Small aggregates entering the reservoir                         | tons |
| [lag\_in](lag_in.md)    | Large aggregates entering the reservoir                         | tons |
| [grv\_in](grv_in.md)    | Gravel entering the reservoir                                   | tons |
| [null](null.md)       |                                                                 |      |
| [flo\_out](flo_out.md)   | Flow out of the reservoir                                       | m3   |
| [sed\_out](sed_out.md)   | Sediment leaving the reservoir                                  | tons |
| [orgn\_out](orgn_out.md)  | Organic nitrogen leaving the reservoir                          | kg   |
| [sedp\_out](sedp_out.md)  | Sediment phosphorus leaving the reservoir                       | kg   |
| [no3\_out](no3_out.md)   | Nitrate nitrogen leaving the reservoir                          | kg   |
| [solp\_out](solp_out.md)  | Soluble phosphorus leaving the reservoir                        | kg   |
| [chla\_out](chla_out.md)  | Chlorophyll-a leaving the reservoir                             | kg   |
| [nh3\_out](nh3_out.md)   | Ammonia nitrogen leaving the reservoir                          | kg   |
| [no2\_out](no2_out.md)   | Nitrite nitrogen leaving the reservoir                          | kg   |
| [cbod\_out](cbod_out.md)  | Carbonaceous Biochemical Oxygen Demand leaving the reservoir    | kg   |
| [dox\_out](dox_out.md)   | Dissolved oxygen leaving the reservoir                          | kg   |
| [san\_out](san_out.md)   | Sand leaving the reservoir                                      | tons |
| [sil\_out](sil_out.md)   | Silt leaving the reservoir                                      | tons |
| [cla\_out](cla_out.md)   | Clay leaving the reservoir                                      | tons |
| [sag\_out](sag_out.md)   | Small aggregates leaving the reservoir                          | tons |
| [lag\_out](lag_out.md)   | Large aggregates leaving the reservoir                          | tons |
| [grv\_out](grv_out.md)   | Gravel leaving the reservoir                                    | tons |
| [null](null.md)       |                                                                 |      |
