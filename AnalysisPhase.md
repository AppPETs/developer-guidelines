# Analysis Phase

- Is there a need of data collection *(Müssen Daten erfasst werden?)*

  - The principle **Privacy by Design** must be taken into consideration when planning app connection behavior and collection of user data *(Sind hier AppPETs übertragungen ausgenommen?)*

    - All data protection-relevant aspects related to the end user must be planned to be secure
    - All options for ensuring data protective behavior have to be preconfigured in a way a user can not accidentally lose personal information
    - Data access takes place in line with data economy principles
    - Data not immediately used may not be collected
    - Passing data to third parties requires an Opt-In from the user

  - **Device-specific information** gathered has to follow some restrictions

    - Unique identifiers (UDID, IMEI, MAC addresses etc.) are obtained only after an user-confirmed Opt-In and only if they are necessary for the specific purpose
    - Unique identifiers are not used for individual user tracking
    - Tracking IDs (IDFA, AAID) are transmitted in encrypted form
    - User-disabled tracking options have to be respected

  - If the app is planned to process personal data, a **Privacy Policy** must

    be implemented and must include the following

    - Which types of personal data are accessed and why?
      - How will this data be used?
      - How will this data be stored?
      - Which third-parties will receive access to the data and under whatconditions?
    - Statement, that collected data will be protected from unauthorized access
    - Contact data of the actual Data Protection Officer
    - Statement on how to access personal saved data as a user
    - Statement on how to initiate personal data deletion as a user

- Is data leaving the main ecosystem? *(Verlassen Daten mein Ökosystem?)*
  - deffinition of the level of data leakage
    - is data leaving the "local boundry"
    - is data leaving the "eco system boundry"
    - is data leaving the "3rd party boundry"
  - service provider needs processing regulation *(Dienstleister benötigt ADV)*

- Which Data needs which data protection level? *(Welche Daten benötigen welches Schutzniveau?)*
  - no protection necessary *(nicht schützenswert und ohne personenbezug)*
  - protection necessary *(Personenbeziehbar und personenbezogen)*
  - processing not suggested / sensitive data *(sensible Daten)* 
  - porcessing prohibited / dangerous data *(Klassifikation nach Gefahr für Leib & Leben)*

- Is data used that must me able to be deleted by user demand?

  - a  routine must be implemented to ensure full user data deletion on demand
    - all saved data from the user must be deletable
    - this applies also to cloud-saved user data
    - if no routine is implemented, user is provided storage server provider contact data to send a data deletion request

- affected person especially protected? *(betroffene Schützenswert? Kinder etc.)*

==> Risk Assessment *(Risikobewertung)*

- all processed dates need to be investigated to elevate a risk level of potential malisous use of the dates
  - based on these risk levels special protection routines need to be used *(hier ggf. standardisierte Risk-LEvel definieren, benennen oder verweisen)* 



**Examples:**

