# Introduction to CuRichFluid

In this repository, CuRichFluid, we present the sulfide saturation, degassing and sulfide resorption code and required 
datafiles for Hogg et al. (2024 – GEOLOGY) ("link to paper"). 

This code integrates several Python3 petrological and thermodynamic packages (PetThermoTools; PySulfSat; Thermobar) 
with published volatile and chalcophile element partitioning data. We model the impact that magma water contents and 
pressure have on the timing of sulfide saturation relative to degassing and the ability for the melt to resorb sulfides.
The goal is to determine the optimal conditions for generating Cu-rich magmatic fluids.


# A breakdown of the files included in CuRichFluid

## PetThermoTools_FC_Modelling.ipynb
This code performs fractional crystallisation models using RhyoliteMELTS run through PetThermoTools, an open-source Python3 tool for performing phase equilibria calculations using the MELTS. Note, to run this code you will need to have alphaMELTS downloaded locally on your computer. See https://magmasource.caltech.edu/alphamelts/version2.php for how to do this. 

## PetThermo_input.csv 
input file required to run code in PetThermoTools_FC_Modelling.ipynb

## PetThermo_output.csv
output file from PetThermoTools_FC_Modelling.ipynb that will be loaded in to SulfSat_Degassing_Modelling.ipynb

## SulfSat_Degassing_Modelling.ipynb
This code is used to model sulfide saturation and chalcophile element partitioning between the melt-fluid and melt-sulfide reservoirs. We use PySulfSat, an open-source Python3 tool to calculate sulfide and sulfate solubilities of the melt. Volatile-melt and sulfide-melt partitioning of chalcophile elements are then calculated. Concentrations and masses of chalcophile elements and volatiles across the melt-fluid-sulfide reservoirs are calculated.  This code contributes to the data discussed in ‘Results’ and ‘Element ratios record sulfide saturation’ section of our manuscript.

## Final_model_output.csv
file output by SulfSat_Degassing_Modelling.ipynb. Data discussed in ‘Results’ and ‘Element ratios record sulfide saturation’ section of our manuscript.

## Before_degassing_sulfsat.csv
file exported from SulfSat_Degassing_Modelling.ipynb prior to partitioning calculations. This file is a required input for Sulfide_Resorption_Modelling.ipynb

## Sulfide_Resorption_Modelling.ipynb
This code performs sulfide resorption calculations. Data are discussed in ‘Basalt interaction with sulfide cumulates generates copper-rich fluids’ section of our manuscript.



