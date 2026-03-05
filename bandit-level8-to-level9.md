### Level8 → Level9

### Goal
- The password for the next level is stored in the file data.txt and is the only line of text that occurs only once.
---

### Important concept in this lab 
- `sort`:This command sorts the lines of data.txt lexicographically so that all identical lines are adjacent. This step is essential because uniq only detects and operates on adjacent duplicate lines.
-  `uniq`: command filters out adjacent duplicate lines to show one of each,
- `-u` : only shows the line that appears exactly once.

### Command

**Run**
`ls` 
- you will see "data.txt" file  
> there are many lines inside the file many of them are dulpicate 

**Run*
`sort data.txt |uniq -u`
> If you just do `sort data.txt |uniq` then you will get other line which looks like key , but as we know `uniq` removes the duplicate but keeps one as a represtative 

So, **Correct command is**
`sort data.txt |uniq -u` 
----
###NOTE
>Please store the passwd of next levl at you text edito
---
***Alish***
