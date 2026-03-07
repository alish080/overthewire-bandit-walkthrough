### Level 11→ Level 12

### Goal

The password for the next level is stored in the file data.txt, where all lowercase (a-z) and uppercase (A-Z) letters have been rotated by 13 positions
---
### Important Concept

***ROT-13 CIPHER***
ROT13 ("rotate by 13 places") is a simple substitution cipher that replaces a letter with the 13th letter after it in the alphabet, wrapping back to A after Z. It is a reciprocal cipher—applying it twice restores the original text.
- To translate into a orginal text from ROT13 cipher 
- syntax is : `tr 'A-Za-z' 'N-ZA-Mn-za-m'`

Range	Alphabet Mapping
A – M	A B C D E F G H I J K L M
N – Z	N O P Q R S T U V W X Y Z

### Command 
**Run**
`ls`
- you will see a files "data.txt"

**Run**
`cat data.txt`
- you sill see "Gur cnffjbeq vf 7k16JArUVv5LxVuJfsSVdbbtaHGlw9D4"

> Here you will see a key but you will need to traslate the text (not the key)

**Run**
> We can solve it by two method

i) **Run**
- `cat data.txt | tr 'A-Za-z' 'N-ZA-Mn-za-m'`
Here,we directy translate the whole line which is "data.txt" where the first words are ROT13  encrypted to orginal text.

ii) **Run**
- `eho "Gur cnffjbeq vf 7k16JArUVv5LxVuJfsSVdbbtaHGlw9D4"| tr 'A-Za-z' 'N-ZA-Mn-za-m`
Here, we simply print the whole line we get and traslate it to orginal text.
----
### NOTE
> Please store the key in your text editor
----
***Alish***
  
