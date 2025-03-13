# All necessary steps to implement new forecast configuration
## Step 1: Define a new WRF&WPS automation scripts path:
```
export WRF_CDRAG='/home/pathop/local.01/wrffc.intel/wrf_cdrag'
```
## Step 2: prepare cropped global LCZ map for 1-km resolution domain
```
cp /disk/r108/wzhangcy/WPS/lcz_d4.tif ${WRF_CDRAG}/WPS.OneAPI.z/
```
## Step 3: modify WRF cdrag for BEP
```
$WRF_CDRAG/met_WRFV3/phys/module_sf_bep.F
```
See updated file module_sf_bep.F
## Step 4: modify WRF namelist.input by changing script
```
$WRF_CDRAG/met_WRFV3/test/em_real/runWRF_EPD_d4nudging.csh-num_metgrid_levels-34
```
See updated file runWRF_EPD_d4nudging.csh-num_metgrid_levels-34
## Step 5: modify WPS automation script
```
$WRF_CDRAG/WPS.OneAPI.z/run_sepSST.csh.6h
```
See updated file run_sepSST.csh.6h
## Step 6: compile WRF
```
./clean -a
./configure
./compile em_real >& log.compile
```
## Step 7: invoke $WRF_CDRAG as usual
