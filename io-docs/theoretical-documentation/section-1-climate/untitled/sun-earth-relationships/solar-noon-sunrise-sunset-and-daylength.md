# 🌄 1:1.1.3 Solar Noon, Sunrise, Sunset, and Daylength

The solar zenith angle, $$\theta_z$$, is the angle between the Sun's rays and the vertical at an observer's location. Solar noon is when that angle is smallest for the day (Figure 1:1-1).

![Figure 1:1-1 Diagram illustrating the solar zenith angle](../../../../.gitbook/assets/Figure_1.png)

For latitude $$\phi$$ and solar declination $$\delta$$, the relationship is

$$\cos\theta_z=\sin\delta\sin\phi+\cos\delta\cos\phi\cos(\omega t)$$                                                                                                       1:1.1.3

Here $$\omega$$ is Earth's angular rotation rate, approximately 0.2618 rad/h, and $$t$$ is time relative to solar noon. Following the sign convention of the earlier SWAT theory, $$t=0$$ at solar noon, is positive in the morning, and is negative in the evening. These are solar-time offsets, not civil clock times.

Sunrise and sunset are symmetric around solar noon in this relationship. Their time offsets are

$$T_{SR}=+\frac{\cos^{-1}(-\tan\delta\tan\phi)}{\omega}$$                                                                                                                1:1.1.4

$$T_{SS}=-\frac{\cos^{-1}(-\tan\delta\tan\phi)}{\omega}$$                                                                                                                  1:1.1.5

The total daylength is

$$T_{DL}=\frac{2\cos^{-1}(-\tan\delta\tan\phi)}{\omega}$$                                                                                                              1:1.1.6

At high latitudes on some days, $$-\tan\delta\tan\phi$$ falls outside the range from -1 to 1. The model then assigns the hour-angle magnitude $$h$$ a value of 0 for polar night or approximately $$\pi$$ for polar day, giving about 0 or 24 hours of daylight.

### Source Code Implementation

**Equation 1:1.1.3 — direct for sampled solar position.** [cli_clgen.f90](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/cli_clgen.f90#L92-L116) computes `ys = sin(phi) sin(sd)` and `yc = cos(phi) cos(sd)`, then evaluates

$$\texttt{cosrho(ii)}=\texttt{ys}+\texttt{yc}\cos(\texttt{hr\_angle}).$$

The routine sets nonpositive values to zero, then [divides each value by the day's total](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/cli_clgen.f90#L114-L118) to form the fraction of radiation in each time step, `frad`. No other routine in this version of SWAT+ reads `frad`, so these fractions do not currently affect simulated results. The sampled hour angle is `hr_angle = (12.5 - ii) * 0.2618 * time%dtm / 60`; `time%dtm` is minutes per simulation step. The code calculates the cosine of the zenith angle, not $$\theta_z$$ itself.

The routine first calculates the [latitude and declination terms](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/cli_clgen.f90#L92-L93):

```fortran
ys = wgn_pms(iwgn)%latsin * Sin(sd)
yc = wgn_pms(iwgn)%latcos * Cos(sd)
```

Then the [Fortran time-step calculation](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/cli_clgen.f90#L109-L111) is:

```fortran
hr_angle = (12.5 - Real(ii)) * 0.2618 * time%dtm / 60.   !!0.2618 rad/hr
cosrho(ii) = ys + yc * Cos(hr_angle)
if (cosrho(ii) <= 0.) cosrho(ii) = 0.
```

**Equations 1:1.1.4–1:1.1.5 — indirect.** The code calculates the shared sunrise/sunset hour-angle magnitude $$h$$. It does not separately calculate or store the time offsets $$T_{SR}=h/\omega$$ and $$T_{SS}=-h/\omega$$.

**Equation 1:1.1.6 — transformed.** The same routine calculates the hour angle and daylength as

$$x=-\frac{\texttt{latsin}\tan(\texttt{sd})}{\texttt{latcos}},\qquad
h=\begin{cases}
0,&x>1,\\
\cos^{-1}(x),&-1\leq x\leq1,\\
3.1416,&x<-1,
\end{cases}\qquad
\texttt{daylength}=7.6394h.$$

This is [the calculation in the code](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/cli_clgen.f90#L79-L88). `latsin/latcos` represents $$\tan\phi$$, and 7.6394 approximates $$2/\omega$$. The 0 and 3.1416 branches handle polar night and polar day.

```fortran
sdlat = -wgn_pms(iwgn)%latsin * Tan(sd) / wgn_pms(iwgn)%latcos

if (sdlat > 1.) then    !! sdlat will be >= 1. if latitude exceeds +/- 66.5 deg in winter
  h = 0.
elseif (sdlat >= -1.) then
  h = Acos(sdlat)
else
  h = 3.1416         !! latitude exceeds +/- 66.5 deg in summer
endif
wst(iwst)%weat%daylength = 7.6394 * h
```

SWAT+ also calculates a **minimum annual daylength** during weather-generator initialization. [cli_initwgn.f90](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/cli_initwgn.f90#L123-L133) evaluates the following unnumbered code equivalent:

$$u=0.4348|\tan\phi|,\qquad h_{min}=\begin{cases}\cos^{-1}(u),&u<1,\\0,&u\geq1,\end{cases}\qquad \mathrm{daylmn}=7.6394h_{min}.$$

This is used in [plant dormancy](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/pl_dormant.f90#L29); it is separate from the daily `daylength` result. The coefficient 0.4348 approximates $$\tan(23.5^\circ)$$.

The [Fortran minimum-daylength calculation](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/cli_initwgn.f90#L131-L133) is:

```fortran
x1 = .4348 * Abs(lattan)
if (x1 < 1.) x2 = Acos(x1)
wgn_pms(iwgn)%daylmn = 7.6394 * x2
```

Here `x2` starts at zero earlier in the routine, so it stays zero when `x1` is at least 1.

| Term or result | Source-code value | Origin |
| --- | --- | --- |
| Latitude $$\phi$$ | `wgn(iwgn)%lat`, then `latsin` and `latcos` | `latitude` in [weather-wgn.cli](../../../../introduction-1/climate/weather-wgn.cli/README.md), converted from degrees to radians in `cli_initwgn.f90` |
| Declination $$\delta$$ | `sd` | Calculated from day of year by equation 1:1.1.2 |
| Day of year | `time%day` | Simulation date; [day_start](../../../../introduction-1/simulation-settings/time.sim/day_start.md) sets the first day |
| Steps per day | `time%step`, then `time%dtm` | [step](../../../../introduction-1/simulation-settings/time.sim/step.md) in `time.sim`; used for sampled solar position |
| Earth rotation rate $$\omega$$ | `0.2618` or folded into `7.6394` | Built-in constants |
| Hour angle and daylength | `h`, `wst(iwst)%weat%daylength` | Calculated results; sunrise and sunset times are not separate outputs |

### Related literature

[Allen et al. (2006)](https://doi.org/10.1016/j.agrformet.2006.05.012), p. 57, give the same relationships for a horizontal surface. Their Eq. 4 is the cosine of the zenith angle in the form of Equation 1:1.1.3, with their hour angle in place of $$\omega t$$, and their Eq. 8 gives the sunset hour angle as $$\cos^{-1}(-\tan\delta\tan\phi)$$, the angle $$h$$ above. Their hour angle is negative in the morning, the opposite of the sign convention used on this page. The constants and polar branches above describe this SWAT+ implementation.
