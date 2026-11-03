---
icon: angle
---

# 1:1.1.2 Solar Declination

Solar declination, $$\delta$$, is the latitude where the Sun is directly overhead at solar noon. It is near zero at the equinoxes and reaches roughly $$\pm23.5^\circ$$ at the solstices. A simple formula from Perrin de Brichambaut (1975), as given in the [SWAT 2009 Theoretical Documentation](https://swat.tamu.edu/media/99192/swat2009-theory.pdf), is:

$$\delta=\sin^{-1}\!\left[0.4\sin\left(\frac{2\pi(d_n-82)}{365}\right)\right]$$                                                                                                       1:1.1.2

Here $$\delta$$ is in radians and $$d_n$$ is the day of year. The offset $$d_n-82$$ is inside the sine argument.

### Source Code Implementation

**Classification: Direct approximation with a rounded divisor.** [cli_clgen.f90](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/cli_clgen.f90#L68-L70) evaluates

$$\mathrm{sd}=\sin^{-1}\!\left[0.4\sin\left(\frac{d_n-82}{58.09}\right)\right].$$

The divisor 58.09 approximates $$365/(2\pi)$$. The result `sd` is calculated from `time%day`; it is not a user-entered parameter. The starting day comes from [day_start](../../../../introduction-1/simulation-settings/time.sim/day_start.md) in `time.sim`. The coefficients 0.4, 82, and 58.09 are built into the code.

The [Fortran calculation](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/cli_clgen.f90#L70) is:

```fortran
sd = Asin(.4 * Sin((Real(time%day) - 82.) / 58.09))  !!365/2pi = 58.09
```

| Term or result | Source-code value | Origin |
| --- | --- | --- |
| Day of year $$d_n$$ | `time%day` | Simulation date; [day_start](../../../../introduction-1/simulation-settings/time.sim/day_start.md) sets the first day |
| Declination coefficients and scale | `0.4`, `82`, and `58.09` | Built-in constants; not user inputs |
| Solar declination $$\delta$$ | `sd` | Calculated result in radians; not a user input |
