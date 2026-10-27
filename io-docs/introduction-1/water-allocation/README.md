# Water Allocation

For SWAT+ main `6f515368`, the current water-allocation reader uses:

- [place_of_use.wro](place_of_use.wro.md): places of use and their diversion and return records.
- [point_of_diver.wro](point_of_diver.wro.md): points of diversion and their associated places of use.

The [water_allocation.wro](water_allocation.wro/README.md) pages retain a historical format and are marked accordingly. They do not describe these current input records.

The current pages document source read order and declared types. They do not claim runtime validation of the water-allocation module. [Source](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/water_allocation_read.f90#L40).
