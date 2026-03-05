### Level6 → Level7

### Goal
The password for the next level is stored somewhere on the server and has all of the following properties:

    owned by user bandit7
    owned by group bandit6
    33 bytes in size

----------------------------------------------------------------------------
> Connect first: ssh bandit6@bandit.labs.overthewire.org -p 2220
> Make sure you are in correct directory **Run** `pwd` if you see `/home/bandit6` you are in current directory
---
## Important concept before moving to Commands

*owned by user:*
- owned by user means user who created it, who has the power to read/write/append anything.

**owned by group:**
-owned by group mean a group has a power to only read a certain  files

***For Example***
Imagine  a file name buget.xlsx
- user owner : Jhon (He can read/ write the file)
- group owner : Finance team (Every one on the team can read not write them)

----
### Command

> See the hints provided in the goal
`find / -user bandit7 -group -bandit6 -size 33c 2>/dev/null`

so basically  we  are told that passwd is store somewhere on the server so we choose the path  `/` 
And, the user owner was bandit7
the group owner was bandit 6

- 2>/dev/null
2> is the standard error we get searching whole "root" server there is a huge chance we will get error message like "permisssion denied and other gebberish code so we send them to /dev/null basically discard them anything that goes on /dev/null the error code is discarded
so now you will get `/var/lib/dpkg/info/bandit7.password`
Now,

**Run**
`cat /var/lib/dpkg/info/bandit7.password`
you will get your key 
---
### NOTE
>Please store the key on your text editor
---
***Alish***
