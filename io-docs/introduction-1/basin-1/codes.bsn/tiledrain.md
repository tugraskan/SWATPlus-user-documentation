---
description: Tile drainage equation code
---

# tiledrain

**Code reference:** `bsn_cc%tdrn` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_module.f90#L57), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_read_cc.f90#L24)).

Selects the tile-drainage flow equation in [`swr_percmain.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/swr_percmain.f90#L186-L192) when tile drainage is active on an HRU (struct default `0`).

| Code | Option |
| ---- | ------ |
| 0 | Simulate tile flow using drawdown-days equation (`swr_origtile`) |
| 1 | Simulate tile flow using DRAINMOD equations (`swr_drains`) |
