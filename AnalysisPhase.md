# Analysis Phase

- Is there a need of data collection?

  - The principle **Privacy by Design** *(link with details to intro)* must be taken into consideration when planning app connection behavior and collection of user data

  - **Device-specific information** gathered has to follow some restrictions

    - Unique identifiers (UDID, IMEI, MAC addresses etc.) are obtained only after an user-confirmed Opt-In and only if they are necessary for the specific purpose
    - Unique identifiers are not used for individual user tracking
    - Tracking IDs (IDFA, AAID) are transmitted in encrypted form
    - User-disabled tracking options have to be respected

  - If the app is planned to process personal data, a **Privacy Policy** must be implemented and must include the minimum requirements of the local data protection laws

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

  ### Is data leaving the main ecosystem?

  - definition of the level of data leakage
    - is data leaving the "local boundary"
    - is data leaving the "eco system boundary"
    - is data leaving the "3rd party boundary"
  - service provider needs data processing contract *(german ADV)*

  ### Which data needs which level of protection?

  0. no personal reference: no protection necessary

  1. person related or relatable: protection necessary

  2. sensitive data: processing not recommended

  3. dangerous data: processing prohibited

     ​

  ### Is data used that must be deletable on user demand? (@ULD: which data is affected)

  - a  routine must be implemented to ensure full deletion of user data on demand
    - all saved data from the user must be deletable
    - this applies also to data stored in the cloud
    - if no such routine is implemented, the user is provided with contact data to send a deletion request

  ### Special protection

- are persons with special protection needs concerned? *(was dann @ULD? betroffene Schützenswert? Kinder etc.)*

## Risk Assessment

(@Introduction.md - after each Development Phase the risk needs to be reassessed)

- all processed data needs to be analysed to specify a risk level of potential malicious use of the data
  - based on these risk levels special protection routines need to be applied *(hier auf standardisierte Risk-Level verweisen @ULD habt ihr da was?)* 



**Examples:**

