### Level3→ Level4

### Goal

The password for the next level is stored in a inhere directory
------------------------------------------------------------------------------
> Connect first :ssh bandit3@bandit.labs.overthewire.org -p 2220 and passwd you got at previous level
> see you are at the correct home directory you must see `/home/bandit3`

### Command
**Run**
`ls`
- you will see a inhere directory
- you will have to change the directory so use command `cd`
- once you use `cd inhere` 

>Run `ls -a` it will show you all the file inside inhere directoy one of them is ...Hiding-From-You

Now
**Run**
`cat ./...Hiding-From-You`

You will see the passwd for the next level

###NOTE
>Please store the passwd that you get in a text editor
-----------------------------------------------------------------------------
***Alish***
 

