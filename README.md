# Fast Radio Burst Scattering Fits #

This repository contains code to fit Fast Radio Burst profiles to measure scattering and other parameters. The code is mainly developed for Python 3, but Python 2 from version 2.7 onwards should work fine.

## Author ##

The software is primarily developed and maintained by Fabian Jankowski. For more information feel free to contact me via: fabian.jankowski at manchester.ac.uk.

## Citation ##

If you make use of the software, please add a link to this repository and cite our upcoming paper. See the CITATION file.

## Installation ##

The easiest and recommended way to install the software is through `pip` directly from the bitbucket repository. For example, to install the master branch of the code, use the following command:

`pip3 install git+https://bitbucket.org/jankowsk/scatfit.git@master`

This will automatically install all dependencies.

## Usage ##

```bash
$ scatfit-fitfrb -h
usage: scatfit-fitfrb [-h] [--binburst bin] [--fscrunch factor] [--tscrunch factor] [--fitscatindex]
                      [--smodel {unscattered,scattered_isotropic,scattered_isotropic_convolving,scattered_isotropic_afb_instrumental,scattered_isotropic_dfb_instrumental}]
                      [--showmodels] [--publish] [-z start end]
                      filename dm

Fit a scattering model to FRB data.

positional arguments:
  filename              The name of the input filterbank file.
  dm                    The dispersion measure of the FRB.

optional arguments:
  -h, --help            show this help message and exit
  --binburst bin        Specify the burst location bin manually. (default: None)
  --fscrunch factor     Integrate this many frequency channels. (default: 256)
  --tscrunch factor     Integrate this many time samples. (default: 1)
  --fitscatindex        Fit the scattering times and determine the scattering index. (default: False)
  --smodel {unscattered,scattered_isotropic,scattered_isotropic_convolving,scattered_isotropic_afb_instrumental,scattered_isotropic_dfb_instrumental}
                        Use the specified scattering model. (default: scattered_isotropic)
  --showmodels          Show comparison plot of scattering models. (default: False)
  --publish             Output plots suitable for publication. (default: False)
  -z start end, --zoom start end
                        Zoom into this time region. (default: None)
```
