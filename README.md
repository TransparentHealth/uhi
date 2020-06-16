# Universal Health Identifier (UHI) (WORK_IN_PROGRESS- FEEDBACK WELCOME)

This purpose of the Universal Health Identifier (UHI) is to define a Patient Safety Identifier (PSI) convention for the United States.  UHI is based on the idea of many "Issuers", but the identifier is ideally issued only one time per person.
The specification is an implementation outline for state governments, health payers (insurance companies), health information exchanges(HIE), and health care providers.

The UHI identifier is intended:

* To be assigned 1 time per person
* To be given to the patient/subject/member (e.g. printed on card)

Here are some considerations for a UHI:

* A UHI should be easy to remember.
* A UHI should play nicely with automated phone-based systems (telephony).


The proposed convention is a 15-digit number.


Definitions
-----------

* **Subject** -  A single human being for whom a UHI is created and maintained. 
* **Issuer** - A legal entity and/or system responsible for issuing a UHI to a Subject.


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



Example
--------
   
  
  119751217206007

It may contain dashes for human readability, but these SHALL be are are ignored for processing.
    
    nnn-nnn-nnnn-nnnn-n
    
Example (With Dashes)
--------------------

    1-19751217-20600-7

    

In Open ID Connect, and JWT the `sub` (Subject) MAY contain the UHI without dashes. See https://tools.ietf.org/html/rfc7519



Feedback
--------

This is a DRAFT. Comments, ideas, and criticism are welcome. Please contribute via Github issues or a pull request.
