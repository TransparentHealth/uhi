# Univeral Health Identifier (UHI)
DRAFT - Universal Health Identifier 

This purpose of the Univeral Health Identifier (UHI) is to define a univeral health identifier convention for the United States.  UHI is intended to be implemented by governments, health payers (insurance companies) and health care providers when assigning a patient-selected (or member selected) master patient index (MPI). 



Here are some considerations for a UHI:

* A UHI should be easy to remember.
* A UHI should play nicely with automated phone-based systems (telephony) as well as Internet systems.


The proposed convention is a 15 digit number.


Definitions
-----------

* **Individual** -  A single human being for whom a UHI is created and maintained.
* **Issuer** - The system and legal entitiy responsible for issing a UHI to an Individual.


The UHI Specification
---------------------

* A Universal Health Identifier (UHI) MAY be abbreviated as "UHI". 
* A UHI SHALL be a 15 chacter ASCII string of only digits. 
* The first 14 digits (position 1-14) SHALL be system defined by the Issuer
* The first 14 digits (position 1-14) MAY be defined by the individual identified by the UHI.
* The first 14 digits (position 1-10) MAY be the Individual's phone number.
* The last 1 digit (position 15) SHALL be a checksum of the previous 14 digits generated using the Luhn Algorithm.
* A UHI SHOULD be permanent for an Individual.
* A UHI MAY be one and the same as a `sub` (Subject) within Open ID Connect. https://openid.net/specs/openid-connect-core-1_0.html#SubjectIDTypes 


Example
--------
   
  
  304837555543213

It may contain dashes for human readability, but these SHALL be are are ignored for processing.
    
    nnn-nnn-nnnn-nnnn-n
    
Example (With Dashes)
--------------------


    304-837-5555-4321-3
    

In Open ID Connect, and JWT the `sub` (Subject) MAY contain the UHI without dashes. See https://tools.ietf.org/html/rfc7519



Feedback
--------

This is a DRAFT. Comments, ideas, and criticism are welcome. Please contribute via Github issues or a pull request.
