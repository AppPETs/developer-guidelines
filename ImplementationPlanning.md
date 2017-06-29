# Mobile Application Security – Implementation Planning

This chapter is dedicated to project managers and test managers and contains detailed information about integrating the data protection and data security aspects into the application production lifecycle.

## Mobile Application Security throughout the Lifecycle

Irrespective of mobile platform choice developers need to have a clear understanding throughout the development process as to how they will address the issue of security.

A lifecycle approach (e.g. Scrum or similar models) is recommended throughout to support the highest level of security possible.
There needs to be buy-in from all stakeholders and a standards based approach to address mobile application security holistically.

Mobile application security is implemented in all stages of the application's life cycle, similar to device security.
The following sections discuss the methods and tools for securing mobile applications.

### Security Integration into the Development Lifecycle

It is recommended that the secure software practices are integrated early into the application development lifecycle so as to be less disruptive during the remediation process.

Applications testers are responsible for ensuring the application meets the established requirements and functions correctly.
Both functional testing and security testing should be performed during the testing phase of the software lifecycle.

### Security Testing and Evaluation

The application testing process is vital in identifying security flaws before the application is released.
In addition to the standard functional testing performed, the development team will have resources specifically testing the application for security flaws.

Examples of testing tools are manual code review, automated code review, third party code review, static analysis tools and web application vulnerability scanners.
A designated Testing Manager will ensure that code is reviewed, defects are tracked and flaws are fixed or addressed in the project plan.

### Security Source Code Review

Source code review is an integral part of mobile application software testing.
Source code testers must inspect program code to ensure compliance with established functionality and security standards.
This is a time consuming process which is aided by methodology and automated tools.

### Automated and Manual Code Review

Automated code reviews can quickly identify the weak areas of an application.
Many automated tools (both standalone applications and web-based tools where source code can be uploaded for analysis) exist for the evaluation of code in traditional languages (e.g. Java, C++); many of these tools extend their capabilities to mobile languages or mobile adaptations of languages (e.g. Objective C, Java for Google Android).

Most of the Java plugins in Eclipse can be used for analysis of Android code.
Also Android provides tools such as DDMS for debugging.
For iOS the development platform provides a Static Analyzer and Instruments tool integrated within the Xcode IDE.

Additionally a manual review of the code, where a human visually inspects lines of code for security issues, can be employed where it is feasible.
Manual reviews are more time consuming than automated reviews and are reliant upon the skill and experience of the reviewer to find security flaws, but they have the advantage of being able to detect forms of vulnerability that might not be found through automated analysis.
Manual code review procedures should be put in place to disqualify false positives and manually check for security vulnerabilities the automated tool fails to identify.

Techniques for manual code review include spot inspection, methodical inspection and full inspection:

-   Spot inspection

    Only portions of the software source code are manually analyzed.
    The selection of code segments is based on indicators from either the client about suspect sections of the source code or from the results of an automated tool.

-   Methodical inspection

    Inspection is based upon logical flow of source code and the analyst's intuition.
    The design documents will be required in order to understand the software design flow.
    The embedded comments in the source code will also be examined to determine indicators of logical security errors.
    Not all of the source code is examined for logical flaws; just the areas where indications lead the analyst.

-   Full inspection

    All source code is inspected for logical errors.
    The design documents and embedded source code are examined for indicators of logical flaws.

Successful and efficient code review procedures for mobile technologies will include a combination of both automated and manual techniques.

### Static and Dynamic Analysis

Both static and dynamic analysis tools can be leveraged for automated code review.
Static analysis tools are valuable if the code is very large.
These tools are made specifically to analyze code based on programming language, support an underlying database for collection and reporting, and provide remediation suggestions for vulnerabilities found.
Some examples of commercially available static analysis tools are Ounce Labs, Coverity Prevent and Fortify Source Code Analyzer.
Note that not all of these tools may support mobile device specific programming languages.

Dynamic analysis is based on application execution, either on the mobile device or via an emulator.
Therefore, it can detect issues that will not be detected via static analysis, including time-based issues and data issues.
However, dynamic analysis is often dependent on user interaction, especially for mobile apps.
A simple example of a dynamic analysis tool is a debugger.

