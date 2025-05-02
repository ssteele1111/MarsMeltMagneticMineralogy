The 'Archiving' folder contains all necessary reproduction data for "Magnetic Properties of Martian Impact Basins Including the Effect of Mantle Excavation." This includes
1. Build, option, and thermodynamic data files to regenerate Perple_X outputs from scratch.
2. Post-processed data files output from Perple_X werami (e.g. density, phase proportions) which can be used to reproduce data/figures in the manuscript.

## Requirements
Regenerate Perple_X outputs:
- Perple_X 7.1.4 or greater

## Definitions
Results from individual runs are stored as 
'03_Data/[crystallization style]/[QFM_m#]/[COMP]' where # denotes the number of log units below the QFM buffer.

eq: Equilibrium crystallization
eqfrac: Equilbrium crystallization transtioning to fractional crystallization at 60 vol% crystal fraction
frac: Fractional crystallization

## 01_ThermodynamicDataFiles
Contains the thermodynamic data files for the Tomlinson and Holland (2021) thermodynamic modeled modified to buffer fO2 at different levels according to the instructions at https://www.perplex.ethz.ch/perplex/faq/how_to_buffer_chemical_potentials.txt. These should be copied into the main Perple_X directory after installation.

## 02_OptionFiles
Perple_X option files with variable 'proportions' settings to produce modal, molar, and mass phase proportions with werami.

## 03_Data
*[COMP].dat:* Output file of Perple_X build. Running vertex with the name (including the path but excluding the .dat) will run the simulation. 
*phase_wt_props:* wt proportion of each phase in the system at each temperature step.
*phase_vol_props:* Volume proportion of each phase in the system at each temperature step.
*Sp(TH)_tot_mass:* Total mass in kg of spinel produced at each temperature step.
*Sp(TH)_tot_vol:* Total volume in m^3 of spinel produced at each temperature step.
*Sp(TH)_mol_prop:* Molar proportion of each spinel endmember at each temperature step.
*system_props:* Physical properties of the system at each temperature step. Does not include previously fractionated material.
*lockup_temp_props (eq only):* Properties of the system when the volume fraction of melt reaches approximately 40%.
*solid_dens:* Bulk density of the solid portion (eq) or the material fractionated at each temperature step (frac/eqfrac).
*[COMP]_fractionated_bulk.dat* (frac/eqfrac only): Total moles of each oxide fractionated at each temperature step.

## Instructions for reproducing Perple_X outputs
- copy the Archiving directory into your main Perple_X directory
- copy 'perplex_option_wt.dat' into the working directory (folder containing the Perple_X build output file) and rename it to 'perplex_option.dat'
- from the main Perple_X install directory, run vertex, and supply the project name (the name of the Perple_X build output file, of the form 'Archiving/[crystallization style]/[QFM_m#]/[COMP]/[COMP]')