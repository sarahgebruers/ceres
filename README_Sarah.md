The original CERES scripts for FEROS data are located in 'ferospipe_original.py' and 'ferosutils_original.py'.
These have been adapted according to the changes described in Gebruers et al. (2022): 'ferospipe_adapted.py' and 'ferosutils.py'.
All the changes are indicated by a comment starting with 'Sarah Gebruers:'.

To run the CERES pipeline do:
python ferospipe_adapted.py  < path to data of FEROS night > -npools < number of cores >

where < path to data of FEROS night > must contain all the raw data of an observing night (i.e. science frames, flats, bias, wavelength calibration frames).

Output comes in 3 files.

- *_sp.fits: original output from the CERES pipeline (see readme file in CERES folder).
- *_sp_merged.fits: wavelength, flux, flux error of full 1D spectrum with merged orders.
- *_sp_noCR.fits: same as '_sp_merged.fits' but with cosmics removed.




It is possible that during the installation something goes wrong with the SSEphem package.
This is a workaround:

First, register here: https://urs.earthdata.nasa.gov/oauth/authorize?client_id=gDQnv1IO0j9O2xXdwS8KMQ&response[…]2Fproxyauth&state=aHR0cDovL2NkZGlzLm5hc2EuZ292L2FyY2hpdmU

When you're logged in, you are allowed to get the files manually.
Now, if you don't want to do that anytime you reinstall, you will have to create a file with your user and password.
Open a text file and name it .netrc.
On it, include the following: machine urs.earthdata.nasa.gov login <username> password <password>
This file needs to have its permissions changed. So that only you can read it
Save this file in the home directory
And try again to install CERES
