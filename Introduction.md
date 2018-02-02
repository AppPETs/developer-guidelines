# Introduction

The goal of the document is to motivate and support the development of privacy-respecting applications. 

*Privacy can be a great **feature** for your users and be a **competetive argument**. Moreover in order to **stay out of trouble with new EU data protection regulation** some things need to be taken into account during app development*

Most guides focus either on the legal aspects of protecting the data of end users or they focus on technical measurements to secure processed data. This document is intended to fill the gap between both worlds and should provide an overview into the different aspects that need to be respected when developing applications.

Depending on the use cases of your app, different things need to be considered about the protection of data. Not respecting certain aspects for certain scenarios might lead to legal consequences. 

**This guideline outlines the relevant concepts to find out where protection of data comes into play and how!**

The goal of the document is to act as an interface between technical solutions and legal aspects, references to both are given to dive deeper into the subjects if you got curious. 
[comment]:"legal foundation, not only aspects, enable you to be compliant"

The legal aspects in this document are based on the *General Data Protection Regulation* (GDPR), which becomes effective in May 25, 2018.

## In very short at your fingertips...

[comment]:"add here a one page summary of the content and motivate a structured development along the lines outlined in the rest of the document. give hints to papers and material referenced and attached to this document"

## Document Structure
The guideline is separated in a number of steps which are usually taken into account during application development. Some guidelines use a different wording, but the process should look familiar or should at least be easy to adopt.

![Application Development Lifecycle](figures/applifecycle.svg)

- [x] shortly explain the phases (one sentence)

* [PlanningPhase.md](./PlanningPhase.md) -  First carefully plan your app: purpose, functions, use cases. [comment]:"focus on functionality"

* [AnalysisPhase.md](./AnalysisPhase.md) - Analyse which data you need and how you need to process it. [comment]:"role of data analysis?"

* [DesignPhase.md](./DesignPhase.md) - The system is designed to satisfy the requirements identified in the previous phases. [comment]:"which"

* [ImplementationPhase.md](./ImplementationPhase.md) - Create the software code and documentation for the project.

* [TestingPhase.md](./TestingPhase.md) - The software is tested in various ways to ensure all features work as intended and to ensure quality.

* [MaintenancePhase.md](./MaintenancePhase.md) - Consider continuos processes after publication.

The basic idea is that it is a good practice to think carefully about the needs of your app and how to address and implement the needed functionality. Moreover it is necessary to take into account potential risks in regard to protecting illegitimate access and abuse of personal data early and in each phase of development. 

**Thinking early about potential risks and flaws makes it much more easy to address the risks with proper measures.**

[(More information on the application development lifecycle)](./ApplicationDevelopmentLifecycle.md)

If you want to learn more about basic concepts like privacy by default, you can have a look at the following sections. But you might want to get started and [jump into the development phases](./PlanningPhase.md) and come back later if you need more information.

## Target Audience

This document is for software developers or other decision makers related to data processing. It aims to clarify the actions required to prevent legal consequences and in addition to support the privacy of their end users.

A background in security and privacy protection is not required. Background information is listed in the [Foundations](Foundations.md) section. The legal aspects are addressed in a non-legalese form, as developers tend to not read them – you are not alone on this.

## Definition of Common Used Terms

### **Privacy by Design & Default**

- All data protection-relevant aspects related to the end user must be planned to be secure
- All options for ensuring data protective behavior have to be preconfigured in a way a user can not accidentally lose personal information
- Data access takes place in line with data economy principles
- Data not immediately used may not be collected
- Passing data to third parties requires an **Opt-In** from the user
  - Opt-In means that the user needs to explicitly confirm the data transfer beyond the scope of the application

### Risk Assessment

- after each Development Phase the risk needs to be reassessed

***
END OF DOCUMENT
***

DISCUSSION SPACE

TODO:

- [ ] add descriptions and definitions of basic concepts used during the DevGL / or in [Foundations](Foundations.md)

- [ ] Explain that the referenced technical solutions are what is considered "state-of-the-art" – which is a fuzzy term in a legal context.

- [ ] We could also reference developer guidelines from Google/Apple (see [App Store Review Guidelines](https://developer.apple.com/app-store/review/guidelines/)) and mention that non-compliance with certain aspects might not only lead to legal consequences but also to rejecting for a market place (at least that is the case for Apple's App Store). Reason behind this: Developers might not fear legal consequences but rejection, because legal consequences might not appear imminent to them, e.g., if they are not directly responsible and think their boss/lawyers will handle it.

- [ ] We could make the document more interesting if we "promise" to discuss how some analytics or advertisement could be realized in a privacy-friendly manner. Developers might think that "privacy = less functionality" and refrain from reading the document based on that prejudice.

- [ ] How do we want to handle the separation of Business to Customer (B2C), Business to Employee (B2E), and Business to Business (B2B)? I suggest that the discussion of certain aspects should clarify the relevant context.

- [ ] Is Mobile Device Management (MDM) relevant?


