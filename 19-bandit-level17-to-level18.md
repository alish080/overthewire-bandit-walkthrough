### Level 17 > Level 18

### Goal
There are 2 files in the homedirectory: passwords.old and passwords.new. The password for the next level is in passwords.new and is the only line that has been changed between passwords.old and passwords.new

### Command
First log into bandit17 first then,

**Run** 
`ls`
> you will see a two files "passwords.old" and "passwords.new"

now if you do,
`cat passwords.old` and `cat passwords.new`

You will see a bunch of key which are identical to keys in passwords.new and passwords.old

Now, if we look at a goal;  it is said that the password is in password.new and is the only line that has been changed between paswords.new and passwords.old so we use now new command that is `diff`
---
**Run**
`diff passwords.new passwords.old`

- Output
42c42
- < x2gLTTjFwMOhQ8oWNbMN362QKxfRqGlO

- > pGozC8kOHLkBMOaL0ICPvLV1IjQ5F1VA

Here,

42c42 means
- 42 : means the line where the operation has done
- 'c' : means changed
- 'a' : means add
- 'd' : means delete
- '>' : indicates  lines from second file
- '<' : indicates lines from first line 
---
So our passwd is 'x2gLTTjFwMOhQ8oWNbMN362QKxfRqGlO'
---
***Alish*** 

