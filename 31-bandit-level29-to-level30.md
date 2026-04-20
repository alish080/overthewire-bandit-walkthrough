### Level 29 > Level 30

### Goal

There is a git repository at ssh://bandit29-git@bandit.labs.overthewire.org/home/bandit29-git/repo via the port 2220. The password for the user bandit29-git is the same as for the user bandit29.

### Walkthrough 

First make a folder like 'level29git' and go to that dir and clone the repo given in a goal

`git clone There is a git repository at ssh://bandit29-git@bandit.labs.overthewire.org:2220/home/bandit29-git/repo`

Now the repo is cloned to you folder now 

`ls`

you will find a 'repo' folder cloned 

`cd repo`
`ls`

you will see a README.md file

`cat README.md` 

you will see a '<no password in production>' so we have to look at the commit history

`git log --oneline --all`

you will see a bunch of things commited, one of them is somthing like 

 <4a8f414 (origin/dev) add data needed for development>

now,

`git show 4a8f414`

you will get password of level30

> qp30ex3VLz5MDG1n91YowTv4Q8l7CDZL
---
***Alish***

