# llamasrun
Some notes about observing and reducing LLAMAS data

## Key Links
* https://sites.mit.edu/llamas/
* https://github.com/mit-kavli-institute/llamas-pyjamas

## Afternoon Calibrations
Gabor ran all of these for us so trying to reconstruct what happened
- ThAr arc: 3 x short (0.05), 3 x medium (0.1), 3 x long (1), 3 x "for BLUE" (1)
- LDLS flat: 3 x short (0.05), 3 x medium (0.1), 3 x long (0.5), 3 x "for RED" (1)
- Bias: 3 x slow, 3 x fast
- Sky flats: about 10

## Reduction Notes (scratch)
- `reduce.py` `main()`
  - `ray_num_cpus`, `bias_file`
  - `generate_new_wavelength_soln` by default false
    - Needed: `arc_file`
    - Optional: `shift_picklename`, `flat_picklename` -> `relative_throughput()`
    - -> `calc_wavelength_soln()`
  - `trace_output_dir`, `extraction_output_dir`, `cube_output_dir`
  - `red_flat_file`, `green_flat_file`, 'blue_flat_file`
    - *`generate_traces()`*
  - `science_files`
    - *`run_extraction()`*
  - Run through pkl_files:
    - *`correct_wavelengths()`*
    - Creates rss files ("row stacked spectra", it effectively means that each row in the image extension corresponds to an individual fibre extraction)
  - *`construct_cube()`*
