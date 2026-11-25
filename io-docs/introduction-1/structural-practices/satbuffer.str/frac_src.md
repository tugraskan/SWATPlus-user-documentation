---
description: "Fraction used in buffer inflow and nitrate partitioning"
---

# frac_src

**Code reference:** `satbuff_db(ibuff)%frac_src` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_module.f90#L101)).

Used to scale buffer inflow and partition tile nitrate ([`hru_control.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_control.f90#L648-L652)). Enter a fraction rather than a percentage; the decision table specified by [`flocon_dtbl`](flocon_dtbl.md) first determines the diverted tile inflow depth $Q_{\text{div}}$:

$$Q_{\text{buf}} = \frac{A_{\text{rcv}}}{A_{\text{src}}} \, f_{\text{src}} \, Q_{\text{div}}, \qquad q_{\text{tile,rem}} = (1 - f_{\text{src}}) \, Q_{\text{div}}$$

where:

- $Q_{\text{buf}}$ is the tile water routed into the buffer HRU
- $q_{\text{tile,rem}}$ is the tile water remaining in the source HRU tile outflow
- $Q_{\text{div}}$ is the diverted tile inflow depth determined by [`flocon_dtbl`](flocon_dtbl.md)
- $f_{\text{src}}$ is `frac_src` (fraction)
- $A_{\text{src}}$ and $A_{\text{rcv}}$ are the source and receiving HRU areas (ha)

For nitrate partitioning:

$$N_{\text{buf}} = f_{\text{src}} \, N_{\text{tile}}, \qquad N_{\text{tile,rem}} = (1 - f_{\text{src}}) \, N_{\text{tile}}$$

where $N_{\text{buf}}$ is the tile nitrate routed into the buffer HRU, $N_{\text{tile,rem}}$ is the tile nitrate remaining in the source HRU tile outflow, $N_{\text{tile}}$ is the source HRU tile nitrate load, and $f_{\text{src}}$ is `frac_src` (fraction).
