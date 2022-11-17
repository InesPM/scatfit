# Scatfit: Scattering fits of time domain radio signals (Fast Radio Bursts or pulsars) #

This repository contains code to fit Fast Radio Burst or pulsar profiles to measure scattering and other parameters. The code is mainly developed for Python 3, but Python 2 from version 2.7 onwards should work fine.

## Author ##

The software is primarily developed and maintained by Fabian Jankowski. For more information feel free to contact me via: fabian.jankowski at manchester.ac.uk.

## Citation ##

If you make use of the software, please add a link to this repository and cite our upcoming paper. See the CITATION file.

The code is also listed in the Astrophysics Source Code Library (ASCL): https://ascl.net/code/v/3366

## Installation ##

The easiest and recommended way to install the software is through `pip` directly from its GitHub software repository. For example, to install the master branch of the code, use the following command:

`pip3 install git+https://github.com/fjankowsk/scatfit.git@master`

This will automatically install all dependencies.

## Usage ##

```
$ scatfit-fitfrb -h
usage: scatfit-fitfrb [-h] [--compare] [--binburst bin] [--fscrunch factor] [--tscrunch factor] [--fast] [--fitscatindex]
                      [--smodel {unscattered,scattered_isotropic,scattered_isotropic_convolving,scattered_isotropic_bandintegrated,scattered_isotropic_afb_instrumental,scattered_isotropic_dfb_instrumental}]
                      [--showmodels] [--snr snr] [--publish] [-z start end]
                      filename dm

Fit a scattering model to FRB data.

positional arguments:
  filename              The name of the input filterbank file.
  dm                    The dispersion measure of the FRB.

options:
  -h, --help            show this help message and exit
  --compare             Fit an unscattered Gaussian model for comparison. (default: False)
  --binburst bin        Specify the burst location bin manually. (default: None)
  --fscrunch factor     Integrate this many frequency channels. (default: 256)
  --tscrunch factor     Integrate this many time samples. (default: 1)
  --fast                Enable fast processing. This reduces the number of MCMC steps drastically. (default: False)
  --fitscatindex        Fit the scattering times and determine the scattering index. (default: False)
  --smodel {unscattered,scattered_isotropic,scattered_isotropic_convolving,scattered_isotropic_bandintegrated,scattered_isotropic_afb_instrumental,scattered_isotropic_dfb_instrumental}
                        Use the specified scattering model. (default: scattered_isotropic_convolving)
  --showmodels          Show comparison plot of scattering models. (default: False)
  --snr snr             Only consider sub-bands above this S/N threshold. (default: 3.8)
  --publish             Output plots suitable for publication. (default: False)
  -z start end, --zoom start end
                        Zoom into this time region. (default: [-50.0, 50.0])
```

## Profile scattering models ##

Several profile scattering models, i.e. pulse broadening functions and instrumental contributions, are implemented and others can easily be added. The image below shows a selection of them.

![Implemented profile scattering models](https://github.com/fjankowsk/scatfit/raw/master/docs/profile_models.png "Implemented profile scattering models")

## Example output ##

The images below show some example output from the program obtained when fitting simulated filterbank data.

![Profile fit](https://github.com/fjankowsk/scatfit/raw/master/docs/profile_fit.png "Profile fit")

![Width scaling](https://github.com/fjankowsk/scatfit/raw/master/docs/width_scaling.png "Width scaling")

![Correlations](https://github.com/fjankowsk/scatfit/raw/master/docs/corner.png "Correlations")
