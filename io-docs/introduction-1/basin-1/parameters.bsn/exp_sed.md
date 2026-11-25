---
description: Temperature-dependent pesticide decay switch
---

# exp\_sed

**Code reference:** `bsn_prm%temp_decay` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_module.f90#L86), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_read_prm.f90#L24)).

Despite the legacy `exp_sed` column label (and source comment describing it as a `0–1` factor), SWAT+ main (`6f515368`) evaluates `bsn_prm%temp_decay == 1` as a binary switch (default `0`, range `0–1`) controlling $Q_{10}$ temperature-dependent pesticide decay in soil ([`pest_decay.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/pest_decay.f90#L49-L53)), foliage using top-layer soil temperature ([`pest_decay.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/pest_decay.f90#L76-L81)), aquifers ([`aqu_1d_control.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/aqu_1d_control.f90#L320-L324)), and channels ([`ch_rtpest.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ch_rtpest.f90#L123), [`#L218`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ch_rtpest.f90#L218)).

When `exp_sed = 1`, [`decay_temp_adjust`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/pest_tempdecay_module.f90#L24-L36) adjusts the 25 °C half-life $t_{1/2,25}$ (`days`) using $Q_{10} = 2.58$:

$$t_{1/2}(T) = t_{1/2,25} \cdot Q_{10}^{(25 - T)/10}, \qquad f_{\text{surv}} = \exp\!\left(-\frac{0.693}{t_{1/2}(T)}\right)$$

where:
- $t_{1/2}(T)$ is the temperature-adjusted half-life (`days`),
- $t_{1/2,25}$ is the 25 °C reference half-life (`days`),
- $Q_{10}$ is the temperature coefficient (`2.58`, dimensionless),
- $T$ is the compartment temperature (`°C`), and
- $f_{\text{surv}}$ is the daily survival fraction (dimensionless).

For any other value, SWAT+ uses the fixed decay factors from [**pesticide.pes**](../../databases/pesticide.pes/).
