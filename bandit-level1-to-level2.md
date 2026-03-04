## Level 1 → Level 2

###  Goal
The password is stored in a file named `-`.

> ***Check the directory first***
- you must see `/home/bandit1`

### 🧠 Problem
The filename `-` is special in Linux.
So, you cant read a `-` file by using a cat command as we know `-` is a special file 
We have to make `-` operate a normal file 

### 💻 Command Used
```bash
ls

cat ./-
```
- `ls` when you do ls you see a `-` file
 
- You will make a `-` file as a normal file, for now we will do 

`cat ./` 
- . means current directory 
- ./ means the file name - inside this directory

## Example
cat ./-          # reads the file named '-' in current directory

cat ./--file     # reads the file named '--file' in current directory

- Now you will see a passwd for next level

***NOTE: Please store you key on text editor***
-----------------------------------------------------------------------------
*Alish*
