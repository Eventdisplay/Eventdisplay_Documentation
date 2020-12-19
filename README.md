# Eventdisplay Documentation

Eventdisplay is a reconstruction and analysis pipline for data of Imaging Atmospheric Cherenkov Telescopes (IACT). 
It has been primarily developed for VERITAS and CTA analysis.

Eventdisplay is in use since roughly 2004 and a rather complex ecosystem grew over the years around the core code base.
This repository collects documentations and links to further resources depending on the application case.

It should be clear that reconstruction and analysis can be complex, as it requires inputs from different sources and execution of several indedependent stages.

## The Eventdisplay Ecosystem

Eventdisplay has been developed for the analysis of VERITAS and only later adapted for other instruments.
Some repositories below are internal to VERITAS and not accessible to the general public.
There are also differences between the Eventdisplay code applied in VERITAS and that made available in the
public repository (see below).

### Code, tools, library

The core libary consist of all code, tools, and libraries required to run the analysis.
This includes the following main reconstruction tools:

1. *evndisp*: calibrate and parametrize images, event reconstruction, stereo analysis
2. *trainTMVAforAngularReconstruction*: train boosted decision trees for direction and energy reconstruction
3. *mscw_energy*: fill and use lookup tables for mean scaled with and lenght calculation, energy reconstruction, stereo reconstruction
4. *trainTMVAforGammaHadronSeparation*: train boosted decision trees for gamma/hadron separation
5. *makeEffectiveArea*: calculation of the instrument response functions (effective areas, angular point-spread function, energy resolution)
6. *makeRadialAcceptance*: calculation of radial camera acceptance from data files
7. *anasum*: analysis to calculate sky maps and spectral energy distribution
8. *libVAnaSum*: shared library tools (to be used with [ROOT](https://root.cern/) to e.g., plot instrument response function, spectral energy distributions, light curves, sky maps

Public code repository: <https://github.com/Eventdisplay/Eventdisplay>

Private (VERITAS) repository (to be used for VERITAS analysis): <https://github.com/VERITAS-Observatory/EventDisplay_v4>


### Execution scripts

### Auxiliary files for parameters, definitions, calibration values

### Converters

### Release tests


### Container appliatons

