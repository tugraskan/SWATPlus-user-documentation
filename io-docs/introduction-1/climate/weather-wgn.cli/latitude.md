# latitude

Station latitude in decimal degrees, from −90 to 90. SWAT+ converts it to radians and uses its sine and cosine for solar geometry:

$$\phi = \frac{\mathrm{latitude}}{57.296}$$

where $\phi$ is the station latitude (radians) and $\mathrm{latitude}$ is `latitude` (decimal degrees).

See [cli_initwgn.f90](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cli_initwgn.f90#L120-L145).
