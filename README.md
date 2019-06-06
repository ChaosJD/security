# security

## OWASP1 Injection
* Input Snitization: escaping or removing Metacharacters  
* Blacklisting: only unwanted characters in input are escaped / removed     //unsafe, more common
* Whitelisting: only entries with permitted characters are allowed          //safer, less common
* Framework: **LdapQueryBuilder in Spring-LDAP**

## OWASP 7 Cross-Site-Scripting(Xss)
* is a Metacharacter Problem  
  by html coding solvable  
  
* Filtering at the time of issue  
  user-generated inputs  
  dates of files, databases or other external sources  
  
* Three variants  
  **No** markup in files: html encoding before handover to client  
  user may use restricted markup  
  user has full confidence: no special treatment, but no security  
  
* further aspects
  Separation of code and layout  
  set Browser charset: ISO 8859-1  
  
### Selektive Tag-Filterung

* Separation of good and bad code  
  bad tags: script, javascript, onClick  
  
* Possible Algorithm  
  delete all tags that are not the good ones  
  delete all Attributs  
  remove all tags that do not belong to the good ones  
  join all attributes that are not good for the current tag  
  remove all attributes whose values do not belong to the good ones for the current tag and attribute.  
  
## OWASP 8 XSRF
*  Pattern: **Synchronizer Token Pattern**  
   server generates "challenge" token
   this is embedded in the delivered page
   request of sensitive actions must include "challenge" token
   challenge token in the request must be checked on the server before executing the action.

# secure Programming with Components

## Trust Boundaries

![TrustBoundaries](./pics/SecureProgrammingWithComponents.svg)

### Kanonisierung
* check namew with regular expressions
* only long datafilename
* point @ the end away
* **absolute** path

#### Where to check
* user inputs
* transfer of parameters
* access to system ressources

### Validation
* build domaintypes ( e-mail, account, date, customer-ID)
* validation before any other task
* Carry out authorization together with validation
* Whitelist 
* Never use client-side validation as the only basis for decision making for example javaScript

## Use Data-Indirektion
* Keep important data as far as possible on the server
* incoming data ar not destination data
* incoming data is not the target data but only to search the target data geeginet  
    accountnumber, price of a product via customer number or referent with article number
    
## serverside gernerated data
safe inut with cryptographic hash function(MAC) or encoding

## Metasign Problems
<dl>
  <dt> Metasign </dt>
  </dd> When submitting data to a subsystem, they convert from a text character to a control character</dd>
</dl>
