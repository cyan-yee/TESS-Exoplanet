# Physics 77: Final Project TESS Exoplanet
# Analyzing Exoplanet Orbits Using TESS

Group Members: Isaac Chan, Kiran John, Jonathan Pan, Cyan Yee, Hana Zitnanska

# Project Overview: 
The purpose of this project is to investigate whether computational techniques applied to TESS Full Frame Images (FFIs) can identify transit events with incomplete orbital information (i.e. planet radius) and use physical transit modeling (batman) combined with Markov Chain Monte Carlo (MCMC) sampling to recover or refine key parameters such as period, planet radius, inclination, angle of periastron, semi-major axis, transit mid-time, and eccentricity. As TESS often produces incomplete or noisy data due to short observing windows, we aim to increase the accuracy of these to help understand the physical properties of given exoplanets. To do so, we extract light curves from TESS FFI using BLS to detect transit signals and estimate initial parameters as BLS  allows more flexibility to missing parameters. 


# Methods & Tools (this is also in the requirements.txt):
- Scientific Libaries used: NumPy (1.23.5), SciPy (1.10.1), Matplotlib (3.7.5), Pandas (1.5.3)
- Astronomy data analysis: Astropy (5.3.4), Astroquery (0.4.6), Lightkurve (2.4.2), batman-package(2.4.9), emcee (3.1.4), corner (2.2.2), tqdm (4.67.1), requests (2.28.2)
- Analysis done in: Jupyter Notebooks (located in Data folder)
  -  Cleaned/normalized light curves located in Data, lightcurves folder
---
# Preprocessing + BLS
- Script located in FFI notebook (in Data folder)
- Has 2 main functions: 1) Analyzes and plots for 1 target, 2) Analyzes for 20 TOIs (and saves light curves to csv) + plots for 1 target
  - Both functions will extract a light-curve, clean/normalize, run BLS search for period, estimate uncertainity, and give plots
- How to run:
  - Run the 2nd cell starting with "if name == "main":"
    - df_missing = search_tois_with_missing_radius() finds TOIs with missing radius
    - To analyze different TOIs:
       - Change index in "candidate_index = #"
       - This will graph all plots, run BLS, and give a summary of all calculations
    - batch_results analyzes multiple TOIs at a time (currently set to 20)
       - Runs BLS on all TOIs
       - Creates csv file of cleaned/normalized light curves, ready for BLS and batman/MCMC
# Processing + MCMC
- Script located in MCMC_FINAL notebook (in Data folder)
- Computation pipline which retreives BLS guesses, optimizes the intial guesses, and runs MCMC on a section of the transit csv file to compute fitted orbital paramters
- How to run:
  - Run the cell with a csv file produced from preprocessing in "data = # Put csv file with  flux, flux error, and time"
    - To analyze different TICs:
       - Change to corresponding csv file
  - Outputs corner plot with posterior distribution and final fitted orbitally paramters
# Light curve + Orbital Model
- Script located in Light_Curve&Orbital_Model notebook (in Data folder)
- 2 cells: 1) Produces a batman light curve based compared to the transit light curve data, 2) Produces an orbital model
    - Both cells run on fitted orbital parameters which must be input into the cells
- How to run:
    - Run first cell with fitted orbital paramters to generate light curve
    - Run second cell with fitted orbital paramters (rp, inc, a, w) to create a model orbit

# Resources:
- [TESS beginner light curve tutorial](https://heasarc.gsfc.nasa.gov/docs/tess/LightCurve-object-Tutorial.html)  
- [TESS data aperture tutorial](https://heasarc.gsfc.nasa.gov/docs/tess/Aperture-Photometry-Tutorial.html)
- [TESS Introduction](https://heasarc.gsfc.nasa.gov/docs/tess/TESS-Intro.html)  
- [NASA Exoplanet Archive](https://exoplanetarchive.ipac.caltech.edu/)
- [MAST](https://mast.stsci.edu/portal/Mashup/Clients/Mast/Portal.html)

