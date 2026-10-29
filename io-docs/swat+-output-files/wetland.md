# Wetland

Wetland output is available at daily, monthly, yearly, and average-annual intervals as `wetland_day`, `wetland_mon`, `wetland_yr`, and `wetland_aa`, with `.txt` and `.csv` variants.

The wetland files share the printed schema used by reservoir output: the identifying columns `jday`, `mon`, `day`, `yr`, `unit`, `gis_id`, and `name`; the state columns `area`, `precip`, `evap`, `seep`, and `flo_stor`; then stored, incoming, and outgoing constituent blocks.

| Field | Description | Unit |
| --- | --- | --- |
| [area](wetland/area.md) | Wetland surface area | ha |
| [precip](wetland/precip.md), [evap](wetland/evap.md), [seep](wetland/seep.md) | Precipitation, evaporation, and seepage volumes | ha-m |
| [flo_stor](wetland/flo_stor.md) | Water stored in the wetland | m3 |
| [`sed_stor`](wetland/sed_stor.md), [`san_stor`](wetland/san_stor.md), [`sil_stor`](wetland/sil_stor.md), [`cla_stor`](wetland/cla_stor.md), [`sag_stor`](wetland/sag_stor.md), [`lag_stor`](wetland/lag_stor.md), [`grv_stor`](wetland/grv_stor.md) | Stored sediment and particle-size classes | tons |
| [`orgn_stor`](wetland/orgn_stor.md), [`sedp_stor`](wetland/sedp_stor.md), [`no3_stor`](wetland/no3_stor.md), [`solp_stor`](wetland/solp_stor.md), [`chla_stor`](wetland/chla_stor.md), [`nh3_stor`](wetland/nh3_stor.md), [`no2_stor`](wetland/no2_stor.md), [`cbod_stor`](wetland/cbod_stor.md), [`dox_stor`](wetland/dox_stor.md) | Stored nutrients and water-quality constituents | kg |
| [`flo_in`](wetland/flo_in.md), [`flo_out`](wetland/flo_out.md) | Incoming and outgoing water | m3 |
| [`sed_in`](wetland/sed_in.md), [`san_in`](wetland/san_in.md), [`sil_in`](wetland/sil_in.md), [`cla_in`](wetland/cla_in.md), [`sag_in`](wetland/sag_in.md), [`lag_in`](wetland/lag_in.md), [`grv_in`](wetland/grv_in.md); [`sed_out`](wetland/sed_out.md), [`san_out`](wetland/san_out.md), [`sil_out`](wetland/sil_out.md), [`cla_out`](wetland/cla_out.md), [`sag_out`](wetland/sag_out.md), [`lag_out`](wetland/lag_out.md), [`grv_out`](wetland/grv_out.md) | Incoming and outgoing sediment and particle-size classes | tons |
| [`orgn_in`](wetland/orgn_in.md), [`sedp_in`](wetland/sedp_in.md), [`no3_in`](wetland/no3_in.md), [`solp_in`](wetland/solp_in.md), [`chla_in`](wetland/chla_in.md), [`nh3_in`](wetland/nh3_in.md), [`no2_in`](wetland/no2_in.md), [`cbod_in`](wetland/cbod_in.md), [`dox_in`](wetland/dox_in.md); [`orgn_out`](wetland/orgn_out.md), [`sedp_out`](wetland/sedp_out.md), [`no3_out`](wetland/no3_out.md), [`solp_out`](wetland/solp_out.md), [`chla_out`](wetland/chla_out.md), [`nh3_out`](wetland/nh3_out.md), [`no2_out`](wetland/no2_out.md), [`cbod_out`](wetland/cbod_out.md), [`dox_out`](wetland/dox_out.md) | Incoming and outgoing nutrients and water-quality constituents | kg |
| [null](wetland/null.md) | Printed separator after each storage, inflow, and outflow block | n/a |

Wetland salt and conservative-constituent files have separate schemas; see [Salt Outputs](salt-outputs.md) and [Conservative Constituents](conservative-constituents.md).
