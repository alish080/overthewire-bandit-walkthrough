### Level 12 →  Level 13

### Goal

The password for the next level is stored in the file data.txt, which is a hexdump of a file that has been repeatedly compressed. For this level it may be useful to create a directory under /tmp in which you can work. Use mkdir with a hard to guess directory name. Or better, use the command “mktemp -d”. Then copy the datafile using cp, and rename it using mv.
---
### Inmportant Concept 
**Hex dump**
Normally, when you open a file (like a photo, a program, or a corrupted document) in a text editor, you’ll just see a mess of weird symbols and gibberish. This is because those files aren't meant to be read as text.
We use hexdump to:

-  See the "Raw" Data: It shows you the exact 0s and 1s of a file, but translated into Hexadecimal (0-9 and A-F) so it’s easier for humans to read than binary.
-  Fix Corrupted Files: If a file won't open, you can use hexdump to see if the "header" (the beginning of the file that tells the computer what it is) is broken.

The Bandit level tells you the file was compressed multiple times.

Meaning the process looks like this:

Original file
   ↓ compress
gzip
   ↓ compress
bzip2
   ↓ compress
tar
   ↓ convert to hex
data.txt

So you must reverse the process step-by-step.

### Command 
**RUN**
> CREATE A TMP DIRECTORY SO THAT SO YOU CAN EXPERIMENT THE FILE WITHOUT ANY WORRIY OF BREAKING OTHER INPORTANT FILES IN A HOME DIRECTORY
 `mktemp -d`
 `/tmp/tmp.NYsEzZGNlS`

**Run**
`cd /tmp/tmp.NYsEzZGNlS`

> copy the data.txt file of home directory to current tmp directory
`cp ~/data.txt .`

**Run**
`ls`
- you will see "data" "data.txt"

> Now, This is the "hexdump" we have to conver it to binary 
`xxd -r data.txt > data`
> see the file type

Identify what type of file it is

Example output:

gzip compressed data

or

bzip2 compressed data

or

POSIX tar archive

**Run**
`file data`
- you see something like "data: gzip compressed data, was "data2.bin", last modified: Tue Oct 14 09:26:00 2025, max compression, from Unix, original size modulo 2^32 572"

> means that file is compreed by gzip, we need to decomprees it 
> we will have to move the file into a correct extension because compressor won't know which file to decompress 

bandit12@bandit:/tmp/tmp.NYsEzZGNlS$ `mv data data.gz`
bandit12@bandit:/tmp/tmp.NYsEzZGNlS$ `gzip -d data.gz`

> see the file tine decomprees it  until you can see the password

`ls`
- data  data.txt

bandit12@bandit:/tmp/tmp.NYsEzZGNlS$ `file data`
data: bzip2 compressed data, block size = 900k

bandit12@bandit:/tmp/tmp.NYsEzZGNlS$ `mv data data.bz2`
bandit12@bandit:/tmp/tmp.NYsEzZGNlS$ `bzip2 -d data.bz2` 
bandit12@bandit:/tmp/tmp.NYsEzZGNlS$ `ls`
- data  data.txt
bandit12@bandit:/tmp/tmp.NYsEzZGNlS$ `file data`
data: gzip compressed data, was "data4.bin", last modified: Tue Oct 14 09:26:00 2025, max compression, from Unix, original size modulo 2^32 20480
 
bandit12@bandit:/tmp/tmp.bRfLLnOzjf$ `mv data data.gz`
bandit12@bandit:/tmp/tmp.bRfLLnOzjf$ `gzip -d data.gz` 
bandit12@bandit:/tmp/tmp.bRfLLnOzjf$ `file data`
data: POSIX tar archive (GNU)

bandit12@bandit:/tmp/tmp.bRfLLnOzjf$ `tar -xf data`
bandit12@bandit:/tmp/tmp.bRfLLnOzjf$ `ls`
data  data5.bin  data.txt

bandit12@bandit:/tmp/tmp.NYsEzZGNlS$ `file data5.bin` 
data5.bin: POSIX tar archive (GNU)

bandit12@bandit:/tmp/tmp.NYsEzZGNlS$ `tar -xf data5.bin`
bandit12@bandit:/tmp/tmp.NYsEzZGNlS$ `ls`
data  data5.bin  data6.bin  data.txt
bandit12@bandit:/tmp/tmp.NYsEzZGNlS$ `file data6.bin` 
data6.bin: bzip2 compressed data, block size = 900k

bandit12@bandit:/tmp/tmp.NYsEzZGNlS$ `mv data6.bin data6.bz2`
bandit12@bandit:/tmp/tmp.NYsEzZGNlS$` bzip2 -d data6.bz2` 
bandit12@bandit:/tmp/tmp.NYsEzZGNlS$ `ls`
data  data5.bin  data6  data.txt
bandit12@bandit:/tmp/tmp.NYsEzZGNlS$ `file data6`
data6: POSIX tar archive (GNU)
bandit12@bandit:/tmp/tmp.NYsEzZGNlS$ `tar -xf data6`
bandit12@bandit:/tmp/tmp.NYsEzZGNlS$ `ls`
data  data5.bin  data6  data8.bin  data.txt
bandit12@bandit:/tmp/tmp.NYsEzZGNlS$ `file data8.bin` 
data8.bin: gzip compressed data, was "data9.bin", last modified: Tue Oct 14 09:26:00 2025, max compression, from Unix, original size modulo 2^32 49

bandit12@bandit:/tmp/tmp.NYsEzZGNlS$ `mv data8.bin data8.gz`
bandit12@bandit:/tmp/tmp.NYsEzZGNlS$ `gzip -d data8.gz` 
bandit12@bandit:/tmp/tmp.NYsEzZGNlS$ `ls`
data  data5.bin  data6  data8  data.txt
bandit12@bandit:/tmp/tmp.NYsEzZGNlS$ `file data8`
data8: ASCII text
bandit12@bandit:/tmp/tmp.NYsEzZGNlS$ `cat data8`
The password is FO5dwFsc0cbaIiH0h8J2eUks2vdTDwAn

> We need to remove the "tmp" directory,it is a good practice (it is not a complassary)
> exit the tmp directory first

`ls -d /tmp/tmp.NYsEzZGNlS`
`/tmp/tmp.NYsEzZGNlS`
bandit12@bandit:~$ `cd /tmp/`
bandit12@bandit:/tmp$ `rm -r tmp.NYsEzZGNlS`
bandit12@bandit:/tmp$ `ls -d /tmp/`
`/tmp/`
bandit12@bandit:/tmp$ `ls -d /tmp/tmp.NYsEzZGNlS`
ls: cannot access '/tmp/tmp.NYsEzZGNlS': No such file or directory
bandit12@bandit:/tmp$ `exit`
---

### NOTE:
> Please store the key on your text editor
---
***Alish***


