# Bearer Authorization

 **What is JSON Web Token?**   
 JSON Web Token (JWT) is an open standard (RFC 7519) for securely transmitting information between parties as JSON object.

 **When should you use JSON Web Tokens?**       

 1. Authorization:  most common scenario for using JWT. Once the user is logged in, each subsequent request will include the JWT, allowing the user to access routes, services, and resources that are permitted with that token. 

2. Information Exchange: JSON Web Tokens are a good way of securely transmitting information between parties. 

**JSON Web Token structure**  

A JSON Web Token consists of 3 parts separated by a period.

``` header.payload.signature ``` 

![pic](https://19yw4b240vb03ws8qm25h366-wpengine.netdna-ssl.com/wp-content/uploads/Why-Cant-I-Just-Send-JWTs-Without-OAuth-JWT-278x300.png)


1. **_Header_**    
JWT header consists of token type and algorithm used for signing and encoding. Algorithms can be HMAC, SHA256, RSA, HS256 or RS256.  

``` 
  {
    "typ": "JWT",    
  "alg": "HS256"
  }
 ```

 2. **Payload**   
 contains the claims. Claims are statements about an entity (typically, the user) and additional data.   
  There are three types of claims: 
  
  
  - registered  
   These are a set of predefined claims which are not mandatory but recommended, to provide a set of useful, interoperable claims. Some of them are: iss (issuer), exp (expiration time), sub (subject), aud (audience), and others.
  
  
  - _public_    
   hese can be defined at will by those using JWTs. But to avoid collisions they should be defined in the IANA JSON Web Token Registry or be defined as a URI that contains a collision resistant namespace.
  
  


  
  - private claims   
  These are the custom claims created to share information between parties that agree on using them and are neither registered or public claims. 


  An example payload could be:

  ``` 
  {
  "sub": "1234567890",
  "name": "John Doe",
  "admin": true
}
```
3. **Signature**  
To create the signature part you have to take the encoded header, the encoded payload, a secret, the algorithm specified in the header, and sign that.

For example if you want to use the   HMAC SHA256 algorithm, the signature will be created in the following way:

```
HMACSHA256(
  base64UrlEncode(header) + "." +
  base64UrlEncode(payload),
  secret)
  ```
The signature is used to verify the message wasn't changed along the way, and, in the case of tokens signed with a private key, it can also verify that the sender of the JWT is who it says it is.    


**How it works?**

Basically the identity provider(IdP) generates a JWT certifying user identity and Resource server decodes and verifies the authenticity of the token using secret salt / public key.

1. User sign-in using username and password or google/facebook.   

2. Authentication server verifies the credentials and issues a jwt signed using either a secret salt or a private key.   

3. User’s Client uses the JWT to access protected resources by passing the JWT in HTTP Authorization header.    

4. Resource server then verifies the authenticity of the token using the secret salt/ public key.    



![pic](https://cdn2.auth0.com/docs/media/articles/api-auth/client-credentials-grant.png)



# Install
``` 
$ npm install jsonwebtoken 
```
## resourses
1. [JWTs Explained](https://www.youtube.com/watch?v=926mknSW9Lo)

2. [Intro to JWT](https://jwt.io/introduction)   

3.[npm jsonwebtoken docs](https://www.npmjs.com/package/jsonwebtoken)