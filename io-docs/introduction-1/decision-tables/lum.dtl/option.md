# option

**Code reference:** `dtbl_lum(i)%act(iac)%option` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/conditional_module.f90#L21)).

Text selector whose meaning follows the [action type](act_typ.md). An unmatched name gives no warning.

| Action | Option |
| ------ | ------ |
| `plant`, `harvest`, `harvest_kill`, `kill` | Plant name in the HRU's community; `harvest`, `harvest_kill`, and `kill` also accept `all` |
| `irrigate`, `irr_demand` | [irr.ops](../../management-practices/irr.ops/README.md) record |
| `fertilize`, `fert_future` | Fertilizer name |
| `manure_demand` | Chemical application record |
| `till` | Tillage name |
| `pest_apply` | Pesticide name |
| `graze`, `burn`, `puddle` | Grazing, fire, or puddle operation record |
| `weir_height` | `wet` for an HRU wetland; anything else sets a reservoir weir |
| `hru_fr_update` | Replacement landscape-unit element file |
| `cn_update` | Type of change applied to the curve number |

For `plant`, `harvest`, and `harvest_kill`, the entry is replaced by a crop named on the management schedule when the schedule's auto-operation name is `pl_hv_summer1` or `pl_hv_winter1` (first crop) or `pl_hv_summer2` (crop of the current rotation year). [`actions.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/actions.f90#L460-L468) · [`actions.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/actions.f90#L525-L533)

Sources: [`dtbl_lum_read.f90`](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/dtbl_lum_read.f90#L114-L242) · [`actions.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/actions.f90#L537-L537) · [`actions.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/actions.f90#L966-L969)
