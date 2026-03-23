### Goal 

The password for the next level can be retrieved by submitting the password of the current level to port 30001 on localhost using SSL/TLS encryption.

> We won't just send a raw key now we will send a key encrypted with SSL/TLS, we will use openssl tool to communicate wirh SSL/TLS port.

> If you try to use nc (Netcat) like you did in the previous level, it will fail because nc sends "raw" text. The server at port 30001 is expecting a secure handshake first.

### Command 

We will have to send a current passwd to a server 30001 encrypted with SSL/TLS 

`openssl s_client -connect localhost:30001`

- `s_client` - is to tell the server we are a client and requsting a service
- `-connect localhost:30001`- is a destinated server to send

you will receive a correct passwd now 

kSkvUpMQ7lBYyCM4GBPvCvT1BfWRy0Dx  
--- 
***Alish**
