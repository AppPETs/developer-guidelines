# Best Practices

## User Interaction

### App configuration "secure by default"

When creating an application, you should not only take inexperienced users into consideration, but also provide configuration options for more adept users.
Even if an application loses some functionality by blocking access, to contact data for example, these features should still be made available to the user.
When using such a function for the first time, approval of the user SHOULD be obtained, something that also contributes towards sensitization.
In this dialog it SHOULD be possible to deactivate the "query behavior", in order to ensure inexperienced users are not "annoyed".
This allows preconfiguration of all options with regard to (data-) protective behavior, without having to lose out on functionality.

Historical data or other sensitive information SHOULD NOT be stored on the device beyond the required period for the application to perform its task or operation (i.e. GPS location information, application specific information, etc.).

### Error messages

Error messages SHOULD help users to submit an error report or avoid the problem in future.
Error messages MUST not allow the internal program structure to be inferred, which would make it easy to compromise the program structure or the data stored therein.

### Screen lock

If a screen lock can be deactivated by the application, it MUST provide an option for deactivating this function and also inform the user of this function.

### Password security & password policies

$Insert Company Password Policy Passwords MUST enable a minimum level of security.
Users SHOULD be notified if their passwords are too simple or too short.
What's more, insufficient passwords MAY NOT be allowed to "leave" the device.
The level of security provided by a password MAY NOT be artificially limited through the implementation of short minimum lengths or the exclusion of special characters.
A password SHOULD have a minimum length of 12 and a maximum length of 30 characters.

The length of a password entered in an input field SHOULD NOT resemble its real length to prevent an easy access to the app in case of theft.

Sensitive data such as passwords or keys MAY NOT be part of a backup, stored or cached unless they are encrypted or hashed.
If possible opt to store them in tamper-proof storage areas provided by the device.
This applies also to tokens used for authorization or authentication.

- ERWEITERN (ifAsec, Kalinna)
- Zwang, sichere Passwörter zu verwenden, in App implementieren

## Operation system specific security options

### iOS

Using the copy & paste function provided by iOS sensitive data might be copied to clipboard.
To prevent other applications using the copied information the clipboard memory SHOULD be cleared on every occasion the app is switched to the background.

If sensitive information is entered into input fields, the input is saved to the keyboard cache.
Input fields used for passwords should be declared as such.
For other input fields used for potentially sensitive information keyboard caching should be disabled.

When pressing the Home button, iOS automatically takes a screenshot to simulate a switch-to-background animation.
Sensitive information MUST NOT be shown on those screenshots by using the delegate-method applicationWillEnterBackground.

### Android

Activities which are used only by the app itself MUST NOT be exported.
Also intents used to start activities MUST NOT content any sensitive information.
The same applies for SharedPreferences.

Sensitive information MAY NOT be included in error messages or locally stored log files.
Exception handling MUST prevent sensitive information to be displayed in the LogCat.

### BlackBerry OS

At the current state of this document there is no specific security option entry available for BlackBerry OS.
That may change at a later state of this document.

### Windows Phone

At the current state of this document there is no specific security option entry available for Windows Phone.
That may change at a later state of this document.

## Cross-platform development: HTML 5 Application Development

### Security of Application Code

When developing HTML5 based applications, several security threats should be considered and addressed to make the application secure, including:

- Cross-site scripting (XSS)
- Cross-origin Resource sharing (CORS)
- Cross-document messaging
- Web workers
- Local storage
- WebSockets
- Application Cache
- Form Tampering
- History Tampering
- Clickjacking
- Stealing sensitive data via Autocomplete
- Web notifications
- Geolocation API
- SVG Graphics Format
- Speech Input
- Additional Experimental API's (Media Capture API, System Information API)

In addition to the aforementioned list of security threats that needs to be addressed, there is also an option to obfuscate the source code of an application to make it harder to understand and thus to prepare and inject malicious code.

Reasons for Code Obfuscation include:
- Conceal purpose of the code
- Deter reverse engineering
- Protection of intellectual property
- Enforce licensing agreements

### Communication Security

HTML5 introduced new possibilities of communication such as WebSockets and Cross-Document messaging, which also introduced new possible security threats.

### Data Security

HTML5 introduced several options for storing data on the client-side.
These may be used for caching purposes for online applications, but also for persistent storage of data for offline apps.
Guidelines to be followed when working with data on the client-side i.e. how to make application data safe are described below:

#### Use a secure connection for communication between client and server.

Storage space is assigned per-origin, but intruders can use DNS spoofing to access user's data.
SSL should be used as prevention.

#### Store as little sensitive information on the client-side as possible.

Enterprise applications often work with a lot of sensitive data such as financial information, personal information, authentication credentials and health information.
It is strongly recommended to avoid storing this type of information on the client-side.
The main for this is that when application becomes compromised using attacks like XSS, all data will be exposed to the attacker.
This should be considered for all types of local storage including the use of the FileSystem API.

