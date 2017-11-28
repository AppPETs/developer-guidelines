# Implementation and documenting Phase

In this phase, the developers create the software code and documentation for the project.

## Established Best Practices

To establish and follow the best practises of software development the programmers should be aware of security and privacy recommendations. Please refer to the “Smartphone Secure Development Guidelines for App Developers” or “Privacy and Data Protection by Design – from policy to engineering” for further information on those topics. (LINKS)

### Test-Driven Development

To verify the correctness of the implementation the software should be tested. In order to detect failures of the implementation in early stages the approach of test-driven development can be used. Hereby, the developers write first the code for automated testing and implement afterwards the code to pass the described test. The single tests can be integrated into an automated test suite to validate the correctness of the entire implementation.

### Continuous Integration

When several programmers work on the same code the risk of conflicting contributions to the code base by different programmers arises. Those conflicts arise due to modifications of the existing code base or by adding new code and dependencies to the project. To avoid these problems a best practise known as “Continuous Integration (CI)” can be applied, where developers integrate their contributions early and often into the common code base.

### Proper Documentation

A technical documentation of the code may contain information about what a code does and how it does it, its dependencies and where this code is required. These documentations are valuable for the programmers and the maintainers of a specific code base and should be written along with the implementation of the code.

### Take Care of Third Party Code

The use of third party code / services may be beneficial or even necessary for the implementation of a software project. The integration of such code or service into a software project comes along with additional dependencies. To sustain the quality of the software project the third party code / service should be checked whether it fulfils the given privacy and security requirements. If a third party code is no longer maintained, this can lead to security and compatibility issues. In those cases, it is recommended to self-maintain such code. Besides the technical integration of third party code / services one should verify that the licence, under which the usage of a third party code / service is allowed, integrates with the software project.

### Reconsider Preceding Phases Where Necessary

If during the implementation phase challenges arise which require to deviate from the original design, this should be done by an additional iteration of the analysis phase.


## **The Privacy Library and Privacy-enhanced Technologies**

The Privacy Library \(plib\) is a development library one can integrate into the app development environment. The plib contains a collection of various methods, separated into two classes: i\) methods for ensuring self-determination about privacy-related data and ii\) methods offering various security-related functions including complex privacy-enhanced technologies \(PETs\).



The plib can be regarded as a **privacy data flow coordinator for data**, which have to leave the app’s area of influence, for example data, which is sent through network connections but also data, which get stored on a shared storage such as the sd card of a mobile device. The plib, regarded as a trusted component, is an essential component of the app audit process including a static data flow analysis. Under consideration of the internal of particular plib methods, a data flow outside the app’s influence can be regarded by the audit process as a legitimate data flow where self-determination with respect to the user’s private data is guaranteed, for example for methods, in which the user is asked to grant a given data flow at runtime or methods, in which sent data is securely encrypted by the plib’s encryption methods.



### **Pre-conditions and assumptions**

Although we believe that developers, which integrate the plib into the development process, do not have bad intentions, the only **trust is given to methods of the plib** during an audit process. With this, from the perspective of a developer we can argue that methods of the plib can be regarded as trustworthy black boxes without the influence of the app developer itself.

**The app audit in combination of the plib has to proof the self-determination of the app's user about his private data.** Self-determination about the data means, that the runtime user has not only knowledge about private, from others interpretable data flows, he should have furthermore the ability to prevent such data flows, if desired. This proof, given by the audit process can only apply for the app implementation and third components, where the functionalities of those components are well-known and trustful, for example so-called remote privacy services \(pservices\).

In order to be regarded as a trustful app, **private data in interpretable form can leave the app's area only if such a data flow is granted by the user or the receiver of such data is also known as trustful**. It should be stated that consequently in order to regard an app as privacy-friendly it is not prohibited to exchange private data in forms which are not interpretable by others. For example, **private data can leave the app's area in encrypted, anonymized or pseudonymized form**.
(REMARK: Hinweis auf die begrenzte Wirksamkeit von Pseudo-/Anonymisierung?)
As stated, the abandonment of the app's area is not only done through classical network connections. On today's mobile devices also other channels should be considered such as Bluetooth connections, outgoing SMS, NFC or even the shared memory, where third-party processes \(which are unknown by the audit process\) can read stored data and send the content anywhere.



