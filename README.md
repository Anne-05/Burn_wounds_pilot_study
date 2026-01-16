# Burn_wounds_pilot_study
This repository contains the code needed to analyse the data corresponding to the pilot study of 15 pediatric burn wound patients. This analysis consists of two parts: the HAPI region analysis and the LSCI vs. LDI comparison. Below, an overview of the used scripts is given. All patient data is saved in: <ins>"P:\TNW\BMPI\Patientdata\HAPI Burn wound study"</ins> 

## HAPI region analysis
The goal of this analysis was to provide an overview of burn wound healing time (<14 days, 14-21 days, and >21 days) versus measured handheld LSCI perfusion (in perfusion units (p.u.)) per region. In this case, regions of 24x24 pixels were used. The steps with corresponding used code are summed up below.

1. Registration of LSCI perfusion maps to LSCI color images
For this, the MATLAB code: **hapi_burns_perfusion_color_registration.m** was used.

2. Manual deliniation of burn wound areas
Done by 2 researchers, reviewed by one burn wound expert.

3. Manual delineation of areas healing within 14-21 days and >21 days
Done by 1 researcher, reviewed by one burn wound expert and one burn wound surgeon. The MATLAB code: **hapi_burns_boundary_selection.m** was used for this.

4. Filtering of perfusion data - removal of specular reflections and regions with a low signal-to-background ratio, and apply motion-artefact correction
The MATLAB code **filter_SpecularReflections_SNR_MAC.m** was used for this.

5. Resizing of the perfusion maps to create 24x24 pixel areas
Maaike has the code for this, NaNs are ignored when calculating the regions

6. Plot data as histograms and as violin plots
Maaike has the code for this, NaNs are ignored when calculating the regions



## HAPI LSCI versus LDI comparison
The goal of this analysis was to compare LSCI perfusion and LDI flux per region of 100x100 pixels and express that per burn wound healing time category (<14 days, 14-21 days, and >21 days). The steps with corresponding used code are summed up below.

### 1) Registration of LSCI perfusion maps to LSCI color images
For this, the MATLAB code: **hapi_burns_perfusion_color_registration.m** was used if the raw data was not analysed in HAPI region analysis yet.

### 2a) Registration of LDI perfusion maps to LDI color images
In some exeptional cases this alignment was incorrect, therefore an additional registration step was added and the MATLAB code **hapi_burns_ldi_perf_to_ldi_registration.m** was used for this.

### 2b) Registration of LDI color images to LSCI color images
The MATLAB code: **hapi_burns_ldi_hapi_registration.m** was used to register the LDI color images to the LSCI color images manually.

### 3) Manual delineation of areas healing within 14-21 days and >21 days
Same step as in HAPI region analysis

### 4) Filtering of perfusion data - removal of specular reflections and regions with a low signal-to-background ratio, and apply motion-artefact correction
Same step as in HAPI region analysis

### 5) Resizing of the perfusion maps to create 100x100 pixel areas
Maaike has the code for this, NaNs are ignored when calculating the regions

### 6) Plot data in scatter plot / histogram data
Maaike has the code for this, my R code is: **statisticalAnalysis.R**









