# Python source extraction code for JCMT SCUBA-2 images
This repository contains my python code and a demo to extract point sources from [JCMT](https://www.eaobservatory.org/jcmt/) 
[SCUBA-2](http://www.eaobservatory.org/jcmt/instrumentation/continuum/scuba-2/) images at 450 or 850 micron. The image 
used for the demo is a reduced 850 micron image of the cluster field Abell 2390, which was presented in 
[Hsu et al. 2017](http://adsabs.harvard.edu/abs/2017arXiv170901238H)

### Data
Input
- s8.fits: a SCUBA-2 850 micron image

Output
- stack850.fits: a stacked image of the 25 brightest sources detected in s8.fits
- psf850.fits: a PSF image generated by fitting a double-Gaussian model to stack850.fits
- test-resid.fits: the residual of s8.fits with 108 4-sigma detected sources subtracted
- test-snr-resid.fits: the signal-to-noise ratio image of test-resid.fits
- test-source.log: the catalog (csv format) of the 108 4-sigma detected sources
- test.reg: the region file of the 108 4-sigma detected sources

### Code

The code is in [scuba2.py](scuba2.py), where ``scuba850`` and ``scuba450`` are the classes for source 
extraction; ``region`` is a function to generate region files; and ``doubleGauss`` is a function to compute 
a double-Gaussian model. Please read the comments of ``scuba850`` for an understanding of the source extraction 
procedure. A simple demo of how to run the code is shown in [demo.ipynb](demo.ipynb).
