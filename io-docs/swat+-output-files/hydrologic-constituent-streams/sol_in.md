---
description: "Incoming heading over a configured constituent scalar"
---

# sol_in

The dormant incoming header places `sol_in` at position 13. At that position the write list supplies configured constituent 1. The tail contains one scalar per configured constituent. The source writes the scalar directly from the constituent record, so its unit follows that record. [Header fields](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/constituent_mass_module.f90#L579) · [Scalar write list](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hcsin_output.f90#L22)

The incoming writer call is commented out in this revision. See [incoming streams](README.md#incoming-streams) for widths and the yearly metals CSV header exception. [Disabled reporting call](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/command.f90#L627)
