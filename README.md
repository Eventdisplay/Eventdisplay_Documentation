# Eventdisplay Documentation

Eventdisplay is a reconstruction and analysis pipline for data of Imaging Atmospheric Cherenkov Telescopes (IACT). 
It has primarily been developed for VERITAS and CTA analysis.

Reconstruction and analysis can be complex; it requires inputs from different sources and execution of several indedependent stages.
Eventdisplay is in use since roughly 2004 and an ecosystem of libaries and repositories grew around the core code base.
This repository collects documentations and links to resources required for the use of the code depending on the application case.
The detailed documentation for the corresponding steps can be found in each repository.

## The Eventdisplay Ecosystem

Eventdisplay has been developed for the analysis of VERITAS and only later adapted for other instruments.
Some repositories described below are internal to VERITAS and not accessible to the general public.
There are differences between the Eventdisplay code applied in VERITAS and that made available in the
public repository (see below).

For almost every use case, Eventdisplay consists of at least three major components: the code (Eventdisplay), a library of scripts, and auxiliary files.
Care should be taken in using the correct versions (releases, tags, branches) combining these three types of repositories.
A blending of different versions of components will lead to incorrect results.

### Code, tools, library

The core library consist of all code, tools, and libraries required to run the analysis.
This includes the following main reconstruction tools (incomplete list):

1. `evndisp`: calibrate and parametrize images, event reconstruction, stereo analysis
2. `trainTMVAforAngularReconstruction`: train boosted decision trees for direction and energy reconstruction
3. `mscw_energy`: fill and use lookup tables for mean scaled with and lenght calculation, energy reconstruction, stereo reconstruction
4. `trainTMVAforGammaHadronSeparation`: train boosted decision trees for gamma/hadron separation
5. `makeEffectiveArea`: calculation of the instrument response functions (effective areas, angular point-spread function, energy resolution)
6. `makeRadialAcceptance`: calculation of radial camera acceptance from data files
7. `anasum`: analysis to calculate sky maps and spectral energy distribution
8. `libVAnaSum`: shared library tools (to be used with [ROOT](https://root.cern/) to e.g., plot instrument response function, spectral energy distributions, light curves, sky maps

Public code repository: <https://github.com/Eventdisplay/Eventdisplay>

Private (VERITAS) repository (to be used for VERITAS analysis): <https://github.com/VERITAS-Observatory/EventDisplay_v4>

### Execution scripts

Typical use cases for Eventdisplay require the processing of many files (tens to several 100,000 in the case of CTA).
A library of scripts for the efficient execution is available and recommended to be used as the main access to the tools described in the section above.

The analysis scripts depend on the specific observatory use cases. 
The following repositories of scripts are available:

- for **CTA**: <https://github.com/Eventdisplay/Eventdisplay_AnalysisScripts_CTA>
- for **VERITAS** (private repository): <https://github.com/VERITAS-Observatory/Eventdisplay_AnalysisScripts_VTS> (to be used for version v485 and new; scripts are included in the [code library](https://github.com/VERITAS-Observatory/EventDisplay_v4) for older versions)
- for the **CTA pSCT** (incomple): <https://github.com/Eventdisplay/Eventdisplay_AnalysisScripts_pSCT>

### Auxiliary files for parameters, definitions, calibration values

The reconstruction of analysis requires information on the instrument (e.g., telescope positions), access information to data bases, parameters for the analysis (e.g., image cleaning parameters or instruction for the gamma/hadron separation), or basic calibration values.

This information is accessible through repositories for auxiliary files, again dependent on the observatory of interest:

- for **CTA**: <https://github.com/Eventdisplay/Eventdisplay_AnalysisFiles_CTA>
- for **VERITAS** (private repository): <https://github.com/VERITAS-Observatory/Eventdisplay_AnalysisFiles_VTS>

### Release tests

Reconstruction and analysis are complex and a series of tests are required before the release of a new version of Eventdisplay.

Release tests depend on the observatory of interest:

- for **VERITAS** (private repository): <https://github.com/VERITAS-Observatory/EventDisplay_ReleaseTests>

### Container applications

Docker files and images are provided for some Eventdisplay use cases.
Docker files are collected in <https://github.com/Eventdisplay/Eventdisplay_Docker>

### Converters

Tools to convert event lists into DL2 or DL3 format are collected in the converter repositories:

- for **CTA** (DL2): <https://github.com/Eventdisplay/Converters>
- for **VERITAS** (DL3, private repository): <https://github.com/VERITAS-Observatory/V2DL3>


