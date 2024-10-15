# Overview

This repository contains the Python codes used to quantify Arctic Amplification (AA), which is characterized by a rapid surface air temperature (SAT) warming in the Arctic. The scripts provided here are specifically designed to recreate the figures presented in Huo et al. (2024).

## Citation
If you use this code or adapt it in your work, please cite the following paper:

Huo, Y., Wang, H., Lu, J., Fu, Q., Jonko, A.K., Lee, Y.J., Ma, W., Maslowski, W. & Qin, Y., 2024. Assessing Radiative Feedbacks and Their Contribution to the Arctic Amplification Measured by Various Metrics. *Journal of Geophysical Research: Atmosphere*, 129, e2024JD040880. https://doi.org/10.1029/e2024JD040880

## Quick Start
**Note:** NCL and NCO are required for Figs. 4-7.
1. Download HadCRUT, ERA5 and CESM2 LE monthly surface temperature data.

   HadCRUT: https://www.metoffice.gov.uk/hadobs/hadcrut5/data/HadCRUT.5.0.2.0/download.html
   ERA5: https://cds.climate.copernicus.eu/datasets/reanalysis-era5-single-levels-monthly-means?tab=download
   CESM2 LE: https://www.earthsystemgrid.org/dataset/ucar.cgd.cesm2le.atm.proc.monthly_ave.html
3. Run Fig1.py, Fig2.py, and Fig3.py to generate Figs.1-3 in Huo et al. (2024).
4. Download the CAM5 kernels (alb.kernel.nc, q.kernel.nc, t.kernel.nc, ts.kernel.nc) and radiative forcings (aerosol.forcing.nc, ghg.forcing.nc) here: https://zenodo.org/record/997902 
5. Download the NCL codes (q_kernel_to_plev.ncl, t_kernel_to_plev.ncl) to convert the kernels from hybrid sigma-pressure to standard pressure vertical coordinate from here https://github.com/apendergrass/cam5-kernels/blob/master/tools  
`ncl tools/t_kernel_to_plev.ncl`  
`ncl tools/q_kernel_to_plev.ncl`
6. Use ncremap to regrid data files to the same as kernel files. 
7. Run planck_lapserate_albedo_watervapor.py and cloud_feedback.py first to create the text files of zonal mean radiative feedbacks.
8. Run Fig4.py, Fig5.py, Fig6.py, and Fig7.py to create Figs.4-7 in Huo et al. (2024).

### Question/Comment
Please post it in the issues tab, or email me at yiling.huo at pnnl dot com
