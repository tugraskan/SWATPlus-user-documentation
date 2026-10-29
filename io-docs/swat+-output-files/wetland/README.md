# Wetland

Wetland output is available at daily, monthly, yearly, and average-annual intervals as `wetland_day`, `wetland_mon`, `wetland_yr`, and `wetland_aa`, with `.txt` and `.csv` variants.

The wetland files share the printed schema used by reservoir output: the identifying columns `jday`, `mon`, `day`, `yr`, `unit`, `gis_id`, and `name`; the state columns `area`, `precip`, `evap`, `seep`, and `flo_stor`; then stored, incoming, and outgoing constituent blocks.

| Field | Description | Unit |
| --- | --- | --- |
| [area](area.md) | Wetland surface area | ha |
| [precip](precip.md), [evap](evap.md), [seep](seep.md) | Precipitation, evaporation, and seepage volumes | ha-m |
| [flo_stor](flo_stor.md) | Water stored in the wetland | m3 |
| [`sed_stor`](sed_stor.md), [`san_stor`](san_stor.md), [`sil_stor`](sil_stor.md), [`cla_stor`](cla_stor.md), [`sag_stor`](sag_stor.md), [`lag_stor`](lag_stor.md), [`grv_stor`](grv_stor.md) | Stored sediment and particle-size classes | tons |
| [`orgn_stor`](orgn_stor.md), [`sedp_stor`](sedp_stor.md), [`no3_stor`](no3_stor.md), [`solp_stor`](solp_stor.md), [`chla_stor`](chla_stor.md), [`nh3_stor`](nh3_stor.md), [`no2_stor`](no2_stor.md), [`cbod_stor`](cbod_stor.md), [`dox_stor`](dox_stor.md) | Stored nutrients and water-quality constituents | kg |
| [`flo_in`](flo_in.md), [`flo_out`](flo_out.md) | Incoming and outgoing water | m3 |
| [`sed_in`](sed_in.md), [`san_in`](san_in.md), [`sil_in`](sil_in.md), [`cla_in`](cla_in.md), [`sag_in`](sag_in.md), [`lag_in`](lag_in.md), [`grv_in`](grv_in.md); [`sed_out`](sed_out.md), [`san_out`](san_out.md), [`sil_out`](sil_out.md), [`cla_out`](cla_out.md), [`sag_out`](sag_out.md), [`lag_out`](lag_out.md), [`grv_out`](grv_out.md) | Incoming and outgoing sediment and particle-size classes | tons |
| [`orgn_in`](orgn_in.md), [`sedp_in`](sedp_in.md), [`no3_in`](no3_in.md), [`solp_in`](solp_in.md), [`chla_in`](chla_in.md), [`nh3_in`](nh3_in.md), [`no2_in`](no2_in.md), [`cbod_in`](cbod_in.md), [`dox_in`](dox_in.md); [`orgn_out`](orgn_out.md), [`sedp_out`](sedp_out.md), [`no3_out`](no3_out.md), [`solp_out`](solp_out.md), [`chla_out`](chla_out.md), [`nh3_out`](nh3_out.md), [`no2_out`](no2_out.md), [`cbod_out`](cbod_out.md), [`dox_out`](dox_out.md) | Incoming and outgoing nutrients and water-quality constituents | kg |
| [null](null.md) | Printed separator after each storage, inflow, and outflow block | n/a |

Wetland salt and conservative-constituent files have separate schemas; see [Salt Outputs](../salt-outputs/README.md) and [Conservative Constituents](../conservative-constituents/README.md).
