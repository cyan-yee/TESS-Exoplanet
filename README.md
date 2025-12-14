# Physics 77: Final Project TESS Exoplanet
# Analyzing Exoplanet Orbits Using TESS

Group Members: Isaac Chan, Kiran John, Jonathan Pan, Cyan Yee, Hana Zitnanska

# Project Overview: 
The purpose of this project is to investigate whether computational techniques applied to TESS Full Frame Images (FFIs) can identify transit events with incomplete orbital information (i.e. planet radius) and use physical transit modeling (batman) combined with Markov Chain Monte Carlo (MCMC) sampling to recover or refine key parameters such as period, planet radius, inclination, angle of periastron, semi-major axis, transit mid-time, and eccentricity. As TESS often produces incomplete or noisy data due to short observing windows, we aim to increase the accuracy of these to help understand the physical properties of given exoplanets. To do so, we extract light curves from TESS FFI using BLS to detect transit signals and estimate initial parameters as BLS  allows more flexibility to missing parameters. 


# Methods & Tools (this is also in the requirements.txt):
- Scientific Libaries used: NumPy (1.23.5), SciPy (1.10.1), Matplotlib (3.7.5), Pandas (1.5.3)
- Astronomy data analysis: Astropy (5.3.4), Astroquery (0.4.6), Lightkurve (2.4.2), batman-package(2.4.9), emcee (3.1.4), corner (2.2.2), tqdm (4.67.1), requests (2.28.2)
- Analysis done in: Jupyter Notebooks

Resources:
- [TESS beginner light curve tutorial](https://spacetelescope.github.io/mast_notebooks/notebooks/TESS/beginner_how_to_use_lc/beginner_how_to_use_lc.html)  
- [TESS data validation tutorial](https://spacetelescope.github.io/mast_notebooks/notebooks/TESS/beginner_how_to_use_dvt/beginner_how_to_use_dvt.html)  
- [TESS Introduction](https://heasarc.gsfc.nasa.gov/docs/tess/TESS-Intro.html)  
- [NASA Exoplanet Archive](https://exoplanetarchive.ipac.caltech.edu/)  

-------------------------------------
To do (for group members):

1. Clone repository, use:
- https://github.com/cyan-yee/Physics-77-Final-Project---TESS-Exoplanet.git
1b. Then in your terminal, run:
- cd Physics-77-Final-Project---TESS-Exoplanet

2. Create Virtual Environment, use:
- python -m venv venv --> For Windows

3. Activate Virtual Environment, use:
- venv\Scripts\activate

4. Install Dependencies, use:
- pip install -r requirements.txt

5. Create your own branch to work on, use:
- git checkout -b (branch name)

6. Making changes + committing them, use:
- git add .
- git commit -m "Updates on what you did"

7. Push your changes back to main branch, so we can all see it:
- git push origin (branch name)

 -------------------------------------
# General Notes:

pull latest changes using:
- git checkout main
- git pull origin main
