Greenhouse Gas Monitoring Tower Datalogger Program
==================================================

Vineyard Pilot Study (2015)
---------------------------

This is an adaption of the [datalogger program][1] running at greenhouse gas 
monitoring towers which are part of the [REACCH project][2]. The program 
combines 10 Hz measurements of CO2 and H2O with 3D wind speeds to generate near
real-time surface fluxes of CO2, latent & sensible heat. Additional 
meteorological statistics are produced at 5 & 30 minute intervals. 

  [1]: https://bitbucket.org/wsular/2011-reacch-tower-logger
  [2]: http://www.reacchpna.org

The main repository (here) contains the datalogger program only. A second, 
private repository hosts deployment-specific information like network addresses 
and access credentials. 

* Main repository (public): <https://bitbucket.org/wsular/2015-vineyard-tower-logger>
* Deployment-specific (private): <https://bitbucket.org/wsular/2015-vineyard-tower-secrets>

### Pre-requisites ###

* [CR3000](https://campbellsci.com/cr3000)
    * network-enabled with an [NL115](https://campbellsci.com/nl115) module
    * `CR3000.Std.31` or newer firmware
* Base sensor suite
    * Infrared CO<sub>2</sub>/H<sub>2</sub>O analyzer with ultrasonic 
      anemometer ([EC150](https://www.campbellsci.com/ec150) + 
      [CSAT3A](https://www.campbellsci.com/csat3a))
    * Cup and vane wind set ([034B](https://www.campbellsci.com/034b))
    * Temperature/humidity probe ([HMP-155A](https://www.campbellsci.com/hmp155a))
    * Net radiometer ([NL-Lite2](https://www.campbellsci.com/nr-lite2))
    * <acronym title="photosynthetically active radiation">PAR</acronym> sensor
      ([LI-190SB](https://www.campbellsci.com/li190sb-l))
    * Tipping bucket rain gage ([TE525WS](https://www.campbellsci.com/te525ws-l))
* Optional sensors
    * Soil moisture/temperature probes ([TDR-315L](http://www.acclima.com))
    * Soil heat flux plates ([HFP01](https://www.campbellsci.com/hfp01))
    * Spectral reflectance (<acronym title="normalized difference vegetation
      index">NDVI</acronym>/<acronym title="photochemical reflectance 
      index">PRI</acronym>) sensors ([SRS series](http://www.decagon.com/en/canopy/canopy-measurements/spectral-reflectance-sensor-srs/))
* Communications & power hardware
    * GPS receiver ([GPS16X-HVS](https://www.campbellsci.com/gps16x-hvs))
    * modem
    * ?



### License ####

This work is licensed under [The MIT License][3] adapted from proprietary works purchased from Campbell Scientific
Inc, who reserves all rights to that original work (which is not present in
this repository).

  [3]: http://opensource.org/licenses/MIT