#### Store data only for as long as necessary.

All data stored in web storage should not be stored longer than necessary.
If there is a need to store data on the client, always think about using session storage before local storage.
Use local storage only if data needs to be persisted between sessions.

Moreover, always think about the "internet café" option, where several users can access the same application, meaning that they can also access each other's data.
The use of local storage should be avoided completely in these scenarios.
Also, if the FileSystem API is used, data should be cleaned up when the session ends.

#### Validate all data retrieved from storage.

Never trust data retrieved from any type of local storage.
There is a potential threat that the data was modified by third party.
Therefore, all data should be validated before rendering it to the client.

The local storage attribute of the HTML 5 specification can be accessed and modified via JavaScript.
Session ID and any other sensitive data stored locally can be accessed and manipulated by attackers.
It is therefore recommended not to use the local storage for session identifiers.
Encrypting on the client side is possible but would depend on a robust JavaScript cryptography library.

#### Encode all data retrieved from local storage to prevent cross-site scripting.

Similar to the previous point, compromised data storage could contain malicious code, which should be encoded before rendering it to the client.

#### Encrypt data in the local storage.

Unlike session storage, local storage persists between sessions, leaving the data stored on the disk/device so that it could potentially be accessed and modified by attackers.
To avoid manipulation of data, local storage should be encrypted.
As local storage consists of key-value pairs, both keys and values need to be encrypted.

The current implementation of local storage does not contain any options for storage encryption.
It is advisable to investigate support for a local storage encryption API.

#### Use tested libraries from trusted sources.

It is strongly advised not to implement a own solution for cryptography, but rather to use one of the tested libraries from trusted sources, such as the JavaScript Cryptography Libraries.

#### Require data encryption and screen locks on mobile devices.

Mobile devices running enterprise applications, which work with sensitive data, should always use data encryption on the system-level and require screen locks.
This is implemented in all modern mobile operating systems.

#### Follow WebSQL-related rules, if applicable.

Even though WebSQL is deprecated as an HTML5 standard, it is still quite popular and implemented in some of the popular browsers.
If WebSQL is used, the following additional rules should be followed:

- Use prepared statements to prevent SQL injection
- Use unique or randomized database names for each app user
- Database schema of application should be different from enterprise database schema

## Platform Security Alternatives

Where it makes technical sense, use of a vendor supported Mobile Application Development Platform (MADP) may provide a good level of application security, in addition to a reduction in custom code development and hence time-to-market.
However, the built-in security features of individual vendors and their applicability to the use cases that the individual applications need to support should be analyzed thoroughly.

Additionally, and as part of a more holistic approach to mobile security, the Mobile Device Management (MDM) platforms address other important security considerations outside of the application itself.
These should be also taken into consideration.

Some security features (non-exhaustive and vendor dependent) that platforms providers can provide as part of a MDM solution can include:

- Central management
- Enforcing power-on password / password policy
- Silent enforcement in the background
- Remote locking /unlocking / wiping
- Root detection
- Certificate distribution
- Access control / role based access
- Rogue application detection
- Secure distribution / updates of applications
- Encryption of data (what data to encrypt, when to encrypt)
- Removable storage medium (i.e. SD cards) can also be encrypted.
- Updating signature files
- Updating anti-virus definitions / engines
- Managing the configuration of the device.
- Ensuring security policies are enforced and devices remain updated
- Device reset (support for hard reset of device, or deletion of data on external storage media)
- Real-time, inbound and outbound traffic monitoring (scanning any file received via SMS, MMS, Bluetooth, Wi-Fi, infrared, or desktop sync)
- Blacklist and Whitelist filtering (i.e. application filtering)
- Ability to log and report all security activity and being able to pull and deliver detailed reports for any exceptions, violation of company security policy and devices entering and leaving service.
- Reports can be by device type, groups or user type, password entry failure and redeployment of new policy upon reconnection, and you can obtain status of client delivered to handheld devices
- Some platforms support data fading ie allow IT administrator to lock, wipe or reset a device that has not communicated with the corporate network / server for a certain period of time, rendering the device unusable.

The scalability benefits of a platform vendor approach to either mobile application or overall mobile device security will need to be balanced by the need for custom security initiatives and overall flexibility and control.

Additionally, certain Mobile Application Management (MAM) solutions, through a container or sandboxing approach, can secure one or a group of applications, provide policy control mechanisms and separate personal vs. enterprise related applications and data.

Whether the app is an in-house app or publicly available through an App Store, MAM/MDM solutions allow the enterprise to control or restrict users to only allow installation of applications that have been pre-approved.
Normally, this would be managed through a Whitelist and Blacklist.
