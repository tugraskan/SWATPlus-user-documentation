# Wetland

Wetland output is available at daily, monthly, yearly, and average-annual intervals as `wetland_day`, `wetland_mon`, `wetland_yr`, and `wetland_aa`, with `.txt` and `.csv` variants.

The wetland files share the printed schema used by reservoir output: the identifying columns `jday`, `mon`, `day`, `yr`, `unit`, `gis_id`, and `name`; the state columns `area`, `precip`, `evap`, `seep`, and `flo_stor`; then stored, incoming, and outgoing constituent blocks.

| Field | Description | Unit |
| --- | --- | --- |
| [area](area.md) | Wetland surface area | ha |
| [precip](precip.md) | Precipitation volume | ha-m |
| [evap](evap.md) | Evaporation volume | ha-m |
| [seep](seep.md) | Seepage volume | ha-m |
| [flo_stor](flo_stor.md) | Water stored in the wetland | m3 |
| [`sed_stor`](sed_stor.md) | Stored sediment | tons |
| [`san_stor`](san_stor.md) | Stored sand | tons |
| [`sil_stor`](sil_stor.md) | Stored silt | tons |
| [`cla_stor`](cla_stor.md) | Stored clay | tons |
| [`sag_stor`](sag_stor.md) | Stored small aggregates | tons |
| [`lag_stor`](lag_stor.md) | Stored large aggregates | tons |
| [`grv_stor`](grv_stor.md) | Stored gravel | tons |
| [`orgn_stor`](orgn_stor.md) | Stored organic nitrogen | kg |
| [`sedp_stor`](sedp_stor.md) | Stored sediment-associated phosphorus | kg |
| [`no3_stor`](no3_stor.md) | Stored nitrate nitrogen | kg |
| [`solp_stor`](solp_stor.md) | Stored soluble phosphorus | kg |
| [`chla_stor`](chla_stor.md) | Stored chlorophyll a | kg |
| [`nh3_stor`](nh3_stor.md) | Stored ammonia | kg |
| [`no2_stor`](no2_stor.md) | Stored nitrite | kg |
| [`cbod_stor`](cbod_stor.md) | Stored carbonaceous biochemical oxygen demand | kg |
| [`dox_stor`](dox_stor.md) | Stored dissolved oxygen | kg |
| [`flo_in`](flo_in.md) | Incoming water volume | m3 |
| [`flo_out`](flo_out.md) | Outgoing water volume | m3 |
| [`sed_in`](sed_in.md) | Incoming sediment | tons |
| [`san_in`](san_in.md) | Incoming sand | tons |
| [`sil_in`](sil_in.md) | Incoming silt | tons |
| [`cla_in`](cla_in.md) | Incoming clay | tons |
| [`sag_in`](sag_in.md) | Incoming small aggregates | tons |
| [`lag_in`](lag_in.md) | Incoming large aggregates | tons |
| [`grv_in`](grv_in.md) | Incoming gravel | tons |
| [`sed_out`](sed_out.md) | Outgoing sediment | tons |
| [`san_out`](san_out.md) | Outgoing sand | tons |
| [`sil_out`](sil_out.md) | Outgoing silt | tons |
| [`cla_out`](cla_out.md) | Outgoing clay | tons |
| [`sag_out`](sag_out.md) | Outgoing small aggregates | tons |
| [`lag_out`](lag_out.md) | Outgoing large aggregates | tons |
| [`grv_out`](grv_out.md) | Outgoing gravel | tons |
| [`orgn_in`](orgn_in.md) | Incoming organic nitrogen | kg |
| [`sedp_in`](sedp_in.md) | Incoming sediment-associated phosphorus | kg |
| [`no3_in`](no3_in.md) | Incoming nitrate nitrogen | kg |
| [`solp_in`](solp_in.md) | Incoming soluble phosphorus | kg |
| [`chla_in`](chla_in.md) | Incoming chlorophyll a | kg |
| [`nh3_in`](nh3_in.md) | Incoming ammonia | kg |
| [`no2_in`](no2_in.md) | Incoming nitrite | kg |
| [`cbod_in`](cbod_in.md) | Incoming carbonaceous biochemical oxygen demand | kg |
| [`dox_in`](dox_in.md) | Incoming dissolved oxygen | kg |
| [`orgn_out`](orgn_out.md) | Outgoing organic nitrogen | kg |
| [`sedp_out`](sedp_out.md) | Outgoing sediment-associated phosphorus | kg |
| [`no3_out`](no3_out.md) | Outgoing nitrate nitrogen | kg |
| [`solp_out`](solp_out.md) | Outgoing soluble phosphorus | kg |
| [`chla_out`](chla_out.md) | Outgoing chlorophyll a | kg |
| [`nh3_out`](nh3_out.md) | Outgoing ammonia | kg |
| [`no2_out`](no2_out.md) | Outgoing nitrite | kg |
| [`cbod_out`](cbod_out.md) | Outgoing carbonaceous biochemical oxygen demand | kg |
| [`dox_out`](dox_out.md) | Outgoing dissolved oxygen | kg |
| [null](null.md) | Printed separator after each storage, inflow, and outflow block | n/a |

Wetland salt and conservative-constituent files have separate schemas; see [Salt Outputs](../salt-outputs/README.md) and [Conservative Constituents](../conservative-constituents/README.md).
