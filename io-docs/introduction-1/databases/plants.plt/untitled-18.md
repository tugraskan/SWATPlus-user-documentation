---
description: Days to maturity
---

# days\_mat

**Code reference:** `pldb(ic)%days_mat` ([declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/plant_data_module.f90#L42)).

The PHU program was incorporated directly into SWAT+. The heat units to maturity were changed to days to maturity (_days\_mat_). The concept of heat units to maturity was developed for annual crops and we use heat units for the entire growing season for native perennials and native annuals. By inputting days to maturity, we can include different crop varieties as defined by length of growing season (e.g., 120-, 110-, 100- and 90-day varieties for corn). The heat units to maturity calculation in the model first computes base zero heat units for the entire year and assumes a planting date when heat units exceed 0.15 \* base zero. Then, the model calculates heat units from planting date through the days to maturity using the crop's base temperature as specified by [tmp\_base](tmp_base.md). If the maximum days for a crop are input, e.g., 120 days for corn, and the growing season is less than 120 days, the model essentially sums heat units for the entire growing season which represents (and estimates) the maximum days to maturity.&#x20;

The algorithm currently uses monthly weather generator parameters but could be modified to alternatively use daily temperature inputs. The model provides heat unit estimates in both the northern and southern hemispheres.&#x20;

There are several advantages to incorporating the heat unit program into SWAT+ including:

1. It eliminates the need for running an external program when developing inputs,&#x20;
2. allows input of a commonly understood variable (days) instead of a variable that is not commonly known at every location (heat units),&#x20;
3. allows the model to calculate heat units for native perennials and annuals that are location dependent,&#x20;
4. a database (plants.plt) can be maintained and supported that includes different crop varieties, and&#x20;
5. by inputting the maximum growing season for a crop, the model will calculate appropriate heat units for that crop anywhere in the northern or southern hemisphere.

Enter days_mat as an integer with no decimal point. SWAT+ main (6f515368) reads this field directly into an integer variable.
