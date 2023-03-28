<!-- TOC start -->
- [Different Authentication protocols](#different-authentication-protocols)
  * [1. LDAP](#1-ldap)
  * [2. Kerberos](#2-kerberos)
  * [3. Oauth 2](#3-oauth-2)
  * [4. SAML](#4-saml)
  * [5. RADIUS](#5-radius)
  
  [_How to choose which one to use ?_](#_how-to-choose-which-one-to-use-_)
<!-- TOC end -->
<!-- TOC --><a name="different-authentication-protocols"></a>
# Different Authentication protocols

Here are the five most used authentication protocols

<!-- TOC --><a name="1-ldap"></a>
## 1. LDAP

_Lightweight Directory Access Protocol_
The LDAP is an open, vendor-neutral, industry standard application
protocol for accessing and maintaining distributed directory information services over an Internet Protocol (IP)
network.

LDAP works by binding an LDAP user to an LDAP server. The client sends an operation request that asks for a particular
set of information, such as user login credentials or other organizational data. The LDAP server then processes the
query based on its internal language, communicates with directory services if needed, and responds. When the client
receives the response, it unbinds from the server and processes the data accordingly.

<!-- TOC --><a name="2-kerberos"></a>
## 2. Kerberos

Kerberos is a computer-network authentication protocol that works on the basis of tickets to allow nodes
communicating over a non-secure network to prove their identity to one another in a secure manner

![](https://upload.wikimedia.org/wikipedia/commons/thumb/6/68/Kerberos_protocol.svg/967px-Kerberos_protocol.svg.png)

<!-- TOC --><a name="3-oauth-2"></a>
## 3. Oauth 2

OAuth (short for "Open Authorization") is an open standard for access delegation, commonly used as a way for
internet users to grant websites or applications access to their information on other websites but without giving them
the passwords.

![](https://upload.wikimedia.org/wikipedia/commons/7/72/Abstract-flow.png)

<!-- TOC --><a name="4-saml"></a>
## 4. SAML

_Security Assertion Markup Language_
SAML is an open standard for exchanging
authentication and authorization data between parties, in particular, between an identity provider and a service
provider. SAML is an XML-based markup language for security assertions (statements that service providers use to make
access-control decisions). An important use case that SAML addresses is web-browser single sign-on (SSO).

![](https://upload.wikimedia.org/wikipedia/commons/thumb/0/04/Saml2-browser-sso-redirect-post.png/900px-Saml2-browser-sso-redirect-post.png)

<!-- TOC --><a name="5-radius"></a>
## 5. RADIUS

_Remote Authentication Dial-In User Service_
ou provide a username and password, and the RADIUS system verifies the information by comparing it to data in a
database.

<!-- TOC --><a name="_how-to-choose-which-one-to-use-_"></a>
### _How to choose which one to use ?_

- **Application needs**. What systems and resources require access? How significant or private are they?
- __Infrastructure__. What protocols can you launch without overhauling your existing system?
- __Effort__. How much training or programming will you need before you can get started?
- __Future__. Can the system grow and change with your company?

