# Burn_wounds_pilot_study
This repository contains the code needed to analyse the data corresponding to the pilot study of 15 pediatric burn wound patients. This analysis consists of two parts: the HAPI region analysis and the LSCI vs. LDI comparison. Below, an overview of the used scripts is given. All patient data is saved in: <int>"P:\TNW\BMPI\Patientdata\HAPI Burn wound study</int> 

## HAPI region analysis
The goal of this analysis was to provide an overview of burn wound healing time (<14 days, 14-21 days, and >21 days) versus measured handheld LSCI perfusion (in perfusion units (p.u.)) per region. In this case, regions of 24x24 pixels were used. The steps and corresponding code are summed up below.

### 1) Registration of LSCI perfusion maps to LSCI color images
For this, the MATLAB code: **hapi_burns_perfusion_color_registration.m** was used.

### 2) Manual deliniation of burn wound areas
Done by 2 researchers, reviewed by one burn wound expert.

### 3) Manual delineation of areas healing within 14-21 days and >21 days
Done by 1 researcher, reviewed by one burn wound expert and one burn wound surgeon.

### 4) Filtering of perfusion data - removal of specular reflections and regions with a low signal-to-background ratio, and apply motion-artefact correction
The MATLAB code **filter_SpecularReflections_SNR_MAC.m** was used for this.

### 5) Resizing of the perfusion maps to create 24x24 pixel areas
Maaike has the code for this, NaNs are ignored when calculating the regions


