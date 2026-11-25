---
description: Type of management operation
---

# op\_typ

**Code reference:** `sched(isched)%mgt_ops(iop)%op` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_operations_module.f90#L145), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/read_mgtops.f90#L27)).

Four-character operation code (`character(len=40)`, default `""`) selecting the scheduled management action in [`read_mgtops.f90`](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/read_mgtops.f90#L41-L175) and [`mgt_sched.f90`](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/mgt_sched.f90#L84-L624).

| Code   | Operation                      | Description |
| ------ | ------------------------------ | ----------- |
| `plnt` | Planting / transplant          | Starts growth of the target plant; optionally calls transplanting when [op\_data3](op_data3.md) `> 1e-6` ([`mgt_sched.f90`](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/mgt_sched.f90#L86-L135)) |
| `mons` | Monsoon initiation window      | Sets or ends the moisture-triggered monsoon window for `moisture_gro` plants ([`mgt_sched.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_sched.f90#L137-L152)) |
| `harv` | Harvest only                   | Harvests yield using the specified `harv.ops` rule without killing the plant ([`mgt_sched.f90`](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/mgt_sched.f90#L154-L242)) |
| `hvkl` | Harvest and kill               | Harvests yield and converts remaining plant biomass to surface residue ([`mgt_sched.f90`](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/mgt_sched.f90#L265-L341)) |
| `kill` | Kill                           | Kills the plant and converts biomass to surface residue ([`mgt_sched.f90`](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/mgt_sched.f90#L244-L263)) |
| `till` | Tillage                        | Mixes upper soil layers and redistributes residue/nutrients ([`mgt_sched.f90`](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/mgt_sched.f90#L343-L356)) |
| `irrm` | Scheduled irrigation           | Applies a fixed irrigation event from `irr.ops` ([`mgt_sched.f90`](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/mgt_sched.f90#L358-L373)) |
| `irrp` | Paddy ponding irrigation       | Starts, adjusts, or stops continuous rice-paddy ponding irrigation ([`mgt_sched.f90`](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/mgt_sched.f90#L528-L568)) |
| `irpm` | Rice-paddy scheduled irrigation | Applies a scheduled rice-paddy irrigation event ([`mgt_sched.f90`](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/mgt_sched.f90#L571-L586); note [`read_mgtops.f90`](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/read_mgtops.f90#L41-L175) has no `irpm` crosswalk case) |
| `fert` | Fertilizer application         | Adds mineral/organic fertilizer to soil or standing paddy water ([`mgt_sched.f90`](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/mgt_sched.f90#L375-L400)) |
| `manu` | Manure application             | Applies manure from `manure_db.frt` ([`mgt_sched.f90`](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/mgt_sched.f90#L402-L415)) |
| `pest` | Pesticide application          | Applies pesticide scaled by `chem_app.ops` efficiency ([`mgt_sched.f90`](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/mgt_sched.f90#L417-L437)) |
| `graz` | Grazing                        | Starts grazing for the specified number of days ([`mgt_sched.f90`](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/mgt_sched.f90#L439-L451)) |
| `cnup` | Curve number update            | Updates HRU `cn2` using `chg_par` clamped to `35–95` ([`mgt_sched.f90`](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/mgt_sched.f90#L453-L464)) |
| `burn` | Burning                        | Executes a fire/burn operation from `fire.ops` ([`mgt_sched.f90`](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/mgt_sched.f90#L466-L476)) |
| `swep` | Street sweeping                | Sweeps urban impervious build-up using `sweep.ops` ([`mgt_sched.f90`](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/mgt_sched.f90#L478-L488)) |
| `dwm`  | Drainage water management      | Adjusts HRU tile drain depth (`mm`) ([`mgt_sched.f90`](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/mgt_sched.f90#L490-L505)) |
| `weir` | Weir height adjustment         | Sets paddy/wetland weir height and principal spillway volume ([`mgt_sched.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_sched.f90#L508-L527)) |
| `pudl` | Puddling                       | Applies rice-paddy puddling (`puddle.ops`) and wet/dry tillage ([`mgt_sched.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_sched.f90#L589-L620)) |
| `skip` | Skip to end of year            | Advances rotation year at read time and skips remaining operations for the year ([`read_mgtops.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/read_mgtops.f90#L39), [`mgt_sched.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_sched.f90#L622-L623)) |
| `pcom` | Plant community lookup         | Crosswalked against `plant.ini` in [`read_mgtops.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/read_mgtops.f90#L43-L49), but has no execution branch in [`mgt_sched.f90`](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/mgt_sched.f90#L84-L624) |
