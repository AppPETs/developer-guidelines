# Introduction

The goal of the document is to motivate and support the development of privacy-respecting applications.

{% hint style="info" %}
Privacy can be a great **feature** for your users and a **competetive argument** in comparison to other apps. Moreover in order to **stay out of trouble with new EU data protection regulation** some things need to be taken into account during app development.
{% endhint %}

Most guides focus either on the **legal** aspects of protecting the data of end users or they focus on **technical** measurements to secure processed data. This document is intended to fill the gap between both worlds and should provide an overview into the different aspects that need to be respected when developing applications.

Depending on the use cases of your app, different things need to be considered about the protection of data. Not respecting certain aspects for certain scenarios might lead to legal consequences.

**This guideline outlines the relevant concepts to find out where protection of data comes into play and how!**

The goal of the document is to act as an **interface between technical solutions and legal aspects**, references to both are given to dive deeper into the subjects if you got curious. \[comment\]:"legal foundation, not only aspects, enable you to be compliant"

The legal aspects in this document are based on the _General Data Protection Regulation_ \(GDPR\), which becomes effective in May 25, 2018.

**Following this guideline will help you to meet the legal requirements of the new European Data Protection Regulation.**

## In very short at your fingertips...

In very very short we want to refer to the [Mozilla Data Privacy Principles](https://www.mozilla.org/en-US/privacy/principles/) [\(CC\)](https://creativecommons.org/licenses/by-sa/3.0/deed.en):

1. **No surprises**

   Use and share information in a way that is transparent and benefits the user.

2. **User control**

   Develop products and advocate for best practices that put users in control of their data and online experiences.

3. **Limited data**

   Collect what we need, de-identify where we can and delete when no longer necessary.

4. **Sensible settings**

   Design for a thoughtful balance of safety and user experience.

5. **Defense in depth**

   Maintain multi-layered security controls and practices, many of which are publicly verifiable.

We will go with you through the different steps of the development lifecyle to discuss the relevant issues for each development phase.

## Document Structure

The guideline is separated in a number of steps which are usually taken into account during application development. Some guidelines use a different wording, but the process should look familiar or should at least be easy to adopt.

![Application Development Lifecycle](https://raw.githubusercontent.com/AppPETs/developer-guidelines/master/figures/applifecycle.png)

From phase to phase you incrementally get more concrete. If questions arise, you need to go back one step.

* [PlanningPhase.md](applicationdevelopmentlifecycle/planningphase.md) - Functionality: First carefully plan your app: purpose, functions, use cases. 
* [AnalysisPhase.md](applicationdevelopmentlifecycle/analysisphase.md) - Requirements, Data Collection: Analyse which data you need.
* [DesignPhase.md](applicationdevelopmentlifecycle/designphase.md) - Adress the requirements, Data Processing: How is data processed und used.
* [ImplementationPhase.md](applicationdevelopmentlifecycle/implementationphase.md) - Code, Best Practices: Create the software code and documentation for the project, apply solutions for privacy protection.
* [TestingPhase.md](applicationdevelopmentlifecycle/testingphase.md) - The software is tested in various ways to ensure all features work as intended and to ensure quality.
* [MaintenancePhase.md](applicationdevelopmentlifecycle/maintenancephase.md) - Consider continuos processes after publication.

The basic idea is that it is a good practice to think carefully about the needs of your app and how to address and implement the needed functionality. Moreover in any phase it is useful to take into account potential risks in regard to protecting illegitimate access and abuse of personal data early and in each phase of development.

**Thinking early about potential risks and flaws makes it much more easy to address the risks with proper measures. This is the basic idea of privacy by design in a nutshell. Later on it becomes more difficult to change fundamental structures of your programme.**

[\(More information on the application development lifecycle\)](applicationdevelopmentlifecycle/)

If you want to learn more about basic concepts like privacy by default, you can have a look at the following sections. But you might want to get started and [jump into the development phases](applicationdevelopmentlifecycle/planningphase.md) and come back later if you need more information.

## Target Audience

This document is for software developers or other decision makers related to data processing. It aims to clarify the actions required to prevent legal consequences and in addition to support the privacy of their end users.

A background in security and privacy protection is not required. Background information is listed in the [Foundations](foundations.md) section. The legal aspects are addressed in a non-legalese form, as developers tend to not read them – you are not alone on this.

