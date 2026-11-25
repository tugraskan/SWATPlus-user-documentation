---
description: "Die-off factor for persistent bacteria on foliage"
---

# do_plnt

**Code reference:** `path_db(ibac)%do_plnt` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/pathogen_data_module.f90#L14)).

Die-off rate (1/day at 20 °C) on foliage. The net rate is `do_plnt − gr_plnt` ([`path_ls_process.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/path_ls_process.f90#L49-L56)).
