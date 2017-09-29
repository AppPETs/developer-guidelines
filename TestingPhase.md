# Testing Phase

During the testing phase the software is tested in various ways to ensure all features work as intended and the overall quality is as intended. This section covers the testing processes, which are specifically designed to test against weaknesses in the software, that might lead to data leaks or a violation of the privacy of the user.

* standard QM/QA steps to acomplish development quality

## Penetration tests

Penetration tests are a set of tests for software applications or specific hardware components such as networks. The goal of these tests is to find security holes in the interfaces between the system and the user. The tests are performed from the perspective of a potential attacker from the outside of the system. It is a so called black-box test and can usually be performed with the help of automated tools.

## Audits

Software audits are a systematic examination of the software. The goal of this process is to detect errors in critical software modules, that could potentially lead to threats to the whole system. In a number of seperate sessions, the written code gets reviewed by a team of several people, usually all the stakeholders of the software in question, that are somewhat in charge of the quality control. This might include the authors of the software, the risk managers and the quality assurance. The audit process might be very time consuming, since it is common to review a module more than once, for example after the first detected errors are corrected and have to be reviewed again for new errors, that might have found its way in the software through the correction itself. This process is a so called white-box test.


-- Anmerkungen:
Ist bisher alles auf das Essentielle heruntergebrochen. Soll das noch ausführlicher?


Es gibt noch so ein paar Tests, die in sicherheitskritischer Software häufig eingesetzt werden. Sind die hier noch angebracht, oder ist das overkill?
- Data flow testing?
- Control flow testing?
- Modified condition/decision coverage testing?
