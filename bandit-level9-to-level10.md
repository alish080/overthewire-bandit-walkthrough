### Level9 → Level10

### Goal
The password for the next level is stored in the file data.txt in one of the few human-readable strings, preceded by several ‘=’ characters.
-----
### Important concept 
- `stings` - Extracts the human-readable text from the binary file.

### Command
**Run**
- `strings data.txt| grep "="`

*we see human readable strings using a `strings` command , we have another hint which is preceded by several ‘=’ characters; so we use `grep "="`.*

> even when we use `grep "="` it still shows you unwanted text try using `grep"==="`

**Run**
`strings data.txt| grep "==="`
----
###Note
>Please store the passwd for nexr level  in your text editor
---
***Alish**
