---
description: Operation data 2 (op_plant)
---

# op\_data2

**Code reference:** `sched(isched)%mgt_ops(iop)%op_plant` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_operations_module.f90#L166), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/read_mgtops.f90#L32)).

Character string (`len=40`, default `""`) supplying secondary operation data or file pointers in [`read_mgtops.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/read_mgtops.f90#L64-L157) and [`mgt_sched.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_sched.f90#L103-L595).

| Operation | Use of `op_data2` |
| --------- | ----------------- |
| `plnt` | Optional transplant parameter set name in [**transplant.ops**](../transplant.ops/README.md); applied when [op\_data3](op_data3.md) `> 1e-6` ([`read_mgtops.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/read_mgtops.f90#L64), [`mgt_sched.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_sched.f90#L101-L110)) |
| `harv`, `hvkl` | Harvest operation name in [**harv.ops**](../../management-practices/harv.ops/README.md) ([`read_mgtops.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/read_mgtops.f90#L72), [`#L80`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/read_mgtops.f90#L80)) |
| `fert`, `manu`, `pest` | Chemical application method name in [**chem\_app.ops**](../../management-practices/chem_app.ops/README.md) ([`read_mgtops.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/read_mgtops.f90#L121), [`#L129`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/read_mgtops.f90#L137), [`#L145`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/read_mgtops.f90#L153)) |
| `irrp` | Paddy irrigation water source (`cha`, `res`, `aqu`, or `unlim`) ([`mgt_sched.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_sched.f90#L530)) |
| `pudl` | Puddling parameter set name in [**puddle.ops**](../puddle.ops/README.md) ([`mgt_sched.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_sched.f90#L592)) |
| All other operations | Not used (enter `"null"`) |
