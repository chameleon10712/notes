#################################
Difference Between SSO and OAuth
#################################





OAuth與SSO的區別？
++++++++++++++++++++++++
`[ref]
<http://blog.51cto.com/favccxx/1635938>`_
[翻譯]

OAuth是一種授權協議(authorization protocol)，只是為用戶資源的授權提供了一個安全的、開放而又簡易的標準。OAuth 2.0為客戶端開發者開發Web應用，桌面端應用程式(Desktop App)，行動應用程式(Mobile App)及客廳設備提供特定的授權流程。

SSO是在多個應用系統中，用戶只需要登錄一次就可以訪問所有相互信任的應用系統。

通俗的講，OAuth是為解決不同公司的不同產品實現登陸的一種簡便授權方案，通常這些授權服務都是由大客戶網站提供的，如QQ，新浪微博，人人網等。而使用這些服務的客戶可能是大客戶網站，也可能是小客戶網站。使用OAuth授權的好處是，在為用戶提供某些服務時，可減少或避免因用戶懶於註冊而導致的用戶流失問題。

SSO通常處理的是一個公司的不同應用間的訪問登陸問題。如企業應用有很多業務子系統，只需登陸一個系統，就可以實現不同子系統間的跳轉，而避免了登陸操作。

OAuth與SSO的應用場景不同，雖然可以使用OAuth實現SSO，但並不建議這麼做。不過，如果SSO和OAuth結合起來的話，理論上是可以打通各個公司的各個不同應用間的登陸問題，但現實往往是殘酷的。

**OAuth與REST的關係？**

談到REST的安全性問題時，很多人容易聯想到使用OAuth來解決這個難題。其實，REST與OAuth有著天壤之別。

OAuth為網站（系統）用戶授權第三方應用(third party App)（網站、系統）訪問自己在網站（系統）中的隱私數據(private data)提供的一種規範。

REST初期理念是“每個不同的子資源都有一個絕對唯一且不重複的URI地址”。它僅僅是一個URI資源 (URI resource)而已，而且是無狀態的(stateless)，因此REST並不適合做需要授權的應用。恰恰相反的是，在使用OAuth授權時，通常會使用REST API來完成授權操作。




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




