### The Privacy Library Usage

The integration of the plib into an own development process is quite simple. The developer has just to refer the build path to the given library. The plib offers as mentioned various methods, documented by a separate interface documentation. **One aim of the plib is to offer IT-security-related complex technologies without to demand very deep knowledge for such complex technologies by the developer.**

Plib interfaces are clearly named and require as few as possible parameters in order to be used. For example, in order to encrypt a given file, one can use the plib interface "encrypt" with a pointer to the file as the only parameter. **The developer does not have to deal with passwords, encryption algorithms, key storage and handling.**

Some complex algorithms are outsourced to remote servers, so called privacy services \(pservices\), for example storage solutions, in which it is guaranteed that nobody except the data owner has cognisance of the existence and the content of this data, neither the pservice operator. For the realization of such complex methods, state-of-the-art-based privacy enhanced technologies \(PETs\) are used. For the developer it is not necessary to know "how it works" in detail. As stated as a pre-condition, also these PETs are regarded as trustful.

**In fact, various documents, certificates of reliable institutions and/or the community will document the fullfilment of these pre-conditions, since all parts of the plib will be open source.**

### Plib Methods

The plib offers methods for granting data flow by the user at runtime \(so-called "allow-flow"-functions\). Beyond that, the plib offers also "access-flow"-functions. For both types, in dependency of the user decision, data are allowed to be sent out the app's influence area, either in its original plain form, anonymized, pseudonymized or encrypted.

#### "Allow-flow"
The **"allow-flow"** type is beneficial for those developers, who are already in possession of an app development. In order to adapt existing developments into privacy-friendly applications, the developer can let the app **request permission** by the runtime user before sending items. The way of accessing private data remains unmodified.

#### "Access-flow"
The **"access-flow"** type operates directly on accessing private data.

The plib offers a number of different access methods, depending the type the developer is intended to access. In order to access exemplary mentioned contacts of the device, the plib visualizes at first a list of all available contacts to the runtime user and let him select a subset of all contacts before asking the runtime user, in which form the selected data have to be granted \(plain, encrypted, anonymized, pseudonymized\) or not. Once granted by the runtime user, the app can process given contacts as needed \(for example sending them somewhere\). **The access, the pre-selection and the definition of the form of the private data is done by the runtime-user and is not within the influence of the developer itself.**

If the developer implements a side-channel, where not for flow granted data leaves the app's influence, the static data flow analysis as part of the audit process will identify such a case. The developer can define a text message, which is displayed to the runtime user while making such a decision. The user can define not to be asked anymore in the future for given data type by checking a given checkbox. This persistent decision can be made dependent on the access position within the implementation \(stack trace\) and depends on the text, the developer transmitted programmatically for displaying. Once such decisions are made persistent, the user will not be asked anymore and consequently the selected data is leaving the plib to the developer area without the "user ask" process.

Such persistent decisions are revocable through the plib user interface. The audit process must also include an evaluation and ensure that the developer's app offers also a link to the plib user interface, for example within the apps settings area.

#### Unproblematic data access

Beyond the "user ask"-processes, the plib offers also methods for accessing private data without demanding access by the runtime user, in which the data is accessed in forms not interpretable by others, in this case in an anonymized, pseudonymized or encrypted form.

**One challenge is the anonymization and a stricter challenge is the pseudonymization of data objects.** First, the evaluation
(REM: it= the evaluation?)
has to ensure that the plib delivers anonymized or pseudonymized objects in their correct structure. For example, IPv4 addresses are structed by four values in the range between 0 and 255. Phone numbers can have a plus or not and when only on the first position and are defined by digits and can carry also brackets and spaces. Location objects are defined by latitude and longitude within defined ranges. The challenge here is to adapt values, that are themselves legitimate structed. The caller and receiver of such data objects should not be able to determine that the given data object is not the real one. This challenge becomes harder for pseudonymizations, in which it should be able to determine the original data object, if required. This is done by structure-related encryptions.
(REM: The difficulty of pseudonymisation of data with little entropy e.g. phone numbers is discussed here: https://signal.org/blog/contact-discovery/, is this taken into account into the plib or the evaluation?)







