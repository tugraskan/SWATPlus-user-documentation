---
description: "Record name"
---

# name

**Code reference:** `w_temp(ich_temp)%name` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/channel_data_module.f90#L170)).

Record name (`character(len=13)`), read into `w_temp(1:)` by [`ch_read_temp.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ch_read_temp.f90#L54). Because [`ch_temp.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ch_temp.f90#L189-L200) reads only `w_temp(0)`, no channel lookup uses `name`.
