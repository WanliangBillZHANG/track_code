# All necessary steps to implement new forecast configuration
## Step 0: WRF&WPS automation scripts path:
```
export WRF_CDRAG='/home/pathop/local.01/wrffc.intel/wrf_cdrag'
```
## Step 0.1: prepare cropped global LCZ map for 1-km resolution domain
```
cp /disk/r108/wzhangcy/WPS/lcz_d4.tif ${WRF_CDRAG}/WPS.OneAPI.z
```
## Step 0.2: modify WRF cdrag for BEP
See file module_sf_bep.F
## Step 0.3 modify WRF namelist.input by changing script
```
$WRF_CDRAG/wrf/met_WRFV3/test/em_real/runWRF_EPD_d4nudging.csh
```
