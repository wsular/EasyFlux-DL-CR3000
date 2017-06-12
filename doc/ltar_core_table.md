Data Table: `LTAR_CORe`
===========================================================

LTAR Common Observatory Repository (CORe) 
---------------------------------------------------------

This table is designed to facilitate data reduction and submission of meteorology data to
the USDA LTAR Common Observatory Repository (CORe) database. For more information, refer to 
[Common Observatory Meteorology Data Concept of Operations.pdf](https://www.ars.usda.gov/ARSUserFiles/np211/LTAR%20Meteorology%20Concept%20of%20Operations%20FINAL%20150929.pdf)
or visit the project's [homepage](https://www.ars.usda.gov/natural-resources-and-sustainable-agricultural-systems/water-availability-and-watershed-management/docs/long-term-agroecosystem-research-ltar-network/). 

* Data table name: `LTAR_Met`
* Record interval: 15 minutes, aligned to midnight

Download field name lookup table in JSON format from [here](../src/ltar_core_lut.json).

| Table Field Name  | Units  | Agg type | LTAR Phase | LTAR CORe variable | LTAR CORe units | Description |
|-------------------|-----------|-------|:-----:|-------------------|-----------|-------------------------|
| amb_tmpr_Avg      | C         | mean  |   1   | AirTemperature    | Degrees C | ambient air temperature |
| rlst_wnd_spd      | m/s       | mean  |   1   | WindSpeed         | m/s       | resultant wind speed |
| wnd_dir_compass   | degrees   | mean  |   1   | WindDirection     | Degrees   | resultant wind direction |
| RH_Avg            | %         | mean  |   1   | RelativeHumidity  | percent   | relative humidity |
| Precipitation_Tot | mm        | total |   1   | Precipitation     | mm        | liquid precipitation |
| amb_press_Avg     | kPa       | mean  |   2   | AirPressure       | kPa       | barometric pressure
| PAR_density_Avg   | umol/(s m^2) | mean |   2   | PAR        | umol m^-2 s^-2 | photosynthetically active radiation (PAR) |
| batt_volt_Avg     | V         | mean  |   2   | BatteryVoltage    | Volts DC  | system input voltage |
| panel_tmpr_Avg    | C         | mean  |   2   | LoggerTemperature | Degrees C | logger panel temperature |
| std_wnd_dir       | degrees   | stdev |   -   | - | - | standard deviation of wind direction |
| VPD_air           | kPa       | mean  |   -   | - | - | vapor pressure deficit |
| Rn_meas_Avg       | W/m^2     | mean  |   -   | - | - | net radiation |
