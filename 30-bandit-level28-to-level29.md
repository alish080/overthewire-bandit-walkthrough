### Level 28 > Level 29

### Goal 
There is a git repository at ssh://bandit28-git@bandit.labs.overthewire.org/home/bandit28-git/repo via the port 2220. The password for the user bandit28-git is the same as for the user bandit28.

## Walkthrough

The process is same for this level too


> Make a seperate folder like a "level28git"a and go to that directory.

Just clone the repo 

`git clone  ssh://bandit28-git@bandit.labs.overthewire.org:2220/home/bandit28-git/repo`

the repo will we clone on your folder now see what is cloned

**Run**
`ls`

you will see a 'repo' folder in you directory that you created

`cd repo`
`ls`

you will see a file README.md

`cat README.md`

you will something like 

---

# Bandit Notes
Some notes for level29 of bandit.

## credentials

- username: bandit29
- password: xxxxxxxxxx

---

so the password is not in a file you wil have to look as the commit history 

`git log --online -all`

you will see,
----

00daa61 (HEAD -> master, origin/master, origin/HEAD) fix info leak
a1487fd add missing data
eaef76e initial commit of README.md

---

so see a particular commit the alphanumerical valuse you see is a commit id

**RUN**
`git show a1487fd`

you will get you passowrd for next level

> 4pT1t5DENaYuqnqvadYs1oE4QLCdjmJ7

---
***Alish**

