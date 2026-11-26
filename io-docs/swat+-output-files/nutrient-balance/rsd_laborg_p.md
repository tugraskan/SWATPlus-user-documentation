---
description: "Surface-residue phosphorus mineralization diagnostic cleared before output"
---

# rsd_laborg_p

**Code reference:** `hnb_d(j)%rsd_laborg_p` in the HRU record ([writer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_output.f90#L73)); matching component in basin and LSU records.

In the static carbon route (`cswat = 0`), `rsd_decomp` adds 80% of decomposed surface-residue P to labile P and 20% to active organic P. It adds only `0.8 * decomp%p` to the temporary diagnostic. The very next routine, `nut_nminrl`, clears that diagnostic before it reaches the output. The SWAT-C residue routines also leave this legacy field at zero. The column therefore gives no measure of the actual mineralized amount in these source paths. [surface-residue pools](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/rsd_decomp.f90#L118-L127), [call order](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_control.f90#L388-L404), [legacy reset](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/nut_nminrl.f90#L82-L88), [SWAT-C reset](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cbn_rsd_transfer.f90#L58-L64).

**Unit:** kg P/ha.

[Back to the output table](README.md).
