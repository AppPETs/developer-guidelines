# Mobile Application Security – Implementation Phase

## Protection of data transmissions

This sub-chapter is targeted towards all wireless communication, regardless of the communication medium the application is planned to use (e.g. WLAN, APN etc.).

### Encrypted communication and validation

Data worthy of protection MUST be protected against unauthorized access or manipulation during transmission with a procedure that utilizes state-of-the-art technology, such as AES 256bit and RSA >2048bit.
Algorithms like RC4 or CBC are not sufficient.

The identity of the communication partner MUST be verified (possible via Certificate Pinning).
This allows problems caused by operating system errors (e.g. "goto fail" under iOS) to be avoided.
However, it has to be made sure that the certificates are always up-to-date.
A new certificate on the communicating server will require a new version of the app with an updated certificate table.

If the identity of the communication counterpart (e.g. a server or another client) is not properly verified or data is transferred via an unsafe connection, transferred data from the server MUST be validated by the app to ensure no tampered/modified files are transferred on the user's device.

### Standardized and current protocols – "State of the Art"

Apps SHOULD use standardized protocols for communication (e.g. JSON, XML, XMPP, etc.).
In doing so care should be taken to ensure the libraries that are used are deemed secure in accordance with the latest technologies available.

## Protection of stored data

### Local data storage

An app MUST select a storage location and storage type that correspond with the level of protection required for the data to be saved.
With regard to data that is particularly worthy of protection, the "secure" memory provided by the operating system should be used.
Furthermore, an encryption method for protecting such data MUST be implemented.
When using encryption, care MUST be taken to ensure sufficient initialization vectors and secure operating modes are used.
The hash procedure SHOULD take the usage of salt into consideration when generating keys.

Sensitive data and passwords generally MUST NOT be hardcoded into the application binary.
The same applies to proprietary and sensitive business logic.

Under iOS, the iOS Keychain MUST be used for storing sensitive data such as passwords, keys and certificates.
An appropriate protection class MUST be selected for saved data.

When saving personal or sensitive data on an iOS device, the protection class (NSFileProtection) that offers the best possible protection for the data MUST be used.

Under Android, sensitive data such as passwords, keys and certificates SHOULD be stored in the Keychain class (android.security.KeyChain).
If this is not possible for technical reasons, then the data MUST be encrypted.

Sensitive data MUST NOT be stored in external memory on an Android device.
When saving potentially sensitive data on an SD card, a standard encryption method MUST be selected since there is no right management for FAT32 formatted SD cards.

### Consent for usage of cloud storage (B2C)

Before using cloud services, the consent of the user MUST be obtained.
The user MUST also be informed about the company processing the data and the geological locations (e.g. countries) the file servers are located.
Furthermore, the user MUST be informed about the type of data that will be transferred.
This also applies even if the app is forced to use a specific cloud service.

With regard to applications whose primary function is not the establishment of a connection to the cloud, the utilization of cloud services MAY NOT be obligatory.
When integrating cloud services, a contract on Commissioned Data Processing MUST be concluded with the cloud service provider according to §11 BDSG.

### Cloud data storage

When using external services, the transmission and storage MUST fulfill the protection requirements of the data in question.
This means it MUST be stored using a procedure that complies with modern encryption standards.

For automatic data backups the backup mechanism SHOULD be within the enterprise domain, where the transmission of data occurs via a safe and tested channel.

With regard to iOS, personal or sensitive data with corresponding file system attributes SHOULD be excluded from the automatic saving in the iCloud, and the user MUST be informed of this situation when no appropriate encryption is available.
The exclusion takes place using the "IsExcludedFromBackupKey" function.

### Cloud provider contact data (B2C)

