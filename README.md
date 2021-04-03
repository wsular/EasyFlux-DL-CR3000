# EasyFlux<sup>&reg;</sup> DL for CR3000

EasyFlux® DL for CR3000 is a free CRBasic program that enables a CR3000
data logger to report fully corrected fluxes of CO<sub>2</sub>, latent heat
(H<sub>2</sub>O), sensible heat, and momentum from a [Campbell Scientific](https://www.campbellsci.com/)
open-path eddy-covariance (EC) system. For official program documentation and 
downloads, refer to the project website: 

> EasyFlux<sup>&reg;</sup> DL: Eddy-Covariance Datalogger Program  
> <https://www.campbellsci.com/easyflux-dl>

## What's Here

This repository contains a version of EddyFlux-DL customized to run on research
towers operated in partnership with the Laboratory for Atmospheric Research at
Washington State University. These towers focus on agricultural research sites
and belong to multiple networks and/or projects, including: 

* USDA ARS Long-Term Agroeconomic Research ([LTAR](https://ltarnetwork.org)) Network
* Landscapes in Transition Pacific Northwest (LIT-PNW) Project
* the [AmeriFlux](https://ameriflux.lbl.gov/) Network

Program modifications are intended to be backwards-compatible and accretive,
but not all changes satisfy these goals. To make identifying and merging changes 
introduced by the vendor easier, official vendor releases are also tracked here
in a separate and unrelated branch history. 


## Getting Started

### Required Equipment ###

* CR3000 datalogger ([CR3000](https://www.campbellsci.com/cr3000))
* Memory card module ([NL115](https://www.campbellsci.com/nl115), [NL116](https://www.campbellsci.com/nl116),
  or [CFM100](https://www.campbellsci.com/cfm100))
    * Network-enabled module is *highly recommended*
* Open-path infrared gas analyzer with ultrasonic anemometer:
    * [IRGASON](https://www.campbellsci.com/irgason), **OR**
    * [EC150](https://www.campbellsci.com/ec150) with [CSAT3A](https://www.campbellsci.com/csat3a)
* 16GB industrial-grade CompactFlash memory card

### Supported Optional Sensors

> ***N.B.*** *this version has known channel assignment conflicts which prevent
> certain optional sensors from being enabled, regardless of compatibility in
> prior versions. Refer to comments in the program file for complete details. In
> future versions, once compatibility is restored, this message will be removed.*

* Fine-wire thermocouple ([FW05](https://www.campbellsci.com/fw05),
  [FW1](https://www.campbellsci.com/fw1), or [FW3](https://www.campbellsci.com/fw3))
* Ambient temperature/relative humidity probe ([HC2S3](https://www.campbellsci.com/hc2s3)
  or [HMP-155A](https://www.campbellsci.com/hmp155a))
* Net radiometer ([CNR4](https://www.campbellsci.com/cnr4), [NR01](https://www.campbellsci.com/nr01),
  or [NL-Lite2](https://www.campbellsci.com/nr-lite2))
* Pyranometer ([CS300](https://www.campbellsci.com/cs300-pyranometer) or
  [LI200X](https://www.campbellsci.com/li200x-l))
* Quantum (PAR) sensor ([LI-190R](https://www.campbellsci.com/li190r-l) or
  [LI-190SB](https://www.campbellsci.com/li190sb-l))
* Infrared radiometer ([SI-111](https://www.campbellsci.com/si-111))
* Tipping bucket rain gage ([TE525](https://www.campbellsci.com/te525-l),
  [TE525WS](https://www.campbellsci.com/te525ws-l), [TE525M](https://www.campbellsci.com/te525mm-l),
  or TE525/TE525MM with 8 inch funnel)
* Averaging thermocouple ([TCAV](https://www.campbellsci.com/tcav-l))
* Water content reflectometer, for heat storage term (up to 2 of
  [CS616](https://www.campbellsci.com/cs616-reflectometer),
  [CS650](https://www.campbellsci.com/cs650),
  [CS655](https://www.campbellsci.com/cs655),
  [5TM](https://www.metergroup.com/environment/articles/meter-legacy-soil-moisture-sensors/#5tm),
  or [TDR-315/315L/310S](http://www.acclima.com))
* Soil heat flux plates (up to 4 of [HFP01](https://www.campbellsci.com/hfp01))
  or [HFP01SC](https://www.campbellsci.com/hfp01sc-l))
* Water content reflectometer, for vertical profiling (up to 6 of
  [5TM](https://www.metergroup.com/environment/articles/meter-legacy-soil-moisture-sensors/#5tm)
  or [TDR-315/315L/310S](http://www.acclima.com))
* Cup and vane wind set ([034B](https://www.campbellsci.com/034b))
* GPS receiver ([GPS16X-HVS](https://www.campbellsci.com/gps16x-hvs))
* Door switch sensor (magnetic reed switch, NO recommended)

### Quick Setup

1. Connect the datalogger to power and sensors as described in relevant manuals.
3. Update the unique calibration values in `src/constants.cr3` and upload to
   to the datalogger.
2. Modify the program file (`src/default.cr3`) as needed to:
    * enable or disable sensors 
    * update other constants, such as UTC offset
3. Upload the program file to the datalogger.
4. Update station variables, as necessary.

For additional details, refer to the [official user guide](https://www.campbellsci.com/easyflux-dl#documents_)
as well as files in the [`/doc`](/doc) folder.


## License

* The EasyFlux-DL code base is *Copyright (c) 2014, 2015 Campbell Scientific,
  Inc. All rights reserved.* For more details, refer to the official
  [project website](https://www.campbellsci.com/easyflux-dl).
* Original software contributions are licensed under 
  [the MIT License](https://opensource.org/licenses/MIT).
* Supporting documentation is subject to the Creative Commons Attribution 4.0
  International ([CC-BY-4.0](https://creativecommons.org/licenses/by/4.0/)).
