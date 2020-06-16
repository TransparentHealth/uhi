# Universal Health Identifier (UHI) (WORK_IN_PROGRESS- FEEDBACK WELCOME)

This purpose of this document is to define a Patient Safety Identifier (PSI) convention for the United States.  UHI is based on the idea of many "Issuers", but the identifier is ideally issued only one time per person.
The specification is an implementation outline for state governments, health payers (insurance companies), health information exchanges(HIE), and health care providers. It is a 15 digit all-numeric number, with the last digit being a checkdigit. An ewxample UHI could be in the form `119800101451391` or `1-19800101-45139-1`.  While not required (not a `SHALL`), including a  birthdate in positions 2-10 is strongly encouraged (a `SHOULD`).



Background and Motivation
-------------------------


The UHI identifier is intended to address the lack of a health identifier in the United States.  Partial use of a social security number (SSN) for this unintended purpose has been problematic to say the least. While not a panacea, creating a patient safety identifier for the people of the United States works to imporve interpoerability and personal control over one's own health data.

A Patient Safety Identifer(PSI) is intended:  

* To be assigned 1 time per person
* To be given to the patient/subject/member (e.g. printed on card)

Here are some considerations for a UHI:

* A UHI should be easy to remember, and should include a person's birthday.
* A UHI should play nicely with automated phone-based systems (telephony).

The convention is a 15-digit number, with the last number 
representing a checkdigit. The checkdigit calculation is prefixed with a numeric ID which
identifies the `issuer`. 


Definitions
-----------

* **`subject`** -  A single human being for whom a UHI is created and maintained. 
* **`issuer`** - A legal entity and/or system responsible for issuing a UHI to a `subject`.


Issuer
------

* An `issuer` SHALL have a `name`, `country_code`, and `uri`.
* An `issuer` MAY have other metadata as needed such as resource locators (e.g. `fhir_uri`).
* Issuers SHALL prevent duplicate UHI issuance by checking the UHI hash register. Issuers will be supplied with the salt and hash necessary to check the hashed UHI webservice.


The UHI Specification
---------------------

* A Universal Health Identifier (UHI) MAY be abbreviated as "UHI". 
* A UHI SHALL be a 15-character ASCII string of only digits (0-9). 
* The first 14 digits (position 1-14) MAY be defined by the Issuer's system.
* Positions 2-10 SHOULD include the subject's birthday in the format YYYYMMDD.
* The last 1 digit (position 15) SHALL be a checksum of the previous 14 digits generated using the Luhn Algorithm applied with a prefix which uniquely identifies the Issuer.
* The Issuer SHALL apply a prefix to the Luhn Algorithm check digit calculation.
* The prefix SHALL be assigned to the Issuer by the UHI webservice governing body.
* A UHI SHOULD be a life-long patient safety identifier for a Subject.
* A UHI SHOULD be one and the same as a `sub` (Subject) within Open ID Connect. https://openid.net/specs/openid-connect-core-1_0.html#SubjectIDTypes



Examples
--------
   
  
  119800101451391

a UHI MAY contain dashes for human readability, but these SHALL be ignored\removed by processing systems.
    
    n-yyyymmdd-nnnnn-n
    
Example (With Dashes)
--------------------

    1-19800101-45139-1

   
In Open ID Connect and JWT the `sub` (Subject) SHALL contain the UHI without dashes. See https://tools.ietf.org/html/rfc7519



Feedback
--------

Comments, ideas, and criticism are welcome. Please contribute via Github issues or a pull request.
