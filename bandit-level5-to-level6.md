### level5 → Level6

### Goal
The password for the next level is stored in a file somewhere under the inhere directory and has all of the following properties:

    human-readable
    1033 bytes in size
    not executable
----------------------------------------------------------------------------
> Check first: ssh bandit5@bandit.labs.overthewire.org -p 2220

> Must check whether you are in correct  dirctory  ***Run**`pwd` you must see `/home/bandit5`

### Command
**Run**  `ls`
- you will see inhere directory

**Run** `cd inhere/`
- you are inside inhere direcory

- now do `ls -a` you will see folder like `maybehere00` to `maybehere19`
>these all are folders
> So, grep will not be useful and cat can't read beause cat only can read fils not folders

***Now lets solve it***

**First**
**Run**
`cd ~ `
- this is used to go the home directory

Now,
**Run**
`find ./inhere -type f -size 1033c -exec file {} \; | grep"ASCII text"`

**explanation of command**
- `./inhere` - starts the search in inhere directory
- `-type f`  - only search for files ignore directory
- `-size 1033c`- looks for files exactly 1033 bytes `c` means byte 
- `-exec` - exec tells find: “For each file you find, run this command on it.” The command can be anything executable, including ls, cat, or file. {} → placeholder for the current file found \; → ends the command
- `file` - file is a linux command that examines the files and tell you the type
- `grep "ASCII text` - Finally, take the output of all those file commands and only show the lines that contain the words "ASCII text."
------------------------------------------------------------------------------
###NOTE
> Please store the key on your text editor
-----------------------------------------------------------------------------
***Alish***
