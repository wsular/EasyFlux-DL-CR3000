# Changelog

Revision history for our modified version of EasyFlux&reg; DL for CR3000.

> *This project does not yet implement semantic versions.*  
> *Supported sections: Security, Issues, Fixed, Added, Changed, Deprecated, Removed*

## [Unreleased]

* New data table `LTAR_CORe` represents 15min meteorology data submission
  format for sites in the USDA Long-Term Agroecosystem Research (LTAR) program
    * Covers both Phase 1 & Phase 2 measurements
    * Anticipates other variables of interest


## [ProgSig 20626] 2017-06-02

### Fixed

* Unique calibration constants can now be edited in the field by changing the
  file `CPU:constants.cr3` and reloading the program. The include file can be
  edited locally on the datalogger keypad, or remotely via support software.

### Added

* Enable field editing of calibration sensitivity values for net radiometer
  (NR-Lite2), quantum sensor (LI-190SB), and soil heat flux plate (HFP01).

----

## [ProgSig 65148] 2017-05-12

### Fixed

* Retrieve alternate CO<sub>2</sub> density value from `EC100()` instruction 
  which is required to complete secondary CO<sub>2</sub> flux calculations.
* Correct errors in calculation of friction velocity (`old_u_star`) and Obukhov
  length (`old_L`) 

### Changed

* Declare GPS receiver variables *Public* so they can be viewed in real-time.
* Data table: **Flux**
    * Table now includes columns previously saved in *Flux_Notes* data table.
* Data table: **Flux_Notes**
    * Table is now merged into *Flux* data table.

----

## [ProgSig 45290] 2017-05-12

This revision is based on *EasyFlux DL for CR3000 v.1.1* by Campbell Scientific.

* Data logger operating system `CR3000.Std.31` or newer is required.
* If using a model EC150 (not IRGASON), then EC100 OS version 7.01 or later is
  required.

### Issues

* Secondary CO<sub>2</sub> flux calculations are incomplete due to missing
  alternate CO<sub>2</sub> density value (wrong command sent to `EC100()`
  instruction), and intermediate array being under sized.
* Column `old_CO2_hf_mg_m3_Avg` is missing units in table *Flux*.
* Changes to wiring locations prevent certain inactive sensors from being used.
* Comments on GPS receiver integration incorrectly refer to ports C7/C8 instead
  of ports C3/C4.
* UTC offset used by `GPS()` instruction is a hard-coded constant.
* Value of "0" used for `MaxTimeDiff` parameter in `GPS()` instruction may
  cause skipped scans in older hardware/firmware.
* Unique calibration constants cannot be edited via *ConstTable* because 
  program is too large to edit in datalogger memory.

### Fixed

* Correct spelling of "Kelvin" for public variable `T_nr` (radiometer body
  temperature). Does not affect data tables since variable is not in use.

### Added

* Re-introduce the pre-EasyFlux calculation of carbon dioxide (CO<sub>2</sub>)
  flux based on standard reported CO<sub>2</sub> mass density (labeled `old_Fc_wpl`)
  and add second, parallel flux calculation (labeled `old_Fc_hf_wpl`) using 
  CO<sub>2</sub> density derived using high-frequency sonic temperature instead
  of slow-response thermistor. This feature is expected to be removed and is 
  already deprecated. **Requires EC150 gas analyzer operating with EC100 control 
  unit having firmware version 7.01 or later.** References:
    * Helbig et al. *Addressing a systematic bias in carbon dioxide flux measurements 
      with the EC150 and the IRGASON open-path gas analyzers.* Agricultural and Forest 
      Meteorology, Volume 217, Supplement 1, January–December 2016, Pages 391-392.
      Online: <https://doi.org/10.1016/j.agrformet.2016.07.018>
    * Campbell Scientific. *Improved Flux Measurements from Campbell Scientific
      Open-Path Gas Analyzers: Utilizing Sonic Temperature to Account for Spectroscopic
      Effects on CO2 Density.* May 23, 2017. Online:
      <https://s.campbellsci.com/documents/us/miscellaneous/Improved-Flux-Measurements-from-Campbell-Scientific-Open-Path-Gas-Analyzers.pdf>
