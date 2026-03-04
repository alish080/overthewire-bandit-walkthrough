### Level2 &raww; level3

### Goal
The password is in --space in this filename-- located at the home directory.

### Problem 
Like in a previous level the file is starting from `--` so the linux won't think
of it as a file, it'll think of it as a option 

So, we have to make our linux think that `--space in this filename--`  is a
filename and not a option

## Command 
**Run**
`ls`
you will see `--space in this filename`

Now,
**Run**
`cat ./--space\in\this\filename--`

Here we use **`\`(Escape the space)** ,
If we don't use `\` linux will think space in this are seperate so,
>inorder, to show that `--space in this filename--` is a single file we use `\`.

### NOTE:
> USE ./ when file name starts with `-`,`--`,`...`

> Please store the key for another level on text editor
----------------------------------------------------------------------------
**Alish**
