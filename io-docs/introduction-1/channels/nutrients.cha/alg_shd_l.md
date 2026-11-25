---
description: Linear algal self-shading coefficient
---

# alg\_shd\_l

**Code reference:** `ch_nut(ich)%lambda1` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/channel_data_module.f90#L153)).

Linear algal self-shading coefficient (`1/(m*ug chla/L)`, default `0.03`, range `0.006–0.065`). In [`ch_read_nut.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ch_read_nut.f90#L78), any value `<= 0.` is replaced with `0.03`, so `0` cannot be retained to disable linear self-shading.

The intended light extinction coefficient $\lambda$ is:

$$\lambda = \lambda_0 + \lambda_1\,\alpha_0\,\text{algae} + \lambda_2\,(\alpha_0\,\text{algae})^{2/3}$$

where:
- $\lambda$ is the light extinction coefficient (`1/m`),
- $\lambda_0$ is `lt_nonalg` (`1/m`),
- $\lambda_1$ is `alg_shd_l` (`1/(m*ug chla/L)`),
- $\lambda_2$ is `alg_shd_nl` (`(1/m)(ug chla/L)^(-2/3)`),
- $\alpha_0$ is `chla_alg` (`ug chla/mg alg`), and
- $\text{algae}$ is algal biomass (`mg alg/L`).

However, in SWAT+ main (`6f515368`), [`ch_watqual4.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ch_watqual4.f90#L162-L169) immediately caps $\lambda$ at $\lambda_0$ (`if (lambda > lambda0) lambda = lambda0`). Because `lambda1` and `lambda2` are forced positive on read, the self-shading addition always exceeds $\lambda_0$ when algae are present and is cancelled before `fl_1` is calculated.

The Riley equation (Bowie et al., 1985) defines $\lambda_1 = 0.0088$ `1/(m*ug chla/L)` and $\lambda_2 = 0.054$ `(1/m)(ug chla/L)^(-2/3)`.

#### Relevant chapter in the Theoretical Documentation:

[Local Specific Growth Rate of Algae](../../../theoretical-documentation/section-7-main-channel-processes/in-stream-nutrient-processes/algae/algal-growth/local-specific-growth-rate-of-algae.md)

#### References

> Bowie, G.L., W.B. Mills, D.B. Porcella, C.L. Campbell, J.R. Pagenkopt, G.L. Rupp, K.M. Johnson, P.W.H. Chan, and S.A. Gherini. 1985. Rates, constants, and kinetic formulations in surface water quality modeling, 2nd ed. EPA/600/3-85/040, U.S. Environmental Protection Agency, Athens, GA.
