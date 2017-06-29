# Introduction

This document serves as a guideline for app developers and assists with orientation during app development, in order to ensure comprehensive data security standards.
The document has been designed in such a way that both inexperienced and experienced developers as well as decision-makers and non-technicians will be able to use it as a basis for planning and development activities as well as the creation of tenders for other projects related to application production.

The bibliography (see → 7.1 Bibliography) contains additional information about further aspects of mobile security as well as links to the operating system manufacturer’s web presences.

The glossary (see → 7.2 Glossary) contains explanations of the technical/specialist terms as well as a link list for obtaining further information.
Glossary terms are highlighted in the running text as written in italics and marked with an indicator number.

There is also a checklist available, serving as an easy tool of controlling during the different phases of the application production process.
Please refer to the “$kunde_Secure_Apps_Checklist” documents.

Certain chapters of this document are related to specific aspects of data protection and data security in a matter they may apply only if the app is designed for  certain target audiences, e.g. Business to Customer (B2C), Business to Employee (B2E) and Business to Business (B2B).
If such a restriction applies to a chapter, it will be highlighted as such at the chapter’s headline.
If there is no such indication, the chapter is relevant for all kinds of applications.

## Target Audiences and Application Classification

This document serves as a guideline for app developers and assists with orientation during app development, in order to ensure comprehensive data security standards.
The document has been designed in such a way that both inexperienced and experienced developers as well as decision-makers and non-technicians will be able to use it as a basis for planning and development activities as well as the creation of tenders for other projects related to application production.

The bibliography (see → 7.1 Bibliography) contains additional information about further aspects of mobile security as well as links to the operating system manufacturer’s web presences.

The glossary (see → 7.2 Glossary) contains explanations of the technical/specialist terms as well as a link list for obtaining further information.
Glossary terms are highlighted in the running text as written in italics and marked with an indicator number.

There is also a checklist available, serving as an easy tool of controlling during the different phases of the application production process.
Please refer to the “$kunde_Secure_Apps_Checklist” documents.

Certain chapters of this document are related to specific aspects of data protection and data security in a matter they may apply only if the app is designed for  certain target audiences, e.g. Business to Customer (B2C), Business to Employee (B2E) and Business to Business (B2B).
If such a restriction applies to a chapter, it will be highlighted as such at the chapter’s headline.
If there is no such indication, the chapter is relevant for all kinds of applications.

## Terms and Methodology

In this document, the terms MUST, SHOULD, CAN and MAY are utilized within the sense of RFC 2119.
Use of these terms applies only to specific instructions that have to be followed during application development.

Users of this guideline are provided with information, which issues of data protection and data security have to be taken into consideration to produce a secure application.
Furthermore they are provided with information as to which behavior or properties of an app might have an influence on categorizing it into the Blacklists1 or Whitelists2 of devices administrated via a Mobile Device Management3 system (MDM).
This applies especially to applications, where an app store release is planned.

A behavioral pattern (e.g. data transmission behavior) or feature (e.g. use of cloud storage) of the application MUST fulfill a certain condition in order to obtain entry in the Whitelist.
There is no margin of discretion here.
If this condition is violated, this might result in an entry in the Blacklist depending on the assessment criteria and protection policies implemented by the MDM administrator.

A behavioral pattern or property SHOULD fulfill a certain condition in order to obtain entry in the Whitelist.
Fulfillment of this condition is generally required, but there will be margin for discretion in certain cases.
If the condition is violated, this might result in entry in the Blacklist, but not always.

A behavioral pattern or property CAN fulfill a certain condition.
In order to obtain entry in the Whitelist, fulfillment of the condition would be beneficial, but there is plenty of room for discretion.
Retrospective downgrading is however possible, if the assessment criteria are intensified.
