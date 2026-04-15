### Level 25 > Level 28

### Goal 
Logging in to bandit26 from bandit25 should be fairly easy… The shell for user bandit26 is not /bin/bash, but something else. Find out what it is, how it works and how to break out of it.

### Walkthrough 

First let's understand the goal the shell `/bin/bash` was used as default but in our bandit26 is different we must look atit and change it to the default  shell so first,

Log into the "ssh bandit25" server,

As, you are loged in type

**Run**
`ls`

you will see a `bandit26.sshkey` so this is the PEA key the same file which we have deal with in previous level.

so, as the dev have blocked the localhost connection which previously if we ran is blocked you can't log in form bandit25 to bandit26 but see if it works for you, 

`bandit -i bandit26.sshkey bandit26@localhost`

If this command is not working then it's totally fine just follow the folloing steps,

1. open a new terminal in you machine and make a folder for example i will name it "bandit26"

`mkdir bandit26`

2. now go to the previous terminal whereyou are loged in as a 'bandit25' and read the 'bandit26.sshekey' and paste in a new file `bandit26.sshkey` into that folder we just made in our machine

3. now go to the same terminal where you are loged in as bandit25 and let's see what shell 'bandit26' is using, you will see 

`bandit26:x:11026:11026:bandit level 26:/home/bandit26:/usr/bin/showtext`

so as you can see the shell used by bandit26 is "/usr/bin/showtext" we must change it to '/bin/bash'

4. first let's see what kind of shell it is,

`cat /usr/bin/showtext`

you will see,
---
#!/bin/sh

export TERM=linux

exec more ~/text.txt
exit 0
---

so here you can see the script the see is using is 'more command' and plus the 'exec' command is used as well we know that when 'exec' is used it not only use the command with it it takes full control of it as we can see here the 'more' command is used and whole script is control by more

`more` : is a text viewer , it stops when the text reach the end and if the text is large then then then window then it automatically stop and we are gonna expolit it

we are gona use `vim` command 

`vim`: is the powerfull texteditor where we are gona change the shell 

5. as you do connection from your machine 

`ssh -i bandit26.sshkey bandit26@bandit.labs.overthewire.org -p 2220`

now srink your window of a terminal what more command does is it pauses the text and we can make a edit so now enter the command which was above

and press `v` and `:`

and you are now in editor mode 

and now perform,

`:set shell=/bin/bash`
and press enter

`:shell`
press enter

now you will be loged in as a bandit26

**Run**
`cat /etc/bandit_pass/bandit26`

> s0773xxkk0MXfdqOfPRVr9L3jJBUOgCZ

---
**ALISH**



