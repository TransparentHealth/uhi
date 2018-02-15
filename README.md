# Univeral Health Identifier (UHI)
DRAFT - Universal Health Identifier 

This purpose of the Univeral Health Identifier (UHI) is to define a univeral health identifier convention for the United States. The proposed convention is a 15 digit number. UHI is intended to be implemented by health payers and providers when assigning a member-selected/patient-selected master patient index. 

Here are some considerations for a UHI:

* A UHI should be easy to remember.
* A UHI should play nicely with automated phone-based (telephony) systems as well as Internet systems.
* A UHI should be designed for those that "opt-in" and should favor convienence over privacy and security.


The UHI convention maps to a phone number and a PIN (i.e. a 10 digit number plus 4 more digits. 


The UHI Specification
---------------------

A Universal Health Identifier(UHI) MAY be abreviated by UHI. 

A UHI SHALL be a 15 chacter ASCII string of only digits. The first 14 digits are user defined. The last digit is a checksum of the previous 14 digits generated using the Luhn Algorithm:

    nnnnnnnnnnnnnnn

For example:
  
  304837555543213

It may contain dashesfor human readability, but these SHALL be are are ignored for processing.
    
    nnn-nnn-nnnn-nnnn-n
    
For example:

    304-837-5555-4321-3
    

In OAuth2, Open ID Connect, and JWT the `sub` (Subject) MAY contain the UHI without dashes. See https://tools.ietf.org/html/rfc7519



Feedback
--------

This is a draft and should be considered like a whiteboard. Comments, ideas, and criticism are welcome. Please add Github issues.
