---
description: "Effective hydraulic conductivity of the main channel alluvium"
---

# k

**Code reference:** `ch_hyd(ich)%k` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/channel_data_module.f90#L79)).

Effective hydraulic conductivity of the main channel alluvium (`mm/h`, struct default `0.01`), intended for channel transmission-loss calculations in [`ch_rtday.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ch_rtday.f90#L226):

$$\text{rttlc} = \Delta t \cdot K \cdot L \cdot P$$

where:
- $\text{rttlc}$ is channel transmission loss ($\text{m}^3$),
- $\Delta t$ is the routing time step (`h`, `24`),
- $K$ is `k` (`mm/h`),
- $L$ is channel length (`km`), and
- $P$ is wetted perimeter (`m`).

In SWAT+ main (`6f515368`), `ch_rtday` has no callers because daily `case ("chan")` dispatch in [`command.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/command.f90#L305-L310) is commented out.
