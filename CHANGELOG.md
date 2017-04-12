Change Log for GHG Monitoring Tower Program
===========================================

Next release
------------

> This release requires operating system `CR3000.Std.31` or newer. 

<p></p>

> Previous telemetry integrations (email, ScadaBR) have been removed in this
> version.

<p></p>

> The data processing core is now built upon [EasyFlux-DL by Campbell 
> Scientific](www.campbellsci.com/easyflux-dl). This represents a substantial 
> improvement in near real-time evaluation of carbon and energy fluxes.

### Data Table Changes

* Remove 5-min flux/met and soil data tables
* Remove references to Picarro or Los Gatos instruments from `extra_info` table
* Remove conditionally-included data table `tsdata_extra`
* Fix issue which caused column `hfp_installed` in data table `site_info` to
  always be false
* New columns associated with alt. CO2 flux calculations (see *Other changes*)
    * `CO2_hf` in `tsdata` is carbon dioxide density derived using high-freq
      sonic temperature instead of thermistor temperature
    * in `stats30` table:
        * `Fc_hf_wpl` is CO2 flux with WPL corrections
        * `CO2_hf_mg_m3_Avg` is mean CO2 density
        * `CO2_hf_mg_m3_Std` is standard deviation of CO2 density

### Instrumentation Changes

* Remove soil temp/moisture probes (8x Decagon Devices 5TM)
* Change soil temperature probes in layer above soil heat flux plates 
  (2x CSI model 109 probes &rarr; 1x CSI averaging thermocouple)
* Remove prototype NDVI/PRI sensors (Decagon Devices)
* Change PAR sensor back to LI190SB with Campbell Scientific-specific cabling
  (versus Licor direct-purchase LI190R unit)

### Other changes

* Remove scheduled reporting to ScadaBR instance
* Remove automated email reporting
* Improved settings menu provides guidance on units where appropriate
* Produces two carbon dioxide flux estimates: the second value `Fc_hf_wpl` is
  calculated using CO2 density derived using high-frequency sonic temperature
  instead of slow-response thermistor temperature; for more information, refer
  to http://dx.doi.org/10.1016/j.agrformet.2016.07.018

### Changes w.r.t EasyFlux v1.0

* Incorporate updates from EasyFlux v1.1 release
    * FIX: correct transposed values in constant used for dewpoint calculations
    * Non-substantive formatting changes
* Increased instrumentation support
    * Additional rain gage models (TE525, TE525WS, TE525 or TE525MM used with
      8" funnel adapter)
    * Additional temperature/humidity probes (HC2S3, HMP45C)




Initial commit
--------------

Import EC tower source code from Vineyard Pilot Study (2015-2017), which is
extension of the Regional Approaches to Climate Change Study code base. 

* Root commit: https://github.com/patricktokeeffe/2015-vineyard-eddyflux-tower/commit/0dff2cd0232c1638ad56fe3326692ccc36375029
* See also: https://github.com/wsular/reacchpna-eddyflux-tower

