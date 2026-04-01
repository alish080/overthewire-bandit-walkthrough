### Level19 > Level20

### Goal 
To gain access to the next level, you should use the setuid binary in the homedirectory. Execute it without arguments to find out how to use it. The password for this level can be found in the usual place (/etc/bandit_pass), after you have used the setuid binary.

**First let's understand how will be solve it**
> here  we will deal with setuid when you log into a server bandit19 and run `ls` you will see a file which is 'setuid' and what we will do is the password of level 20 can be accesed by this file

**Important concept **
- `setuid`: setuid is a special permisssion command in linux/unix that allows the executable file to act as the owner
FOR Example : we have a file "bandit20-do" this is setuid file that means even when you are user bandit19 you will be able to acces the password of level20 which means bandit20-do acts as the owner

### Command

**Run**
`ls -la`
you  wills see 
> -rwsr-x---   1 bandit20 bandit19 14884 Oct 14 09:26 bandit20-do

to indetify the file if it has setuid or not you will have to look at the permission in above output, you can see 's' which means it has setuid enabled.
Now,

`./bandit20-do cat /etc/bandit_pass/bandit20`
- you will get your passwd for next level

> 'bandit20-do allows up to acces the passwd of level 20 cause it is etuid file and acts as a owner'
> Even though you are logged in as bandit19, the setuid bit (s) on bandit20-do allows you to execute commands with the privileges of the file's owner, bandit20.
passwd for next level 
> 0qXahG8ZjOVMN9Ghs7iOWsCfZyXOUbYO
---
***Alish***



