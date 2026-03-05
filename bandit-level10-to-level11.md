### Level 10 → Level 11

### Goal
The password for the next level is stored in the file data.txt, which contains base64 encoded data.
----

### Important
-` base64`: command is used for encoding and decoding data, which is standard on most distributions. This command converts binary data into printable ASCII text format, often for transmission over text-based channels like email
- `-d`: is used to decode 
---

### Command
**Run** `ls`
- you will see "data.txt"

**Run** `cat data.txt`
- you will get the binary data which we have to decode it to ASCII text

**Run**
`echo -n "VGhlIHBhc3N3b3JkIGlzIGR0UjE3M2ZaS2IwUlJzREZTR3NnMlJX | base64 -d`
> `-n` When we use echo to print a string, it automatically adds a hidden "newline" character (\n) to the very end so your terminal prompt starts on a new line.
- **For example**
Base64 is very sensitive. It encodes every single bit you give it.
    echo "hello" | base64 
    
    With the Newline:
    You are actually sending h + e + l + l + o + [Invisible Newline] to the base64 tool.
    The K you see in aGVsbG8K is the Base64 version of that invisible "Enter" key.
    
    echo "hello"| base64
    Without the Newline (-n):
    You are sending only h + e + l + l + o.
    The = you see in aGVsbG8= is just "padding" to make the math work out for the 5 letters.
-----
### Note
> Please store the passwd in your text editor
---
***Alish***

