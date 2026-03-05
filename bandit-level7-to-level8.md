### Level7  Level8

### Goal
The password for the next level is stored in the file data.txt next to the word millionth
---

### Important Concept

> To search the word in a file we know we use command `grep` 
> To, correctly find the correct word  we have to use flags
 - `-i`: ignore the case sensitivity (e.g "Watch" "watch")
 - `-n`: shows the line number where the words was matched
 - `-r`: recursively search through all the files in current directory and its subdirectories
 - `-l`: only shows the filename the word is matched and not the line 

### Command

**Run** `ls`
 - you will see a file named "data.txt"

*If you run*  `ls data.txt`
- you will see thousand of files 
 
Now,
**Run**
`grep -in "millionth" data.txt`

- "millionth": is a word we are searching for our passwd is nect to this word
- data.txt : is the files we are searching at 
> Now, we can see key for our level
----
### Note
> Please store the key at your text editor
---
***Alish***