Successful and effective code review will include both static and dynamic analysis to ensure the largest possible set of security vulnerabilities can be detected and eventually remedied.

### Third-Party Code Review

Several commercial companies offer code review services.
Companies use a mixture of automated reviews and manual reviews by experienced auditors.
Third-party review is valuable if the application is highly exposed, is large, or cannot be manually reviewed in depth.
This procedure often requires code to be sent to a third party.
If code is sent electronically, security measures must be considered for secure transmission and measures must be in place for intellectual property protection.
Alternatively, third party reviewers must be brought on site for the evaluation process.

### Penetration Tests

Integrate Penetration Tests into the development lifecycle

### Access Control

Access controls on credentials are the physical/tangible objects that identify the individual and enable access to computer-based information systems, devices or physical locations.
The most common access control methods are PINs/passwords and CACs.
These access control methods protect the enterprise by allowing only authorized personnel access to approved devices.

Password authentication may be used as an underlying certificate to a user account.
If password authentication is used, password complexity and maintenance requirements must be enforced.
Password complexity combines minimum length, upper, lower case, numbers, and symbols.
Password masking (display of asterisks when users enter their password) must also be enforced.

### Mobile Web App Security / Mobile Browser Security

Mobile browser security is governed by Browser sandbox or Web-view Sandbox.
Both models are based on the WebKit engine.

Additionally, mobile web apps can be secured with libraries that are added to consumer ready apps.
This secures the app at the source code level.
Securing apps with this method ensures the data path through the network is encrypted end-to-end (see 3.1).

A secure browser policy lists all the Intranet domains, sub-domains, and embedded Internet domains that administrators make available on the mobile device.
A secure browser provides a browser history, which can be cleared.
It utilizes a secure container for browsing, thus storing all the data in encrypted format.
This ensures secure and separate enterprise data.

### Web Application Vulnerability Scanners

Web application vulnerability scanners allow testers and application developers the ability to scan the web applications in a fully operational environment and check for many known security vulnerabilities.
Web application vulnerability scanners parse URLs from the target web site to find vulnerabilities.
These scanners check web applications for common security problems such as SQL injection, cross site scripting, command injection, buffer overflow, session management, and other vulnerabilities.

### Application Lifecycle Management

Application Lifecycle Management (ALM) can be divided into three significant events: idea, deployment, and decommissioning.
In the first phase of the lifecycle, an existing app is selected for use within the enterprise and secured at the source code level.
The secured app is then deployed through an app store hosted by the client's server resources.
During deployment, the app is maintained via Mobile Device Management (MDM).
MDM maintains the device by continuously monitoring for compliance and enforcing required updates.

When the app has reached its end of service, proper migration procedures should be in place to replace user functionality that would be lost with the decommissioning of the app.
This should minimize any negative effects from the lost functionality.
App decommissioning (e.g. uninstallation and/or wipe of selected data) would be enforced through a MDM.

## SSL/TLS Implementation Guidelines

In addition to securing the application itself it is paramount to secure the channel used to send and receive data.
Strong encryption techniques must be used for transmitting sensitive data or information.
Use standard security protocols such as TLS or secure channel signing and sealing.

Configure internet transmission to use TLSv1.2 or higher.
Only 128 bit cipher keys or higher can be enabled.

Certificates must be from a reputable certificate authority; the application must not allow unsigned certificates and must not disable TLSv1.2 or higher chain validation.

Do not use SMS or push notifications as a secure channel of transmission.

For more information about this "fast changing" area of secure communication external information like the "Mozilla Server Side TLS Guidelines" should be used.

### "State of the Art" integration of cryptography

(USE Checlist Definition)

## Identity and Access Management Guidelines

Where technically possible, the login mechanism for applications must abide by the controls defined by the internal IT standards, but the following password complexity requirements can be used as guideline:

-   Password
    -   $Insert Company Password Policy
    -   password length must exceed 12 characters
    -   use of upper- and lower-case letters (case sensitivity)
    -   inclusion of one or more numerical digits
    -   inclusion of special characters, e.g. `@`, `#`, `$` etc.
    -   prohibition of words found in a dictionary or the user's personal information
    -   prohibition of passwords that match the format of calendar dates, license plate numbers, telephone numbers, or other common numbers
    -   prohibition of use of company name or an abbreviation