* Add support for using either Acclima TDR-315 or Decagon 5TM soil probes with 
  the soil heat flux plates.
* Add support for separate vertical profile of up to six soil probes. Probes
  can be Acclima TDR315 or Decagon 5TM sensors, but not a mixture. Addresses
  must increase sequentially starting with "`3`".
* Add support for MetOne model 034B cup-and-vane anemometer.
* Add support for Garmin GPS16X-HVS GPS receiver. 
* Add support for door switch sensor. 
* Add support for related rain gage models (TE525, TE525WS, and TE525 or
  TE525MM with 8in funnel)
* Add support for selecting ambient T/RH probe using program constants, instead
  of modifying values in source code.
* Add support for editing unique calibration constants via the *ConstTable*

### Changed

* Wiring configuration
    * Move net radiometer input from DF6 to DF10 (reason not specified)
    * Move PAR (quantum) sensor input from DF8 to DF11 (reason not specified)
    * Move TCAV input from DF11 to DF5 (reason not specified, allows 2 sensors)
    * Move ambient T/RH probe inputs from SE27/SE28 to DF8/DF9 (reason not specified)
    * Move rain gage input from P1 to P2 (reason not specified)
    * New SDI-12 sensors (Acclima TDR315 & Decagon 5TM) use port C7 (reason not
      specified for using C7 instead of C5 along with CS65X)
    * New cup-and-vane anemometer uses ports SE23, VX1 and P1
    * New GPS receiver uses "`Com2`" ports C3/C4
    * New door switch sensor uses control port C8
* Data table: **Time_Series**
    * New column `CO2_hf` inserted after `H2O_sig_strgth` contains CO<sub>2</sub>
      mass density (mg/m<sup>3</sup>) derived using high-frequency ultrasonic
      anemometer "sonic temperature" value instead of slow-response thermistor 
      ambient temperature.
* Data table: **Flux**
    * Thirteen new columns are inserted at front of table which contain results
      from the simplified (pre-EasyFlux) eddy-covariance computational model
      using CO<sub>2</sub> density calculated using both high-frequency (`CO2_hf`)
      and slow-response (`CO2`) ambient temperature values: `old_L`, `old_u_star`,
      `old_Fc_wpl`, `old_Fc_hf_wpl`, `old_LE_wpl`, `old_Hc`, `old_Uz_Std`,
      `old_CO2_mg_m3_Avg`, `old_CO2_mg_m3_Std`, `old_CO2_hf_mg_m3_Avg`,
      `old_CO2_hf_mg_m3_Std`, `old_Tc_Avg`, `old_amb_press_Avg`
    * Four new columns inserted after `PAR_density_Avg` contain data from MetOne
      cup-and-vane anemometer (model 034-B): `cupvane_WS_Avg`, `cupvane_WS_rslt_Avg`,
      `cupvane_WD_rslt_Avg`, `cupvane_WD_csi_Std`
* Data table: **Flux_Notes**
    * New column `door_is_open_Hst` inserted after `Lv` contains time-weighted
      average of enclosure door status where non-zero values indicate door was
      open for a duration of the sampling interval.

### Deprecated

* The newly-added secondary flux calculations are considered temporary and are
  already deprecated. 

### Removed

* Functionality from old (pre-EasyFlux DL) code base that was not re-incorporated:
    * Remove scheduled reporting to ScadaBR
    * Remove automated email reporting
    * Remove 5-min statistics data tables
    * Remove "site info" and "extra info" data tables
    * Remove high-frequency table for "extra" sensors
    * Remove support for PAR sensors with factory (non-CSI) cable configuration
    * Remove support for using pair of thermistors in place of an averaging 
      soil thermocouple
    * Remove support for experimental Decagon NDVI/PRI sensors
    * Remove support for Picarro Inc CO<sub>2</sub>/CH<sub>4</sub>/H<sub>2</sub>O
      trace gas analyzer (model G2301f)
    * Remove support for Los Gatos Research N<sub>2</sub>O/CO trace gas anlayzer
      (serial no. 10-0038)
