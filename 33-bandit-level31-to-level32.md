### Level 31 > Level 33


### Goal

There is a git repository at ssh://bandit31-git@bandit.labs.overthewire.org/home/bandit31-git/repo via the port 2220. The password for the user bandit31-git is the same as for the user bandit31.

### Walkthrough 

THe same way we cloned the repo like we always do,

1. make a folder like 'level31git' and ,

`git clone ssh://bandit31-git@bandit.labs.overthewire.org:2220/home/bandit31-git/repo`

the repo will be cloned to your folder now,

`ls`

repo will  be there 

`cd repo`
`ls`

you will see a 'README.md' file, let's read it

`cat README.md`

you will see

---

This time your task is to push a file to the remote repository.

Details:
    File name: key.txt
    Content: 'May I come in?'
    Branch: master

----

here you have to send the content to taht file name key.txt

`echo "May I come in?" > key.txt

now,

`git add -f key.txt`
`git commit -m "added the requested key.txt"`
`git push orign master`

once you push will get a password as you read down,

> 3O9RfhqyAlVBEZpVb6LYStshZoqoSx5K
---

***Alish***
