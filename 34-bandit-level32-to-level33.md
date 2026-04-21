### Level 32 > 33

### Goal
After all this git stuff, it’s time for another escape. Good luck!

### Walkthrough 

log in first to level32

`ssh bandit32@bandit.labs.overthewire.org -p 2220`

> you are trapped in a "restricted shell" that acts like a filter. Whatever you type, it converts to uppercase before executing it.

> In Linux shells (like Bash or Sh), there are special variables called Positional Parameters. These are symbols like $0, $1, $2, etc.

-    $1 usually refers to the first argument given to a script.

-   $0 is a very special variable. It refers to the name of the program currently running.

> When you log in, what program is running? A shell. If you type $0 and hit enter:

1.    The restricted shell looks at $0.

2.     It sees that $0 represents the shell itself (usually /bin/sh or similar).

3.     Because $0 is a symbol, it cannot be converted to uppercase. It stays $0.

4.     The system executes $0, which basically means it starts a new, fresh version of the shell.

so NOW, 

as you log in just do,

`$0` : it will open a new script where the case rule won't apply

`ls`
you will se a 
- `uppershell` : this is a setuid permission file so 

> NOTE: In Bandit 27: When you logged in, you were given a normal shell. You had a $ prompt and could type lowercase commands. However, you didn't have permission to read the password file. You had to use ./bandit27-do like a "key" to open that specific file.

> In Bandit 32: When you logged in, you were not given a normal shell. The system automatically put you inside the uppershell program. You were "trapped" inside the program from the very first second.

`cat /etc/bandit_pass/bandit33`

you will get password 
> tQdtbs5D5i2vJwkO8mEyYEyTL8izoeJ0
---
***Alish***
