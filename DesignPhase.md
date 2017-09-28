# Design Phase

During the design phase, the system is designed to satisfy the requirements identified in the previous phases.
The identified requirements need to be transformed into a System Design Document that describes the design of the system which will be used for the implementation of the system.

## Objectives/Goals

The successfull completion of the design phase should include:

* Transformation of **all** requirements into detailed specifications covering **all** aspects of the system
* Assessment and planning of security risks
* Assessment and planning of privacy risks
(DG: noch andere Risiken?)

## Deliverables

* Architecture document
* Test plan
* Security risk assessment and mitigations
  * If no mitigations given, explanation why security risks are accepted
  * Users of the system need to be informed
* Privacy risk assessment and mitigations
  * If no mitigations given, explanation why privacy risks are accepted
  * Users of the system need to be informed 

# Design activities

## System Architecture
The system's architecture gives an overview of all physical and logical components of the system and how they interact with each other.

## Perform Risk Management
Threats and vulnerabilities that exist in the project’s environment or that result from interaction with other systems need to be identified during this phase.
You cannot consider the design phase complete unless you have a threat model or models that include such considerations. Threat models are critical components of the design phase and reference a project’s functional and design specifications to describe vulnerabilities and mitigations.

Code that was created by external development groups in either source or object form. It is very important to evaluate carefully any code from sources external to your team. Failure to do so might cause security vulnerabilities about which the project team is unaware.

Threat models that include all legacy code if the project is a new release of an existing program. Such code could have been written before much was known about software security, and therefore could contain vulnerabilities.

### Security Risk Management
Complete the threat models for all functionality identified during the analysis phase. Threat models typically must consider the following areas:

* All code exposed on the attack surface and all code written by or licensed from a third party.
* All features and functionality.
* New features or functionality added in the updated version.

### Privacy Risk Management

* Which personal data is collected?
* What is the compelling customer value proposition and business justification?
* Which notice and consent experiences are provided?
* What controls are provided to users and enterprises?
* How is unauthorized access to personal information prevented?

* Data storage remote vs. local on the device
  * If remote: what are possible potential privacy leaks

## Problems
*(technische Umsetzung der Datentransfers)*
*(welche Umsetzungsmöglichkeiten habe ich, und welche varianten sind hier datenschutzfreundlicher.)*
*(zB Vermeidung eines jeden Datenabflusses, hier gute Beispiele einbringen: Wetterapp, genau oder ungenau, nächste Wetterstation, Rasterung, etc)*
*(-> Designentscheidungen sollen hier wohl überlegt sein.)*
*(Bewertung lieber nicht, weil alle Daten sensibel sind??)*
*(-> nur wenn nötig nur für den bestimmten zweck und nur möglichst sicher verarbeitet....)*
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
