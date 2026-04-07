# group7_ulab
Repository for the Group 7 ULAB project!

## Files

### `ALMA_datacubes.ipynb`
Explores and visualizes ALMA FITS spectral cubes. Includes a reference table of FITS header keywords and their meanings. Produces:
- A channel map at the source rest velocity
- A moment-0 (integrated intensity) map
- A velocity-corrected spectrum summed over the spatial extent of the cube

### `col_dens_calculator.ipynb`
Calculates the molecular upper state and total column density from a FITS spectral cube. Contains the following functions:
- `solid_angle(r)` — computes the solid angle of the source from its radius in degrees
- `extract_fits_params(fits_path)` — extracts beam size, pixel size, and integrated flux directly from a FITS cube
- `mol_upper_state_cd(...)` — computes the upper state column density N_u using the Einstein A coefficient, integrated flux, beam/pixel geometry, and source solid angle
- `partition_func(T_rot, temps, Q_vals)` — interpolates Q(T_rot) from a table of values from SPLATALOGUE/CDMS using log-log interpolation
- `upper_state_degeneracy(J)` — computes g_u = 2J+1 for a linear molecule
- `total_mol_cd(N_u, g_u, Q_rot, E_u, T_rot)` — computes the total molecular column density N_T assuming LTE and optically thin emission

### `line_data_extraction.ipynb`
Parses a molecular line list exported from CASSIS as a `.txt` file. Extracts the transition name, species ID, frequency, upper state energy, and Einstein A coefficient, then copies the result to the clipboard ready to paste into Excel.

### `CS-97dot9-dot98.FITS`
ALMA spectral cube of the CS J=2→1 transition at ~97.98 GHz, used as input to `col_dens_calculator.ipynb`.
