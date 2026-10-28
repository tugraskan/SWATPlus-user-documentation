# Debugging Outputs

These reports record simulation status, opened outputs, input problems, and specialized checks. They are not regular daily/monthly/yearly model-result tables, and not every file is produced by every configuration.

* simulation.out
* success.fin
* files\_out.out
* diagnostics.out
* checker.out

`simulation.out` records run progress and timing. `success.fin` is the successful-completion marker. `files_out.out` lists output files opened by the run. `diagnostics.out` collects input and processing diagnostics, while `checker.out` contains model consistency checks. Other specialized builds or options can also write reports such as `area_calc.out`, `hydcon.out`, and `erosion.out`.

Do not use the existence of one of these files as proof that a simulation completed successfully; use the completion marker together with the process exit status and the expected result files.
