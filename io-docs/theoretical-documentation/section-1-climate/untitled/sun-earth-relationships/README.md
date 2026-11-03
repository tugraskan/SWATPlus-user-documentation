# ☀️ 1:1.1 Sun-Earth Relationships

SWAT+ uses the day of year and a weather generator station's latitude to calculate solar declination, an Earth–Sun distance factor, daylength, and maximum possible solar radiation. Daylength also affects plant dormancy. This section gives the underlying solar relationships and shows how the current code evaluates them.

Each page distinguishes the published relationship from the code's rounded constants, boundary handling, or calculations that the model does not perform separately. The [SWAT 2009 Theoretical Documentation](https://swat.tamu.edu/media/99192/swat2009-theory.pdf) presents the earlier theory for these equations. Iqbal (1983) provides a detailed discussion of these and other topics related to solar radiation for users who require more information.
