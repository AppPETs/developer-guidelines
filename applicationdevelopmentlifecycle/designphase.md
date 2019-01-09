# Design Phase

## Design Phase

During the design phase, the system is designed to satisfy the requirements identified in the previous phases. The identified requirements need to be transformed into a System Design Document that describes the design of the system which will be used for the implementation of the system.

{% hint style="info" %}
In any step of your Design think of how you can do it in a data protection friendly way.
{% endhint %}

### Objectives/Goals

The successfull completion of the design phase should include:

* Transformation of **all** requirements into detailed specifications covering **all** aspects of the system
* Assessment and mitigation of data security risks
* Assessment and mitigation of privacy risks \(infringements of informational self-determination\)
* [ ] REM: more risks to add?

### **Deliverables**

List of deliverables, more detailed information you will find in the sections below:

* Architecture document
* Planning of test cases and testing schedules
* Data security risk assessment and mitigations
  * Where no mitigations are given, justification for the acceptance of security risks is necessary
* Privacy risk assessment and mitigations justification for the acceptance ofprivacy risks is necessary
* Users of the system need to be informed about known risks and shortcomings of risk mitigations

## Design activities

### System Architecture Document

The system's architecture should give an overview of all physical and logical components of the system and how they interact with each other,

* [x] [R](https://github.com/AppPETs/developer-guidelines/tree/5d6d22d22b2f697aeba374552a121460ae793d2a/%22*/README.md)EM: missing: planning test  and schedules
* [ ] Including the data flows?

A proper documentation about the logical interdependencies and the data flows of the application helps you to identify the problematic spots. Spots you have to take into account for measuring pitfalls and risks regarding data protection issues. It also shows where you need special tools to protect users and their privacy -- also to comply with legal obligations \(see section Data Protection Impact Assessment below\).

### Plan test cases and testing schedules 

We conceive it as essential to use test-driven development \(see also section testing phase\). Experience shows that no one can develop without bugs, and you cannot fully test the functionality of your app manually. However, often changes in one part of the software affect other parts, which usually is overlooked during development. For that the best thing is to write test cases which use the functionality of the app. Think about a schedule for regular testing, in order to find problems early and avoid big trouble. Write down your plan in order to fully elaborate your cases and schedule. 

* [ ] REM: find link for reference, in the wiki

### Perform Risk Management

Threats and vulnerabilities that exist in the project’s environment or that result from interaction with other systems need to be identified during this phase. 

**You cannot consider the design phase complete unless you have a threat model or models that include such considerations.** 

Threat models are critical components of the design phase and reference a project’s functional and design specifications to describe vulnerabilities and mitigations.

In order to assess the risk you need to take into account possible **attacks and threads**.

* Assess the probability of its occurrence 
* Assess the level of harm each thread induces
* Develop tools and measures that address the risks assessed.
* Evaluate if and how the risks are reduced through the measures implemented.

#### Code that was created by external development groups in either source or object form.

It is very important to evaluate carefully any code from sources external to your team. Failure to do so might cause security vulnerabilities about which the project team is unaware.

#### Threat models that include all legacy code if the project is a new release of an existing program.

Such code could have been written before much was known about software security, and therefore could contain vulnerabilities. 

* [ ] _REM: wording/explain_

#### Security Risk Management

The threat models for all functionality identified during the analysis phase need to be completed. Threat models typically must consider the following areas:

* All code exposed on the attack surface and all code written by or licensed from a third party.
* All features and functionality.
* New features or functionality added in the updated version.

#### Privacy Risk Management

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

In certain cases, like the processing of sensitive data or bulk processing of personal data you are obliged by the GDPR to conduct a Data Protection Impact Assessment. The UK's [Information Commissioner Office](https://ico.org.uk/for-organisations/guide-to-the-general-data-protection-regulation-gdpr/accountability-and-governance/data-protection-impact-assessments/) outlined the basic aspects to take into account and offers a checklist for Data Protection Impact Assessments. The French [Commission Nationale de l'Informatique et des Libertés \(CNIL\)](https://www.cnil.fr) developed an [Open Source tool for conducting Privacy Impact Assessments](https://www.cnil.fr/en/open-source-pia-software-helps-carry-out-data-protection-impact-assesment).

### Common problems in the context of application development

There are common problems you should be aware of when designing your application.

* Data receiving
  * How is data collected or received?
  * Are the connections secure?
  * Is metadata generated which might reveal personal information?
  * \[\[REM\]\]\("add?: is executable code received?"\)
* Data sending
  * How is data transmitted to other apps and servers?
  * Are connections secure?
  * Is it necessary to send the data?
  * Can the transmission be manipulated?
* Data processing
  * How is the data used and processed?
  * Are decisions made which might affect the fundamental rights of users and others?
  * Do you build behavioural models which might affect the freedom of action of individuals? \[\[REM\]\]\("elaborate or examples needed here"\)

Especially if data is exchanged with 3rd parties you should evaluate the transmission channels and the kind of information which is exchanged.

* Is the 3rd party trustworthy? 
* Is the connection secure?
* Is the transmission necessary or are there other ways to fulfill the goal?

| Example | Questions to take into account if you think of a SatNav app. |
| :--- | :--- |
| Data receiving | Which data is collected from the device? Which data is received: the download of certain parts of the map for instance reveals the location of the user. |
| Data sending | Where is the location information send to? Which other information is sent? Which information is deferrable, e.g. speed and direction. How exact needs the location data be for the Map server? Which data can stay on the device in order to reduce information security risks? |
| Data processing | The model built from the aggregated behaviour of users informs which users routed in which ways. Are you building profiles? Are the areas where users are not routed? What criteria flow in the computation of the route? Do you really now which information will be stored by 3rd parties and how they will use it? |

You need to keep in mind that you comply with the data protection principles of data minimisation and purpose binding.

* [ ] REM: explain in more detail here? e.g. legal ground for data collection and processing.

### Technical Measures

* [ ] REM: TODO: Link technical measures to problems arised in the section above

Which technical measures can be applied to address the identified risks. Possible counter measures include:

<table>
  <thead>
    <tr>
      <th style="text-align:left">Technical Measure</th>
      <th style="text-align:left">Use case</th>
      <th style="text-align:left">Caution</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">Cryptography</td>
      <td style="text-align:left">For safer transmission and storage of data. With strong encryption you
        can minimize the risk of leaking data during transmission. Also you can
        store data encrypted in order to make it more difficult for attackers in
        case of a lost device.</td>
      <td style="text-align:left">Use strong methods and take care of the keys, to keep it effective.</td>
    </tr>
    <tr>
      <td style="text-align:left">Anonymisation</td>
      <td style="text-align:left">If you can effectively remove the data's reference to individual person,
        it is not suspect the General Data Protection Regulation. Take into account
        that anonymized data can be deanonymized where data sets still contain
        unique information. Most probably if you join different data sets it becomes
        more likely to reidentify certain individuals, especially the ones which
        deviate from the majority.</td>
      <td style="text-align:left">Make sure that anonymized data cannot easily be reidentified.</td>
    </tr>
    <tr>
      <td style="text-align:left">Pseudonymisation</td>
      <td style="text-align:left">
        <p>If you replace the unique ID through a chiffre instead of deleting the
          unique ID, it is pseudonymized. Keep in mind that this kind of data can
          quite easily be reidentified.</p>
        <ul>
          <li>REM: add legal notice</li>
        </ul>
      </td>
      <td style="text-align:left">Take into account that pseudonymized data can quite easy be reidentified
        with some additional information.</td>
    </tr>
  </tbody>
</table>See next section for examples from our Privacy Library.

### Organisational Measures

Organisational measures include:

* Transparency
  * Communication of risks and purpose of data collection to the end user
* Intervenability
  * Means for the end user to delete and modify data
  * which extend functionality is necessary
  * contact person
* Availability
  * SDM \(Standard Datenschutz Modell\)
* Data minimisation



* [ ]  [REM](https://github.com/AppPETs/developer-guidelines/tree/5d6d22d22b2f697aeba374552a121460ae793d2a/%22*/README.md): reflexivity, communication, testification
* [ ] TODO: Add links and examples

## TODO:

* licence of SDL documents

## Sources / References

* MS SDL Design Phase: [https://msdn.microsoft.com/en-us/library/windows/desktop/cc307414.aspx](https://msdn.microsoft.com/en-us/library/windows/desktop/cc307414.aspx)
* Appendix C - SDL Privacy Questionaire: [https://msdn.microsoft.com/en-us/library/windows/desktop/cc307393.aspx](https://msdn.microsoft.com/en-us/library/windows/desktop/cc307393.aspx)
* [http://doit.maryland.gov/SDLC/Documents/SDLC Phase 05 Design Phase Single Custom.pdf](http://doit.maryland.gov/SDLC/Documents/SDLC%20Phase%2005%20Design%20Phase%20Single%20Custom.pdf)
* [http://infolab.stanford.edu/~burback/watersluice/node11.html](http://infolab.stanford.edu/~burback/watersluice/node11.html)

