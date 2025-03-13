# All necessary steps to implement new forecast configuration
## Step 0: WRF&WPS automation scripts path:
```
/home/pathop/local.01/wrffc.intel
```
## Step 0.1: prepare cropped global LCZ map for 1-km resolution domain
```
cp /disk/r108/wzhangcy/WPS/lcz_d4.tif /home/pathop/local.01/wrffc.intel/wrf/WPS.OneAPI.z
```
## Step 0.2: modify WRF cdrag for BEP
See file module_sf_bep.F
