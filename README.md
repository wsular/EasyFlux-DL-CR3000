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
    * `CR3000.Std.27` or newer firmware
* Sensors and hardware (see documentation)


### License ####

This work is licensed under [The MIT License][3] adapted from proprietary works purchased from Campbell Scientific
Inc, who reserves all rights to that original work (which is not present in
this repository).

  [3]: http://opensource.org/licenses/MIT
