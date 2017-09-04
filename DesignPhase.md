# Design Phase

During the design phase, the system is designed to satisfy the requirements identified in the previous phases.
The identified requirements need to be transformed into a System Design Document that describes the design of the system which will be used for the implementation of the system.

## Objectives/Goals

The successfull completion of the design phase should include:

* Transformation of **all** requirements into detailed specifications covering **all** aspects of the system
* Assessment and planning for security risks
* Assessment and planning for privacy risks
* ...

## Deliverables

* Architecture document
* Implementation plan
* Critical priority analysis
* Performance analysis
* Test plan
* Security risk assessment and mitigations
  * If no mitigations given, explanation why security risks are accepted
  * Users of the system need to be informed
* Privacy risk assessment and mitigations
  * If no mitigations given, explanation why privacy risks are accepted
  * Users of the system need to be informed 

# Design activities

## System Architecture

## Perform Risk Management

Threats and vulnerabilities that exist in the project’s environment or that result from interaction with other systems.
You cannot consider the design phase complete unless you have a threat model or models that include such considerations. Threat models are critical components of the design phase and reference a project’s functional and design specifications to describe vulnerabilities and mitigations.

Code that was created by external development groups in either source or object form. It is very important to evaluate carefully any code from sources external to your team. Failure to do so might cause security vulnerabilities about which the project team is unaware.

Threat models that include all legacy code if the project is a new release of an existing program. Such code could have been written before much was known about software security, and therefore could contain vulnerabilities.

### Security Risk Management

Complete threat models for all functionality identified during the cost analysis phase. Threat models typically must consider the following areas:

* All code exposed on the attack surface and all code written by or licensed from a third party.
* All features and functionality.
* New features or functionality added in the updated version.

### Privacy Risk Management

* What personal data is collected?
* What is the compelling customer value proposition and business justification?
* What notice and consent experiences are provided?
* What controls are provided to users and enterprises?
* How is unauthorized access to personal information prevented?

## Cryptography

From MS SDL:

* Use AES for symmetric enc/dec.
* Use 128-bit or better symmetric keys.
* Use RSA for asymmetric enc/dec and signatures.
* Use 2048-bit or better RSA keys.
* Use SHA-256 or better for hashing and message-authentication codes.
* Support certificate revocation.
* Limit lifetimes for symmetric keys and asymmetric keys without associated certificates
* Support cryptographically secure versions of SSL (must not support SSL v2).
* Use cryptographic certificates reasonably and choose reasonable certificate validity periods.
* (New for SDL 5.2) Use Transport Layer encryption securely. Properly use Transport Layer Security (TLS) when communicating with another entity, and verify that your service checks the Common Name attribute to be sure it matches the host with which you intended to communicate. Verify that your service consults a certificate revocation list (CRL) for an updated list of revoked certificates at a frequent interval. If your service is accessible via a browser, confirm that no security warnings appear at any visited URL for any supported browser.

## Organisational Measures

No technical solutions. 

Organisational measures, such as:

* Transparency
  * Communication of risks and purpose of data collection to the end user
* Intervenability
  * Means for the end user to delete and modify data

# Sources
* MS SDL Design Phase: https://msdn.microsoft.com/en-us/library/windows/desktop/cc307414.aspx
* APpendix C - SDL Privacy Questionaire: https://msdn.microsoft.com/en-us/library/windows/desktop/cc307393.aspx
* http://doit.maryland.gov/SDLC/Documents/SDLC%20Phase%2005%20Design%20Phase%20Single%20Custom.pdf
* http://infolab.stanford.edu/~burback/watersluice/node11.html

# Old Notes

- Which data can be locally processed / stored? (no privacy leak for the user)

- Which data must be processed / stored remotely? (possible data leak)

  - how can the following steps possibly help:

    - encryption

    - anonymisation

    - pseudonymisation

    - organisational steps

      - -> data minimisation steps (SDM)

      ​

  ### Dataflow and other components (backend and frontend)(Datenflüsse und andere Komponenten)

- Data recieving problematically? (Datenabruf problematisch? (Metadata & PKR))

- Data sending problematically? (Datenversand problematisch?)

- Data processing problematically? (Datenverarbeitung problematisch?)

- Interaction with 3rd parties? (Interaktion mit dritten? (z.B. beim Bezalvorgang)) 

  - No? (z.B. bei Bezahlvorgang (Barzahlung = unproblematisch))
  - Yes? (z.B. beim Bezahlvorgang (paypal / Kreditinstitut etc.))
    - back to point -> "how can the following steps possibly help?"

## Interveneabality enforcement (Intervenierbarkeit sicherstellen)

- which extend functionality is necessary? (Welche zusätzliche Funktionalität wird benötigt?)
  - Contact person (Ansprechpartner)
- availability (Verfügbarkeit (sowohl SDM als auch technisch))
