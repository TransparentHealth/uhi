# Univeral Health Identifier (UHI)
DRAFT - Universal Health Identifier 

This purpose of the Univeral Health Identifier (UHI) is to defone a univeral health identifier format for the citizens of the United States.  It is based off a US phone number plus 4 digits. Here are some consideration for a uhi:

* It should be easy to remember
* It should play nicely with automated phone based systems (telephony) as well as Internet systems.
* It should be designed for those that opt-in and should favor convienence over security.

A Specification
-------------

A UHI bhall consist of a 14 string of digits:

    nnnnnnnnnnnnnn

For example:
  
  30483755554321

It may contain dashesfor human readability, but these SHALL be are are ignored for processing. but are meant only for human  
    
    nnn-nnn-nnnn-nnnn
    
For example:

    304-837-5555-4321
    

In OAuth2, Open ID Connect, and JWT the `sub` (Subject) MAY contain the UHI without dashes. See https://tools.ietf.org/html/rfc7519


This is a draft and should be considrewd like a whiteboard. Comments, ideas and criticism are welcome.
