---
description: "Aquifer hydraulic conductivity, m/day"
---

# aquifer_K

**Code reference:** `zones_aquK(i)` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L94), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L397)).

Horizontal hydraulic conductivity of the aquifer, in m/day. Each cell takes the value of its `K_zone` ([`gwflow_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L461)). Flow between neighboring cells follows Darcy's law ([`gwflow_lateral.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_lateral.f90#L64-L93)):

$$Q = K_{f} \, \frac{h_{n} - h_{i}}{d} \, \bar b \, L, \qquad K_{f} = \frac{2 K_{i} K_{n}}{K_{i} + K_{n}}$$

where:
- $Q$ is the flow into cell $i$ from neighbor $n$ ($\text{m}^3/\text{day}$),
- $K_{f}$ is the harmonic-mean interface hydraulic conductivity ($\text{m}/\text{day}$),
- $K_{i}$ and $K_{n}$ are the `aquifer_K` values of cell $i$ and neighbor $n$ ($\text{m}/\text{day}$),
- $h_{n}$ and $h_{i}$ are the heads in neighbor $n$ and cell $i$ (m),
- $d$ is the distance between the cell centroids (m),
- $\bar b$ is the mean saturated thickness of the two cells (m), and
- $L$ is the connection width ($\sqrt{\min(A_{i}, A_{n})}$, m).

The calibration parameter `aquifer_K` changes the value cell by cell ([`cal_parm_select.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cal_parm_select.f90#L1061-L1064)).
