---
description: Fraction of HRU area at principal spillway
---

# hru\_ps

**Code reference:** `wet_hyddb(ires)%psa` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/reservoir_data_module.f90#L84)).

During initialization ([`wet_initial.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wet_initial.f90#L135), [initial area](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wet_initial.f90#L216)), `hru_ps` scales the HRU area to compute the principal surface area (`wet_ob%psa`) and initial wetland surface area ($A_{\text{init}}$, ha):

$$A_{\text{psa}} = f_{\text{ps}} \cdot A_{\text{hru}}, \qquad A_{\text{init}} = A_{\text{hru}} \cdot f_{\text{ps}} \cdot \text{fr}$$

where $f_{\text{ps}}$ is `hru_ps`, $A_{\text{hru}}$ is HRU area (ha), $A_{\text{psa}}$ is principal surface area (ha), and $\text{fr}$ is the initial surface area fraction. If `hru_ps <= 0.0`, [`wet_read_hyd.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wet_read_hyd.f90#L60) sets it to $0.08 \cdot d_{\text{ps}}$ (`0.08 * wet_hyd(ires)%pdep`).

However, `hru_ps` is only used for estimating the initial wetland area. For daily wetland simulations, the model assumes for simplicity that the entire HRU is wet, so the HRU area is used instead of the principal surface area to calculate the principal volume of the wetland. Accordingly, `hru_ps` has very limited impact on wetland calculations.
