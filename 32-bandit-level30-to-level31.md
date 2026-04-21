### Level 30 > Level 31

### Goal 
There is a git repository at ssh://bandit30-git@bandit.labs.overthewire.org/home/bandit30-git/repo via the port 2220. The password for the user bandit30-git is the same as for the user bandit30.

### Walkthrough 

Again the cloneing part is same as the prevoius level so nothing new 

1. make a seperate folder i.e'level30git' in your localmachine

Now,

***Run***

`git clone ssh://bandit30-git@bandit.labs.overthewire.org:2220/home/bandit30-git/repo`

now the repo will be cloned in you folder

now,
`ls`

`cd repo`

you will see a 'README.md'

`cat README.md`
you will see a text 
> just an epmty file... muahaha
 
so the file is empty but so we know we looked at the git log right we will see log

`git log --oneline --all`

there is not much too see so our next thing will be looking at the branch 

---

  remotes/origin/HEAD -> origin/master
  remotes/origin/master

---

so no hidden branch as we can see so now another thing is dev might delete the commit but forget the 'tag'

Sometimes a developer deletes a secret in the main code but forgets that a "Tag" still points to the old version where the secret exists.

`git tag`

you will see a 'secret'

`git show secret`

you will get you password

- fb5S2xb7bRyFmAvQYQGEqsbhVyJqhnDy
---
***Alish*** 
 
