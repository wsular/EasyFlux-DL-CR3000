*Datalogger Program Source Code*

Sensors are wired to a CR3000 as specified in `../doc/wiring_details.ods` 
([PDF version][1]).

  [1]: https://bitbucket.org/wsular/2015-vineyard-tower-logger/downloads/wiring_details.pdf

1. Edit values in `email-template.cr3` and save as `email.cr3` then save and 
   encrypt to `email_Enc.cr3`. Load `email_Enc.cr3` onto the CR3000's `CPU:`
   drive.
2. Repeat pattern in step 1 for `scadabr-template.cr3`.
3. Load `default.cr3` onto the CR3000's `CPU:` drive.