-   Login
    -   Password must be masked upon login
    -   Login fields must or suggest valid user IDs or password/passphrases.

        Auto-complete attribute of login form must be explicitly set to 'off'.
-   System
    -   Must enforce a password change for new accounts on first login
    -   Must enforce a password change in appropriate timeframe (e.g. 75 days)
    -   The initial one-time password, for new accounts, must ONLY be sent to an email address on file for that user.

        An email informing of the password change must be sent to the email address on file after the password change.
        The email must not contain the user id. Where technically possible, the email must be encrypted
        Account lockout after 7 failed login attempts within a 30 minute period
        Idle timeout must be at least 60 minutes for confidential and highly confidential data, at least 30 minutes for restricted data
-   Authentication
    -   In general, if a mobile application will store any type of restricted or highly sensitive data, two-factor authentication is recommended
    -   If basic authentication must be used, an encryption mechanism such as TLS or IPSEC must be employed to protect the plaintext credentials
    -   Ensure authentication credentials or tokens are transmitted to the back-end with every request made from the mobile application
    -   Authentication attributes used by the application must map to the end user instead of the device.

        E.g. device attribute such as Unique Device Identifier (UDID) or device serial number must not be used
-   Administration / Account Management
    -   Users and administrators must all use a unique ID, shared IDs must not be used
    -   The application must have a facility that will enable an administrator to define role-based access control and configure granular permissions.

        Least privilege principle must be implemented
    -   Development team members' access to source code in the development and test environments must be reviewed at least every 6 months or when people roll-off

### Auditing and Logging

User access activities must be logged and audited to identify unauthorized access and to determine possible flaws in the access control system.
At a minimum, successful and failed user logon and logoffs must be captured (i.e., data & time stamp, user ID, application name, pass/fail indicator) and recorded on the back-end system rather than the mobile device.

### Privileged Account Controls

There must be no shared user IDs.
Define a formal authorization process for granting, modifying and revoking of administrative access to the application.

## Application Hardening Guidelines

For application hardening and preventing vulnerability exploitations, a number of methods need to be implemented.
These include:

-   Client and server side input validation must exist for all input fields.
-   Validate input for data type, character length, regular expression and custom expressions, etc. Apply HTML encoding.
-   Validate all inputs by the server-side code.
-   Ensure proper length limit on application parameters and URLs.

    Validate strings length, expected characters and pattern.
    Use regular expressions for validation as necessary.
-   Validate numeric values are indeed numeric and fall within the expected value range.
-   Reject inputs with potentially malicious characters.

    Sanitize input to exclude context-changing symbols such as apostrophe, quotes, etc.; as well as script characters such as `< > " ' % ; ) ( & +`, `<script>`, `</script>`, JavaScript: `img`
-   Use parameterized SQL query statements.

    Input values must not be directly concatenated to SQL query statements.
-   Track all third party frameworks/APIs used in mobile applications for security patches.
-   Use static code analyzers during the build process to identify security flaws.
-   Use safe string functions during development to avoid buffer and integer overflows.
-   Do not use sensitive parameters in the URLs (i.e., user id, session id, etc.).

    When compiling the application for distribution, the application must be build using the Release/Distribution configuration and not DEBUG configuration.

## Mobile Security Reference Architecture

Clarifying a mobile security reference architecture (see Figure 1) can help to analyze and document the mobile environment during a risk assessment.
It covers main components of mobile platforms, presents its relationship and interconnections, to identify where threats exist and where to apply controls to mitigate them.

The Mobile Security Reference Architecture should serve a basis for a list of questions to be answered as part of a broader risk assessment.
Example questions that could be reviewed as part of the assessment

- What connections are there between the components?
- Which protocols are used?
- Are the connections secured?
- Have they been tested and verified?
- Where is the data stored?
- What components are missing?
- Are there any limitations that arise?
- Is performance of the application impacted?

**Mobile Application Security – Implementation Phase**

The guideline chapter related to the Implementation Phase contains all aspects relevant to data protection, cloud storage services, 3rd party modules, update and remote wipe functionality.
All applicable prerequisites mentioned in the earlier chapters should have been fulfilled or being worked on when the Implementation Phase starts.