The user MUST be able to access all provider data that is relevant with regard to data protection.
It MUST be possible to establish contact with the cloud service provider directly and to request that all data is deleted from the cloud (see [Data deletion](PreImplementationPhase.md#data-deletion-b2c)).

### Security by obscurity

- Einsortierung überarbeiten
- Android: Reflections
- iOS-Equivalent suchen

## Server-powered services

Local server services MAY only be addressed from an external application with an explicit request and MUST be protected against unauthorized access using appropriate measures (see [Encrypted communication and validation](#encrypted-communication-and-validation)).
Server services MUST be blocked with regard to standard passwords, remote maintenance, remote administration and test access, and they may not automatically offer local file downloads without authentication.

## Secure code implementation

The compiler used to translate the source code MUST be configured in such a way that the best possible review of the source code is carried out (e.g. compiler warnings may not be automatically ignored).
For additional information, see [Automated and Manual Code Review](ImplementationPlanning.md#automated-and-manual-code-review).

Compiler warnings MUST be treated as errors and removed from the source code before the application is released.
Activation of the corresponding compiler flags varies depending on the compiler used.

During iOS application code compiling using LLVM, the compiler switches "-wall" and "-werror" are affected.
Furthermore, before the iOS application is released, the source code MUST be analyzed using the Clang Static Analyzer, and any error messages found during the source code analysis must be addressed accordingly.

During Android application code compiling using the Eclipse Java Compiler (EJC), the compiler switch "-err:all" is affected.

During Windows Phone application code compiling using Microsoft Visual Studio 2013, the compiler switch "/WX" is affected.

## Implementing Third-Party modules

### Advertising modules "Ad Tracking" (B2C)

If modules are used for customized advertising and ad tracking, the user MUST be notified of this.
Personally identifiable data MUST NOT be transmitted to advertising companies.
Ad tracking SHOULD be an Opt-In and MUST at least have an Opt-Out (this could also be realized through the purchase of an "ad free"-Add-on).

With regard to identification of the user, only the advertising ID designated by the system MAY be used for this purpose (see [Device-specific information](PreImplementationPhase.md#device-specific-information-b2c)).
Unique IDs MUST NOT be used for ad tracking.

### User Statistics & Analytics "Performance Tracking"

In principal, the same rules as for ad tracking apply here.
Tracking here has a different focal point, which means it is not the "monitoring" of the user that is being focused on here, but the way in which they use the app.
This means there is no need to transmit any personal data.

### Development-supporting modules and "SDKs"

There are other areas with additional modules or even entire development environments, which deal with source code maintenance or the creation of the source code.
In these areas it MUST be made clear in advance that no modules may be integrated into the application that do not comply with these guidelines.

In such a case a source code review of the created code SHOULD be carried out, which pays particular attention to unwanted or hidden functions (e.g. tracking, the transmission of device-specific or personal information, backdoors, known weaknesses of the used SDKs or similar).
As of July 2014, SDKs containing known weaknesses are for example the Facebook connect SDK, SDKs offering potentially unsafe OpenSSL implementation, etc.

## Update functionality (B2C)

An application MAY only install those updates independently, which do not change the application's basic functionality from a data protection perspective.
Applications MAY NOT update their basic functional behavior without informing the user.
Updates SHOULD be confirmed by the user.
Changes MUST be communicated to the user in an understandable and barrier-free manner (see [Implementing a Privacy Policy and Terms Of Service](PreImplementationPhase.md#implementing-a-privacy-policy-and-terms-of-service-b2c)).
This SHOULD definitely be practiced in relation to Anti-Features.

## Remote Wipe / Kill Switch

In the case of loss or theft, applications on managed devices SHOULD leverage remote wipe and kill switch API's available from the OS to remove sensitive data.
This applies mainly to applications storing sensitive and company-relevant data.

## User Interaction

### App configuration "secure by default"

The app should be preconfigured to be secure by default (from a data-protection perspective).
Historical data and sensitive information are not stored on the device beyond the required period for the application to perform its task or operation (e.g. GPS location information, etc.)

### Error Messages

Error messages must not reveal the internal structure of the app to the user.

- Error reports sent by the user do not include personal data.
- Error reports are transmitted over a secured connection.

### Screen Lock

Deactivating the screen lock functionality must be confirmed by the user.
There must also be an option to disable the screen lock deactivation.

### Password security & password policies

Passwords must enable a minimum level of security.

-   The user is informed about a too weak password.
-   Passwords are not transmitted in plain text.
-   Passwords should have a minimum length of 12 characters.
-   Password input fields should not resemble the real length of a password when showing placeholder characters (like *)
-   Passwords may not be part of a backup or cached in plain text.

    The same applies to authorization, authentication and session tokens.

-   Password complexity should not be limited
