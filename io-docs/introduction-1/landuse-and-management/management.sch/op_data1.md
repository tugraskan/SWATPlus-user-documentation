---
description: Operation data 1 (op_char)
---

# op\_data1

**Code reference:** `sched(isched)%mgt_ops(iop)%op_char` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_operations_module.f90#L165), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/read_mgtops.f90#L31)).

Character string (`len=40`, default `""`) supplying the primary target name or parameter option for the operation in [`read_mgtops.f90`](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/read_mgtops.f90#L41-L175) and [`mgt_sched.f90`](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/mgt_sched.f90#L84-L624).

| Operation | Use of `op_data1` |
| --------- | ----------------- |
| `pcom` | Plant community name in [**plant.ini**](../plant.ini/README.md) ([`read_mgtops.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/read_mgtops.f90#L45)) |
| `plnt` | Plant name in the HRU's [**plant.ini**](../plant.ini/README.md) community and [**plants.plt**](../../databases/plants.plt/README.md) ([`mgt_sched.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_sched.f90#L93)) |
| `harv`, `hvkl`, `kill` | Plant name in [**plant.ini**](../plant.ini/README.md) community, or `"all"` to apply to all growing plants ([`mgt_sched.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_sched.f90#L160), [`#L248`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_sched.f90#L248), [`#L271`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_sched.f90#L271)) |
| `till`, `pudl` | Tillage implement name in [**tillage.til**](../../databases/tillage.til/README.md) ([`read_mgtops.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/read_mgtops.f90#L88), [`mgt_sched.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_sched.f90#L603)) |
| `irrm`, `irrp`, `irpm` | Irrigation operation name in [**irr.ops**](../../management-practices/irr.ops/README.md) ([`read_mgtops.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/read_mgtops.f90#L97)) |
| `fert` | Fertilizer name in [**fertilizer.frt**](../../databases/fertilizer.frt/README.md) ([`read_mgtops.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/read_mgtops.f90#L110)) |
| `manu` | Manure name in [**manure\_db.frt**](../../databases/manure_db.frt/README.md) ([`read_mgtops.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/read_mgtops.f90#L130)) |
| `pest` | Pesticide name in [**pesticide.pes**](../../databases/pesticide.pes/README.md) and HRU pesticide community ([`read_mgtops.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/read_mgtops.f90#L146), [`mgt_sched.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_sched.f90#L421)) |
| `graz` | Grazing operation name in [**graze.ops**](../../management-practices/graze.ops/README.md) ([`read_mgtops.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/read_mgtops.f90#L161)) |
| `cnup` | Change type (`absval`, `abschg`, or `pctchg`) passed to `chg_par` ([`mgt_sched.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_sched.f90#L457)) |
| `burn` | Fire operation name in [**fire.ops**](../../management-practices/fire.ops/README.md) ([`read_mgtops.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/read_mgtops.f90#L169)) |
| `swep` | Street sweeping operation name in [**sweep.ops**](../../management-practices/sweep.ops/README.md) ([`read_mgtops.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/read_mgtops.f90#L177)) |
| `weir` | Weir record name in [**weir.res**](../../reservoirs/weir.res/README.md) ([`mgt_sched.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_sched.f90#L519)) |
| `mons`, `dwm`, `skip` | Not used (enter `"null"`) |
