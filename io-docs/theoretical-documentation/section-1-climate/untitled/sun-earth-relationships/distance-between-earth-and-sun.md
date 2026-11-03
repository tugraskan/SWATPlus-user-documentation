---
icon: people-arrows
---

# 1:1.1.1 Distance between Earth and Sun

The mean Earth–Sun distance is about $$1.496\times10^8$$ km, or one astronomical unit (AU). Because the orbit is elliptical, the distance varies through the year. Incoming solar radiation varies approximately with the inverse square of that distance. For most engineering applications, a simple expression used by Duffie and Beckman (1980) is adequate. The [SWAT 2009 Theoretical Documentation](https://swat.tamu.edu/media/99192/swat2009-theory.pdf) gives it for the Earth–Sun distance factor, $$E_0$$, also called the eccentricity correction factor:

$$E_0=\left(\frac{r_0}{r}\right)^2\approx 1+0.033\cos\left(\frac{2\pi d_n}{365}\right)$$                                                                                              1:1.1.1

Here $$r_0$$ is the mean Earth–Sun distance, $$r$$ is the distance on the day being calculated, and $$d_n$$ is the day of year. SWAT+ uses the actual day of year, including day 366 in leap years, while the approximation keeps a fixed 365-day scale. It does not force February to have 28 days.

### Source Code Implementation

**Classification: Direct approximation.** [cli_clgen.f90](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/cli_clgen.f90#L72-L73) calculates the factor as

$$\mathrm{dd}=1+0.033\cos\left(\frac{d_n}{58.09}\right).$$

The divisor 58.09 approximates $$365/(2\pi)$$. The code stores the factor as `dd` and uses it in [maximum possible solar radiation](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/cli_clgen.f90#L90-L94); it does not calculate $$r$$ or $$r_0$$ separately. $$d_n$$ comes from the simulation date, whose starting day is set by [day_start](../../../../introduction-1/simulation-settings/time.sim/day_start.md) in `time.sim`. The coefficient 0.033 and divisor 58.09 are built into the code.

The [Fortran calculation](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/cli_clgen.f90#L73) is:

```fortran
dd = 1.0 + 0.033 * Cos(Real(time%day) / 58.09)
```

| Term or result | Source-code value | Origin |
| --- | --- | --- |
| Day of year $$d_n$$ | `time%day` | Simulation date; [day_start](../../../../introduction-1/simulation-settings/time.sim/day_start.md) sets the first day |
| Orbit coefficient and scale | `0.033` and `58.09` | Built-in constants; not user inputs |
| Earth–Sun distance factor $$E_0$$ | `dd` | Calculated result used for maximum possible solar radiation |
| Distances $$r$$ and $$r_0$$ | No separate code values | Represented by the calculated factor `dd` |

### Related literature

[Allen et al. (2006)](https://doi.org/10.1016/j.agrformet.2006.05.012), p. 56, Eq. 2, give the same relationship as $$d^2=1/\left[1+0.033\cos\left(2\pi\,\mathrm{DOY}/365\right)\right]$$, where $$d$$ is the relative Earth–Sun distance in astronomical units, so $$1/d^2=E_0$$. They attribute it to Duffie and Beckman (1991). The constants and rounded divisor above describe this SWAT+ implementation.
