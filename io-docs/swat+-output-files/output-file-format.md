# Output File Format

Some output families use the daily, monthly, yearly, and average-annual settings in [print.prt](../introduction-1/simulation-settings/print.prt/README.md). The filename suffix identifies the reporting interval. Each family defines which values are totals, averages, or states. [Object Outputs](object-outputs.md) use the requests in [object.prt](../introduction-1/simulation-settings/object.prt/README.md). Module reports and diagnostic files use their own settings and layouts. [Output Family Index](output-family-index.md)

## When a run ends mid-month

SWAT+ can close the final simulation year on a day other than the last calendar day of a month. At revisions `6f515368` and `aa4179fe`, some writers move accumulated values into the yearly record only at month end. Their yearly and average-annual totals omit a final partial month even if daily rows show those days. In a run with no warm-up, `time%yrs_prt` is calculated from simulated days, including that final span. On SWAT+ dev the day total is divided by 365 plus the leap days per printed year (not per simulated year). [Simulation calendar and divisor](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/time_control.f90#L138-L188).

| Reports | Treatment of the final partial month |
| --- | --- |
| [Aquifer](aquifer/README.md), [Recall](recall/individual-recall.md), [Routing Unit](routing-unit/README.md), [Hydrographs](hydrographs/README.md) and [Deposition](hydrographs/deposition.md) | Period sums omit those days. The individual and basin aquifer state averages also omit them. |
| [Reservoir](reservoir/README.md) and [Wetland](wetland/README.md) | Period fluxes and area omit those days. The storage block uses the state at the end of the run. |
| [Water Balance](water-balance/README.md), [Nutrient Balance](nutrient-balance/README.md), [Losses](losses/README.md), and [Plant and Weather](plant-and-weather/plant-weather-output.md) | Annual accumulations omit those days. Some final soil-water, snow, and plant nutrient fields use the last simulated day. |
| [SD Channel General](channel/sd-channel-general.md), [Basin SD Channel General](channel/basin-sd-channel-general.md), and [SD Channel Morphology](channel/sd-channel-morphology.md) | Annual accumulations omit those days. General reports use final-day storage. Annual morphology geometry comes from the last month transferred into the year. |
| [Pesticide balances](pesticides/README.md) | Annual accumulations omit those days. Aquifer final pesticide storage still comes from the last simulated day. |
| [HRU Pathogens](pathogens/README.md#reporting-periods-and-csv-format) | Yearly and average-annual numerators omit those days. The yearly writer still divides the available monthly contributions and any prior-year carryover by 12. |
| [HRU Salt](hru-salt/README.md) and [object-level salt reports](salt-outputs/README.md) | Annual accumulations omit those days. |
| [Basin Salt Balance](salt-outputs/basin-salt-balance.md) | Daily values go directly into the yearly and average-annual sums, including the final partial month. |
| [Object-level conservative-constituent reports](conservative-constituents/README.md) | Annual accumulations omit those days. |
| [Basin Conservative-Constituent Balance](conservative-constituents/basin-balance.md) | Daily values go directly into the yearly and average-annual sums, including the final partial month. |
| GWFlow basin [water](gwflow-basin-water-balance/longer-period-basin-water-balance.md), [solute](gwflow-outputs/basin-solute-balance.md), and [heat](gwflow-outputs/longer-period-basin-heat-balance.md) balances | Yearly and average-annual results include those days. Water and solute monthly rows require calendar month end. Heat has yearly and average-annual files. |
| Water allocation [use](water-allocation/water-use.md) and [treatment](water-allocation/water-treatment.md) | Yearly and average-annual sums omit those days. |
| [Water allocation transactions](water-allocation/allocation-transactions.md) | Annual accumulators include those days and repeatedly add the running monthly subtotals. |
| [Flow Duration Curve](flow-duration-curve/README.md#partial-years-and-fixed-ranks) | The run-end curve includes those days. The annual ranks remain fixed, so unavailable ranks contribute zeros to the median across years. |
| [Basin sediment budget](channel-sediment-budgets/basin-sediment-budget.md) and [channel erosion summaries](channel-sediment-budgets/channel-erosion-by-channel.md) | The yearly accumulator includes those days, and they carry into the average-annual result. |

## Headers and data rows

SWAT+ writes both list-directed and explicitly formatted text. A title, field headings, and a units line are common. The number of preamble lines varies by family and can differ between TXT and CSV. For example, the HRU-salt CSV files write basin and program identification and a units line before their headings. [HRU-salt CSV opener](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/header_salt.f90#L215)

Read the headings together with the family page's data layout. Some writers omit values, change the order of identifiers, or repeat groups for layers, plants, or connections. The heading `null` can label a numeric temperature value. [Hydrograph headings](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydrograph_module.f90#L546)

| Case | Layout to use |
| --- | --- |
| HRU salt | In the eight-ion case the header has 159 fields and the data row has 151 values. The writer omits the groundwater-upward-transfer group and later values shift. [HRU Salt](hru-salt/README.md) |
| Average-annual HRU pathogens | `hru_path_aa.csv` uses comma-separated headings and fixed-width data rows. [Pathogen Outputs](pathogens/README.md) |
| Water allocation | The transaction report uses different row shapes for places of use, diversions, and receiving points. Water-use and treatment files have separate prefix and column-count exceptions. [Water Allocation](water-allocation/README.md) |
| Object requests | The selected code determines the header and data list. Soil-layer and plant counts can change row width. [Object Outputs](object-outputs.md) |
| Opened reports with headings only | The `hru_ncycle_*` source trace found title, heading, and unit writes. Check the actual presence of data rows before using a report. [HRU Nutrient Cycling](carbon/hru-nutrient-cycling.md) |

The `.csv` extension identifies the requested variant. Check its actual writer before choosing a delimiter. For instance, `yield.csv` uses the same list-directed write as `yield.out`. [Debugging Outputs](debugging-outputs.md) · [LTE yield writes](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_lte_control.f90#L206)
