### Level 22 > Level 23

#### Goal 
A program is running automatically at regular intervals from cron, the time-based job scheduler. Look in /etc/cron.d/ for the configuration and see what command is being executed.

NOTE: Looking at shell scripts written by other people is a very useful skill. The script for this level is intentionally made easy to read. If you are having problems understanding what it does, try executing it to see the debug information it prints.

### Walthrough 

The process is same as level 21 as the script is in cron `etc/cron.d` 
This time we are searching the password of level 23 as being a user bandit22

As, you run

***Run***

`cat cronjob_bandit23`

you will see a script that us written by the developer

### Understaning the script
--
#!/bin/bash
myname=$(whoami)

mytarget=$(echo I am user $myname | md5sum | cut -d ' ' -f 1)

echo "Copying passwordfile /etc/bandit_pass/$myname to /tmp/$mytarget"
cat /etc/bandit_pass/$myname > /tmp/$mytarget

--
- The output of the whoami is the bandit23 as bandit23 is running the shell script and being stored in a `my target` 
- The seconf line of code is the destination basically prnting the output of bandit23 being sumed by md5 and the field of output is being stored in a `mytarget`
- The third line  refres to sending the password of bandit23 to `/tmp/mytarget`
- so the password is stored in a "/tmp/mytarget"

> You will have to find the value of "mytarget", you can't directly  run mytarget as it's  object 

**Run**

`echo I am user bandit23 | md5sum | cut -d ' ' -f 1`
you will get, 

8ca319486bfbbc3663ea0fbe81326349
 
so now just simply,

`cat /tmp/8ca319486bfbbc3663ea0fbe81326349`

you will get a password for next level,


- 0Zf11ioIjMVN551jX3CmStKLYqjk54Ga

---
***Alish***
