#################################
Difference Between SSO and OAuth
#################################


`OAuth is not Single Sign-On
<https://stormpath.com/blog/oauth-is-not-sso>`_



**OAuth** is an ``authorization protocol``.

**SSO** is an ``authentication / authorization flow`` through which a user can log into multiple services using the same credentials.

For instance, at your company, you might want to use one set of credentials to access:

- Your internal company website.
- Your Salesforce account.
- Your Atlassian account.
- etc.

Instead of making each employee at your company create different accounts for each of those services they use all the time, you can instead create a single account for each employee that grants them access to all of your company services.

This is SSO.


YouTube - Understanding Authentication and Authorisation Protocols
###################################################################



Authentication
+++++++++++++
AuthX
``who are you?``

Assuptions for now:

entity = a person
claim = email address
proof = password


Authorisation
+++++++++++++
AuthN
``what can this entity do?``
- Once I have an identity, I can check permissions
- Will affect menus, page access, function access, text labels, extra content and more.
- An identity allows us to group entities into roles. Roles make authorsation easier but are not requeired for AuthX/N


Problem
+++++++++++++
- Convenience
- Security
- Collaboration  (many goups of organisations want to work together)
- Unattended access


Solutions
+++++++++++++
- SAML/Shibboleth
- OpenID
- OAuth2
- OAuth2 + OpenID Connect
- Several others


SAML/Shibboleth
+++++++++++++++++
- Security Assertion Markup Language
- High-level protocol for 'exchanging security assertions'
- Mature but old/arguably oudated
- XML-based
- Shibboleth is Java-based AuthX implementation for SAML
- Tightly-bound, strongly checked
- Theoretically strong = **complicated to implement**


OpenID
+++++++++++++
- Open source authenticaiton protocol
- De-centralised =  **trust issues**
- Discovery protocol
- Arguably terse documentation = **hard to understand**
- URLs and XML = **developers don't like**
- Poor developer take-up


OAuth/OAuth2
+++++++++++++++++
- An authorisation protocol designed for API access  (ex. Facebook)
- Often used (incorrectly) for authentication
- Does not always authenticate user
- Allows unattended access without authentication
- v1 = TLS not requred = digital signatures = poor uptake
- v2 = TLS requried = simple data exchange = popular
- The two are not compatible

**OAuth2 for authentication**

- Restrict any unattended operations e.g. refresh tokens
- Always require authentication from the provider
- But: you have no way of enforcing or knowing this in OAuth2
- Vague specification = many different implemattions
- Virtually all plugins have a class per provider

**OAuth2 + OpenID Connect**

- Has add a few more varations of OAuth2 'flows'
- Has standardized more of OAuth2's vagueness
- Much easier to implement a 'standard' provider
- Some details changes (new parameters etc.)
- Signature required for id token (can be done via library)
- Instead of/as well as 'auth code', RP gets an 'ID token'
- ID token is signed Javascript web token
- token contains information about the user including AuthX details
- Allows pure identity providers to bypass normal OAuth2 flow
- Also allows distributed log out

**Summary**

- Various protocols exist
- Some are outdated
- Difficult protocols don't get embraced by developers
- People don't link working with potentially complex exchange like signature, XML and Java.
- For general use, OAuth2 + OpenID Connect is likely to be the future
- Libraries already exist e.g. IdentityServer, to delegate the difficult bits




































