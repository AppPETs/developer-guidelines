# Design Phase

During the design phase, the system is designed to satisfy the requirements identified in the previous phases.
The identified requirements need to be transformed into a System Design Document that describes the design of the system which will be used for the implementation of the system.

## Objectives/Goals

The successfull completion of the design phase should include:

* Transformation of **all** requirements into detailed specifications covering **all** aspects of the system
* Assessment and mitigation of data security risks
* Assessment and mitigation of privacy risks (infringements of informational self-determination)
(DG: noch andere Risiken?)

## Deliverables

* Architecture document
* Planning of test cases and testing schedules
* Data security risk assessment and mitigations
  * Where no mitigations are given, justification for the acceptance of security risks is necessary
* Privacy risk assessment and mitigations justification for the acceptance ofprivacy risks is necessary
* Users of the system need to be informed about known risks and shortcomings of risk mitigations

# Design activities

## System Architecture
The system's architecture should give an overview of all physical and logical components of the system and how they interact with each other,
*(DG: including the data flows(?))*

## Perform Risk Management
Threats and vulnerabilities that exist in the project’s environment or that result from interaction with other systems need to be identified during this phase.
**You cannot consider the design phase complete unless you have a threat model or models that include such considerations.** Threat models are critical components of the design phase and reference a project’s functional and design specifications to describe vulnerabilities and mitigations.

###Code that was created by external development groups in either source or object form.
It is very important to evaluate carefully any code from sources external to your team. Failure to do so might cause security vulnerabilities about which the project team is unaware.

###Threat models that include all legacy code if the project is a new release of an existing program.
Such code could have been written before much was known about software security, and therefore could contain vulnerabilities.
*(DG:wording/explain)*

### Security Risk Management
The threat models for all functionality identified during the analysis phase need to be completed. Threat models typically must consider the following areas:

* All code exposed on the attack surface and all code written by or licensed from a third party.
* All features and functionality.
* New features or functionality added in the updated version.

### Privacy Risk Management

Questions that should be addressed during the Privacy Risk Assessment:

* Which personal data is collected?
* What is the compelling customer value proposition and business justification?
* Which notice and consent possibilities are offered?
* What controls are provided to users and enterprises in order to supervise the flow, processing and access of data?
* How is unauthorized access to personal information prevented?

* Which risks are triggered through the storage of data?
  * Which data is stored local on the device?
  * Which data is stored on remote devices?
  * What risks through potential privacy leaks are linked to the place of storage?

## Problems
*(Arbeitsnotizen:)*
*(TODO Verbinden von Problemen und technischen Umsetzungsmöglichkeiten. Welche Optionen existieren, wo sind sie angebracht und welche Implikationen haben sie.)*
*(zB Vermeidung eines jeden Datenabflusses, hier gute Beispiele einbringen: Wetterapp, genau oder ungenau, nächste Wetterstation, Rasterung, etc)*
*(-> Designentscheidungen sollen hier wohl überlegt sein.)*
*(Bewertung von Daten? Oder: alle Daten sind immer sensibel?)*
*(-> nur wenn nötig nur für den bestimmten Zweck und nur möglichst sicher verarbeitet....)*
*(als App-Entwickler weiss man gar nicht wo am Ende aggregierte Daten verwendet werden)*

* Data receiving problematically? (Datenabruf problematisch? (Metadata & PKR))
*(technisch umsetzbar / machbar?)*

* Data sending problematically? (Datenversand problematisch?)

* Data processing problematically? (Datenverarbeitung problematisch?)

* Interaction with 3rd parties? (Interaktion mit dritten? (z.B. beim Bezahlvorgang))
  * No? (z.B. bei Bezahlvorgang (Barzahlung = unproblematisch))
  * Yes? (z.B. beim Bezahlvorgang (paypal / Kreditinstitut etc.))
    * back to point -> "how can the following steps possibly help?"

## Technical Measures
Which technical measures can be applied to address the identified risks.
Possible counter measures include:

* Cryptography
* Anonymisation
* Pseudonymisation

*(-> PLib (!) Beispiele sind hier ein guter Anknüpfungspunkt)*

**(an jedem Schritt des Design möglichst überlegen wie man hier datenschutzfreundlich umsetzen kann...)**

TODO: Add links and examples

## Organisational Measures
Organisational measures include:

* Transparency
  * Communication of risks and purpose of data collection to the end user
* Intervenability
  * Means for the end user to delete and modify data
  * which extend functionality is necessary
  * contact person
* Availability
  * SDM (Standard Datenschutz Modell)
* Data minimisation

TODO: Add links and examples

# TODO:
* licence of SDL documents

# Sources
* MS SDL Design Phase: https://msdn.microsoft.com/en-us/library/windows/desktop/cc307414.aspx
* Appendix C - SDL Privacy Questionaire: https://msdn.microsoft.com/en-us/library/windows/desktop/cc307393.aspx
* http://doit.maryland.gov/SDLC/Documents/SDLC%20Phase%2005%20Design%20Phase%20Single%20Custom.pdf
* http://infolab.stanford.edu/~burback/watersluice/node11.html
