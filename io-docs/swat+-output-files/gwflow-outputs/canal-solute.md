# GWFlow Canal Solute

`gwflow_canal_sol_day.txt` uses the fixed 12-column schema `jday`, `mon`, `day`, `yr`, `unit`, `gis_id`, `name`, `solute`, `div_mass`, `storage`, `pond_mass`, and `seep_mass`. Mass fields are kg. The water and solute files open together under the [canal water-balance settings](canal-water-balance.md). [Headers and units](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L1382-L1401)

With GWFlow solute transport enabled, the writer emits configured salt and conservative-constituent rows. NO₃ and P have no rows in this file. Each of the four masses is the corresponding canal water-balance volume multiplied by the Recall diversion concentration in g/m³ and divided by 1,000. The writer indexes that concentration using the canal's Recall diversion ID without checking it is positive. A canal with no assigned Recall diversion can therefore reach an out-of-bounds index when either solute group is active. [Daily row calculations](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_canal_div.f90#L208-L241), [Concentration array dimensions](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L1653-L1654)

[Back to the GWFlow Outputs index](README.md).
