# Univeral Health Identifier (UHI)
DRAFT - Universal Health Identifier 

This purpose of the Univeral Health Identifier (UHI) is to defoioe a univeral health identifier format for the citizens of the United States.  It is based off a US phone number plus 4 digits. Here are some consideration for a UHI:

* A UHI should be easy to remember.
* A UHI should play nicely with automated phone-based (telephony) systems as well as Internet systems.
* A UHI should be designed for those that "opt-in" and should favor convienence over privacy and security.

Thge UHI Specification
----------------------

A Universal Health Identifier(UHI) MAY be abreviated by UHI. 

A UHI SHALL be consist of a 14 string of digits:

    nnnnnnnnnnnnnn

For example:
  
  30483755554321

It may contain dashesfor human readability, but these SHALL be are are ignored for processing.
    
    nnn-nnn-nnnn-nnnn
    
For example:

    304-837-5555-4321
    

In OAuth2, Open ID Connect, and JWT the `sub` (Subject) MAY contain the UHI without dashes. See https://tools.ietf.org/html/rfc7519


This is a draft and should be considered like a whiteboard. Comments, ideas, and criticism are welcome.
