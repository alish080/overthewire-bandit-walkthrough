### Goal 

The credentials for the next level can be retrieved by submitting the password of the current level to a port on localhost in the range 31000 to 32000. First find out which of these ports have a server listening on them. Then find out which of those speak SSL/TLS and which don’t. There is only 1 server that will give the next credentials, the others will simply send back to you whatever you send to it.

### Command

**log into bandit16 first**
`ssh bandit16@bandit.labs.overthewire.org -p 2220`
- paste the passwd that we got in level 15

Once you are loged in,

See, first which server is actually listening

`nmap -Sv -p 31000-32000 localhost`

you will see 5 ports with servies like "ssh\echo","echo","ssh/unknown"

> echo means whatever input you give it will give you exact input as output 
> ssh\echo is also same as echo 
> ssh\unknown is more suspecious so we are  gonna take  ssh\unknown port

now lets check  what is inside the port 

**Run**
`openssl s_client -connect localhost:31790`

now you see a RSA private key 
> copy that private key from ----begin to --end whole on your local machine for good practice make a seperate folder and insert the key on filename.key
> when you do file filename you must see "PEM RSA private key"

> there the filename is bandit17.key

now,
connect to bandit17 server cause you have a private RSA key file

`ssh -i bandit17.key bandiy17.labs.overthewire.org -p 2220`

You now have loged into a bandit17 server check by doing `pwd`

now to get the passwd
`cat /etc/bandit_pass/bandit17`

you will get a passwd of bandit 17

>EReVavePLFHtFlFsjn3hyzMlvSuSAcRD

---
Alish 


