---
description: File pointer
---

# fp

**Code reference:** `dtbl_lum(i)%act(iac)%file_pointer` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/conditional_module.f90#L25)).

Record name or selector used by some actions; enter `null` otherwise. A name that matches no record gives no warning.

| Action | Entry |
| ------ | ----- |
| `harvest`, `harvest_kill` | [harv.ops](../../management-practices/harv.ops/) record |
| `fertilize`, `fert_future`, `pest_apply` | [chem_app.ops](../../management-practices/chem_app.ops/) record |
| `plant` | Transplant record, optional |
| `lu_change` | `landuse.lum` record |
| `snow_change` | `snow.sno` record |
| `impound_on` | `wetland.wet` record |
| `tile_install`, `septic_install`, `fstrip_install`, `grassww_install`, `user_def_bmp` | Structure or BMP record |
| `irr_demand` | `unlim` to apply water directly |
| `stripcrop`, `terrace` | `pasture` or `sod_outlet` adjustment |
| `hru_fr_update` | Replacement routing-unit element file |

Sources: [`dtbl_lum_read.f90`](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/dtbl_lum_read.f90#L105-L258) · [`actions.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/actions.f90#L148-L152) · [`actions.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/actions.f90#L1109-L1126)
