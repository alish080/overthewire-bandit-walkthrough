### Level4 → Level5

### Goal

The password for the next level is stored in the only human-readable file in the inhere directory
----------------------------------------------------------------------------------
> Connect first: ssh bandit4.bandit@labs.overthewire.org -p 2220

> Must be correct home directory `/home/bandit4`

### Command
**Run** `ls`
- you will see inhere directory

**Run** `cd /inhere`
- you are now inside inhere directory

**Run** `ls -a`
- you will see bunch of files

***1st method***
> you can  keep doing `cat ./-file00` to `cat ./-file09` 
and you will find the key in `cat ./-file07`

***2nd method***
> we will use grep commadan ***grep is a command-line tool used to search for specific text or patterns within files and print the matching lines***

***Run***
`grep -a "" ./-file*`

- `-a` treats binary files as text
- "" shows every content inside file
- `./file*` means all file starting from -file
> means it searches all the files `./-file*` and shows the connnet of files treating everything as a text
-----------------------------------------------------------------------------
### NOTE:
> Please store the key for the next level in text editor
-----------------------------------------------------------------------------
***Alish***

