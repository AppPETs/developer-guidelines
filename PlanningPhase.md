# Planning Phase

Before you start to code, carefully plan your app: what purpose is it for? Which functions will be needed, what are the use cases?

## Defining the Purpose and Functionality of the App

### The App's Purpose

What will the app do for the end-user? It might seem obvious, but **it is a good start to take a moment and reconsider what the actual aim of the app is**.

- Which functions should the app provide and
- which user data is necessary for the planned functionality.

Especially it is important to carefully think which user data is needed and how it will be processed.



| "Legal Hint" - Purpose Binding  |
|---|
|   Personenbezogene Daten dürfen aufgrund Art. 5 Abs. 1 b der Datenschutz-Grundverordnung (DSGVO) nur für festgelegte, eindeutige und rechtmäßige Zwecke verarbeitet werden. Wenn dies erfüllt ist, ist weiter zu beachten: die Daten dürfen nach Art. 5 Abs. 1 c DSGVO nur so weit verarbeitet werden, wie es angemessen und erheblich ist für den Zweck. Es dürfen also nicht mehr Daten verwendet werden als nötig, nicht länger als nötig und die Verarbeitung darf nicht weiter gehen als nötig. |
|**Determining the purpose is important for deciding upon the functionality that may be included in the app, and if and how user data needs to be processed.**|


<br>

| "Example" - Purpose Binding |
|---|
| For example a weather app might let you choose and display weather information; a firewall app might let you inhibit or monitor a smartphone's connections to the internet. <br> For this functions certain user data might be necessary or useful like geo-data or access to data connections. This data has implications which need to be taken into account at an early stage of development for proper integration of security measures.* |

### Intended and Unintended Ways to Use the App

- [ ] is the unintended use a main issue here?

When planning the application design, consider not which purpose you design the app for but also take into account that users might find alternative ways to use the app which can have an impact on other users of the device.

*For example a firewall app can give you information about other apps' illegitimate connections to the internet. Yet it might also give end users a tool to secretly record and monitor other users' internet activities.*

**Be creative about potentially harmful ways to use of your app. Think about safeguards against illegitimate uses.**

*For example in the case of a firewall app a notification about the monitoring activity in the background would give the user transparency.*

## Defining the App's Functionality and Permissions

A privacy-friendly app will only include functionality and permissions that is needed to serve the purpose determined in the beginning.

**Think carefully about which permissions are essential for providing the functionality.**

*An app providing location based services does not need to access the device's microphone to do so.*

Ideally any permissions that are not strictly necessary to serve the intended purpose should be avoided. Any need for permissions must be explained and justified in a comprehensible way. Take into account that users have no deeper understanding of the dependencies and technical necessities. Only if they really understand why and how the permission is used they can actually give a real consent.

 – [ ] should there be a headline with "Analysis of required data"? (or in Analysis Phase?) 

## Defining the sort of data to be used

There are different categories of data which are relevant for the use of the app.

 - **Primary Data**: Data related to the end-user or to other data subjects concerned. Apart from personal data, consider content data needed.
 - [ ] is content data different from user generated data?

 - **Secondary Data**: Data will be produced while the app is running. This might be user content (e.g. messages), log data, data related to payment, statistics to authorizing access or other. These will also contain personal data that require protection and thus need to be specified and assessed.

 - [ ] what's the use of the differentiation of primary/secondary data here?

---
END OF DOCUMENT

---

###Things to add:
 - [ ] Check Laws and Regulations applicable to your specific sector of industry

 - [ ] Rights and obligations to erase the data collected

###Pastebin

####former sections:

 - [ ] Data Subjects

 - [ ] Processes

 - [ ] Responsibilities

 - [ ] Communication of Purpose / Data Processing Requirement and Protection Measurements



