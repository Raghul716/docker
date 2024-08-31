YAML File Overview.
YAML files are composed of maps and lists.
Indentation matters (be consistent)
Always use spaces

Syntax of YAML
Basic syntax
Key value pairs

#example 1: Key value pairs  
app: user-authentication
port: 9000
version: 1.7

#example 2: Objects
microservice:
 app: user-authentication
 port: 9000
 version: 1.7

#example 3: Lists
 microservices:
  - app: user-authentication
    port: 9000
    version: 1.7
  - app: shopping-cart
    port: 9001
    version: 1.-

#example 4: Booleans
microservices:
 - app: user-authentication
   port: 9000
   version: 1.7
   deployed: false
