# Authentication

Authentication refers to the process of identifying an individual, usually based on a username, password, and some type of additional verification.

## _Securing Passwords_

**Passwords** are the first line of defense against cyber criminals and the most vital secret of every activity we do over the internet .     

 **Cryptographic** hash algorithms MD5, SHA1, SHA256, SHA512, SHA-3 are general purpose hash functions, designed to calculate a digest of huge amounts of data in as short a time as possible.   


_The benefit of hashing is that if someone steals the database with hashed passwords, they only make off with the hashes and not the actual plaintext passwords.

PROBLEMS WITH CRYPTOGRAPHIC HASH ALGORITHM: 
1. Brute Force attack  
2. Hash Collision attack
3. BCrypt, IT's SLOW AND STRONG AS HELL 

## _Basic Auth_

basic access authentication is a method for an HTTP user agent (e.g. a web browser) to provide a user name and password when making a request.    

- Features :
HTTP Basic authentication (BA) implementation is the simplest technique for enforcing access controls to web resources because it does not require cookies, session identifiers, or login pages; rather, HTTP Basic authentication uses standard fields in the HTTP header.   
- Security:   
The BA mechanism does not provide confidentiality protection for the transmitted credentials. They are merely encoded with Base64 in transit and not encrypted or hashed in any way. Therefore, basic authentication is typically used in conjunction with HTTPS to provide confidentiality.

- Protocol: 
1. Server side  : When the server wants the user agent to authenticate itself towards the server after receiving an unauthenticated request, it must send a response with a HTTP 401 Unauthorized status line and a WWW-Authenticate header field.     

2. Client side :When the user agent wants to send authentication credentials to the server, it may use the Authorization header field.

## OWASP auth cheatsheet   
Session Management is a process by which a server maintains the state of an entity interacting with it.     


**Authentication Solution** and Sensitive Accounts¶
Do NOT allow login with sensitive accounts (i.e. accounts that can be used internally within the solution such as to a back-end / middle-ware / DB) to any front-end user-interface      

Do NOT use the same authentication solution (e.g. IDP / AD) used internally for unsecured access (e.g. public access / DMZ)       



**Implement Proper Password Strength Controls**
1. Password Length:  Minimum length of the passwords should be enforced by the application     

   Maximum password length should not be set too low, as it will prevent users from creating passphrases
2. Implement Secure Password Recovery Mechanism
3. Store Passwords in a Secure Fashion.
4. Compare Password Hashes Using Safe Functions 

## bcrypt docs

A library to help you hash passwords.    
to see the all commands follow this link 
 [node.bcrypt.js](https://www.npmjs.com/package/bcrypt)


# sreources

[Securing Passwords](https://thehackernews.com/2014/04/securing-passwords-with-bcrypt-hashing.html)    

[Basic Auth](https://en.wikipedia.org/wiki/Basic_access_authentication)

[OWASP auth cheatsheet](https://cheatsheetseries.owasp.org/cheatsheets/Authentication_Cheat_Sheet.html) 

