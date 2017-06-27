# Mobile Application Security – Pre-Implementation Phase

The guideline chapter related to the Pre-Implementation Phase contains aspects relevant to data protection, data economy and data deletion, which have to be taken into consideration prior to the actual production phase.
* Informationen Düsseldorfer Kreis
* Informationen Bayerisches Landesamt für Datenschutz
* Gültigkeitsraum defnieren
* Deutsches Datenschutzrecht bewerben (Vorbildfunktion)

## Data protection and data economy

### Implementing a Privacy Policy and Terms Of Service (B2C)

If the app will process personally identifiable data (PII), a Privacy Policy (PP) MUST be implemented as according to §13 TMG.

The following points MUST be explained in the PP:

* Which data worthy of protection will be accessed and why?
* How will this data be used? (Processing, transmission to server, etc.)
* How will this data be stored? (Plain text, encrypted, hashed, etc.)
* Which third-parties will receive access to the data and under what conditions?
* A statement from the application owner confirming they will protect the data that is collected.
* Who is the Data Protection Officer, and how can he/she be reached?
* Will the user be given the opportunity to view all of the data on them that has been collected and stored and, if required, to have them removed completely, which also includes removal from the servers of the service provider?

Terms Of Service (TOS) and PP MUST be provided in a barrier-free manner and has to be available offline (§ BDSG/TMG).
What’s more, this statement SHOULD also be provided as a link to online versions in order to improve readability.
The user SHOULD be able to view the PP in the app store.

### Privacy Policy and Terms Of Service compliant app behavior (B2C)

The behavior of an app MUST correspond with the behavior stated in the PP/TOS.
If new functions are added that exceed the areas defined in the original TOS and PP, then the PP/TOS MUST be updated and adjusted.
Furthermore, the user MUST be informed about the change.
In doing so, you SHOULD not only refer to general changes to the PP/TOS, but also to the changed area that will be made directly available to the user.

### “Privacy by design” vs. “Failure by design” (B2C)

Apps MUST comply with the principle Privacy by Design.
This means that all data protection-relevant aspects that relate to the end user must be secure and capable of configuration.
In doing so, preconfiguration of all options for ensuring (data-) protective behavior is essential.

The infrastructure MUST be checked for design errors, which avoid systematic, non-removable behavior (called Failure by Design, corresponding to Privacy by Design).
E.g. "WhatsApp": with this app the users are authenticated using their telephone number.
This is actually personal data, which means it should not be transferred to any foreign server without the consent of the owner.
However, as the telephone numbers of persons in the address book (who even might not use WhatsApp) will be transmitted to a WhatsApp server.
This way, data-protection-compliant usage of the app is not possible.

### Device-specific information (B2C)

Access to device-specific information (e.g. UDID, IMEI, MAC addresses, etc.) MUST be obtained from the user via an Opt-In and MAY only take place to the extent that is really required.

Many app manufacturers claim that device IDs are “anonymized” using hash values.
As this is actually pseudonymization and not anonymization, the manufacturers are wrong here.
There is no reason why these IDs should be accessed to recognize users.

It is another matter, however, with regard to the “Tracking-IDs“ created specifically by the operating system manufacturers (IDFA (Identifier for Advertisers, iOS); AAID (Android Advertising ID, Android)).
These MUST be transmitted in encrypted form (see → 4.1.1 Encrypted communication and validation) and the Opt-In will also be obligatory in future.
The different development levels of the data protection standards for mobile operating systems mean a standard evaluation is not possible.

With iOS (from version 6.0) it is possible to change the IDFA or refuse utilization of it for the most parts.
The programmer is however responsible for respecting this refusal option.

The way the Android Advertising ID works in Android is similar to the way of the IDFA in iOS.
It is generated completed dynamically by the user with a Google app that has been available since Android 4.0.x and can be reset at any time.
It is mandatory to use for user identification as of August 1, 2014 when it comes to user tracking.
It does also have an option for limiting usage.

There are also unique IDs that can be used for authentication or user identification issues.
It is not possible to change the Android ID in Android, which is often used by apps for tracking purposes, without installing a Custom ROM or modifying the user’s rights using a Root software/tool.
The same applies to the UDID on iOS devices, that can only be faked on a device with a Jailbreak installed.
Use of these IDs is mostly prohibited by the operating systems manufacturer (especially for ad tracking purposes).

### Data access (B2C)

Access to data (e.g. PIM, media, etc.) MUST take place in line with data economy according to §3a BDSG.
Data MUST NOT be passed on to third parties without an Opt-In from the user.
Utilization of the data SHOULD be explained to the user (why does the application need this access, and what will not function if I do not provide this access?).

## Data deletion (B2C)

An app SHOULD implement a procedure for deleting data, which was been generated by the app or during utilization thereof.
This includes accounts, local data, and data stored on the servers of the app provider or on cloud servers.

If no deletion procedure is provided within the app, contact details MUST be provided to ensure the user is able to send a data deletion request to the service provider (see → 4.2.4 Cloud provider contact data).
