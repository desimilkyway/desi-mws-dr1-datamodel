=========
RVRUN
=========

Results from a given RVSpecfit run.
This contains the folder that stores measurements of stars in different
surveys/programs grouped by healpixel. It can contain either measurements
from stacked spectra or individual exposures.

This folder also contains the combined tables of measurements for
different surveys/programs.

I.e. rvpix-main-bright.fits contains rvspecfit measurements from stacked spectra in the  main survey, bright program.
rvpix_exp-main-bright.fits contains measurements from single epoch observations in the main survey, bright program.

Contents:

.. toctree::
   :maxdepth: 1

   healpix/index
   rvpix
   rvpix_exp
