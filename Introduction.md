## Definition of common used terms

### **Privacy by Design & Default**

- All data protection-relevant aspects related to the end user must be planned to be secure
- All options for ensuring data protective behavior have to be preconfigured in a way a user can not accidentally lose personal information
- Data access takes place in line with data economy principles
- Data not immediately used may not be collected
- Passing data to third parties requires an **Opt-In** from the user
  - Opt-In means that the user needs to explicitly confirm the data transfer beyond the scope of the application

### Risk Assessment

after each Development Phase the risk needs to be reassessed

------

======== Alter Inhalt (ggf. übernehmen) ===========

# Introduction

The goal of the document is to support the development of privacy-respecting applications. Most guides focus either on the legal aspects of protecting the data of end users or they focus on technical measurements to secure processed data. This document is intended to fill the gap between both worlds and should provide an overview into the different aspects that need to be respected when developing applications.

Depending on the usage scenario, different protection goals are relevant. Not respecting certain aspects for certain scenarios might lead to legal consequences.

As the goal of the document is to act as an interface between technical solutions and legal aspects, references to both are given. The legal aspects in this document are based on the *General Data Protection Regulation* (GDPR), which becomes effective in May 25, 2018.

**TODO**: Explain that the referenced technical solutions are what is considered "state-of-the-art" – which is a fuzzy term in a legal context.

**TODO**: We could also reference developer guidelines from Google/Apple (see [App Store Review Guidelines](https://developer.apple.com/app-store/review/guidelines/)) and mention that non-compliance with certain aspects might not only lead to legal consequences but also to rejecting for a market place (at least that is the case for Apple's App Store). Reason behind this: Developers might not fear legal consequences but rejection, because legal consequences might not appear imminent to them, e.g., if they are not directly responsible and think their boss/lawyers will handle it.

**TODO**: We could make the document more interesting if we "promise" to discuss how some analytics or advertisement could be realized in a privacy-friendly manner. Developers might think that "privacy = less functionality" and refrain from reading the document based on that prejudice.

## Target Audience

This document is for software developers or other decision makers related to data processing. It aims to clarify the actions required to prevent legal consequences and in addition to support the privacy of their end users.

A background in security and privacy protection is not required. Background information is listed in the [Foundations](Foundations.md) section. The legal aspects are addressed in a non-legalese form, as developers tend to not read them – you are not alone on this.

**TODO**: How do we want to handle the separation of Business to Customer (B2C), Business to Employee (B2E), and Business to Business (B2B)? I suggest that the discussion of certain aspects should clarify the relevant context.

**TODO**: Is Mobile Device Management (MDM) relevant?

## Document Structure

The document is structured with respect to the target audience.

First relevant background information on security and privacy is provided. Especially the terminology used throughout this document is explained, as terms differ between the software security and legal communities. Then an overview of possible threats and data protection goals is given.

The main part is structured in familiar way for software developers, the different phases of the application development lifecycle. For each phase, relevant aspects are highlighted and technical solutions to address certain problems are referenced.