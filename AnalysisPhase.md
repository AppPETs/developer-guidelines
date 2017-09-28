# Analysis Phase

- Is there a need of data collection?

  - The principle **Privacy by Design** *(link with details to intro)* must be taken into consideration when planning app connection behavior and collection of user data
*(Ausführen)*

  - **Device-specific information** gathered has to follow some restrictions

    - Unique identifiers (UDID, IMEI, MAC addresses etc.) are obtained only after an user-confirmed Opt-In and only if they are necessary for the specific purpose
    - Unique identifiers are not used for individual user tracking
    - Tracking IDs (IDFA, AAID) are transmitted in encrypted form *(sollte eigentlich gar nicht drin sein, in irgendeiner Form wird es aber dennoch einfließen.)*
    - User-disabled tracking options have to be respected *(das ist aber nur opt out, ist an anderer Stelle vielleicht schon erwähnt, also hier nochmal stärker machen - kann auch in aderer Form erwähnt werden, aber ist eben wichtig hier unseren Fokus zu schärfen)*

  - If the app is planned to process personal data, a **Privacy Policy** must be implemented and must include the minimum requirements of the local data protection laws
*(Daten auf dem Gerät sind immer auch möglicherweise personalisierbar ... -> grundsätzlich immer möglich Daten für Rückschlüsse nutzbar? -> Datenminimierung)*
*(keine minimale Compliance, sondern ordentlicher Datenschutz)*

    * this implies, but is not limited to
      * Which types of personal data are accessed and why?
        * How will this data be used?
        * How will this data be stored?
        * Which third-parties will receive access to the data and under what conditions?
      * Statement, that collected data will be protected from unauthorized access
      * Contact data of the actual Data Protection Officer
      * Statement on how to access personal saved data as a user
      * Statement on how to initiate personal data deletion as a user
    * updated information about privacy policies can be found here
      * https://****ADD EXTERNAL/ULD LINK HERE****
*(hier einfach die basalen Punkte, (die zeitlos sind) übernehmen*
*(Enisa Rempfehlungen für Smartphones vielleicht anwendbar -> checken)*


  ### Is data leaving the main ecosystem?

  - definition of the level of data leakage
    - is data leaving the "local boundary"
    - is data leaving the "eco system boundary"
    - is data leaving the "3rd party boundary"
  - service provider needs data processing contract *(german ADV)*
*(auch die Auftrragsdatenverarbeiter verpflichten auf Datenschutzprinzipien)*

  ### Which data needs which level of protection? 

  Special categories of data are placed under particular protection of the law.

  0. no personal reference: no protection necessary *(gibt es eigentlich nicht)* *(alterativ: Folgen der Ausnutzung? -> Keine Folgen)*

  1. person related or relatable: protection necessary

  2. sensitive data: processing not recommended *(was hat das für einen praktischen Wert? Lieber Leitlinien: Zweckbindung, sonst nicht)*

  3. dangerous data: processing prohibited 
*(was ist da genau gemeint, Gefahr für Leib und Leben? / streichen?)* 
*(anstatt dessen: hier streichen und stattdessen eher eine Kategorie mögliche Folgen (Gefahrenpotential)-> Also: Konkretisierung)*

     ​#### Sensitive Data

(REM: Ergänzungen vielleicht in eine Art Kasten)  
Amongst these are personal data revealing racial or ethnic origin, political opinions, religious or philosophical beliefs, or trade union membership, and the processing of genetic data, biometric data for the purpose of uniquely identifying a natural person, data concerning health or data concerning a natural person's sex life or sexual orientation. These data generally may only be used where the data subject has given explicit consent regarding these very categories of information.

#### Extend of data used

(REM: Ergänzungen vielleicht in eine Art Kasten)  
Where the information on individuals used by the app is particularly comprehensive, exposing their conduct or characteristics, particular attention needs to be paid to the protection of those data.

  ### Is data used that must be deletable on user demand? (@ULD: which data is affected)
*(grundsätzlich immer)*

  - a  routine must be implemented to ensure full deletion of user data on demand
    - all saved data from the user must be deletable
    - this applies also to data stored in the cloud
    - if no such routine is implemented, the user is provided with contact data to send a deletion request

  ### Special protection

- are persons with special protection needs concerned? *(was dann @ULD? betroffene Schützenswert? Kinder etc.)*

(REM: Ergänzeungen vielleicht in eine Art Kasten)
For instance if children or other persons who require particular legal protection are involved, the processing of data might be more restricted than otherwise.

## Risk Assessment

(@Introduction.md - after each Development Phase the risk needs to be reassessed)
*(kommt in DesignPhase nochmal, vornehmen anhand der oben genannten Kriterien)*
*(was für Risiken eigentlich? was wird vom Entwickler erwartet?)*

- all processed data needs to be analysed to specify a risk level of potential malicious use of the data
  - based on these risk levels special protection routines need to be applied *(hier auf standardisierte Risk-Level verweisen @ULD habt ihr da was?)* 



**Examples:**

