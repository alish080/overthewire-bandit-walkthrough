### Level 24 > Level 25

### Goal 

A daemon is listening on port 30002 and will give you the password for bandit25 if given the password for bandit24 and a secret numeric 4-digit pincode. There is no way to retrieve the pincode except by going through all of the 10000 combinations, called brute-forcing.
You do not need to create new connections each time

### Understanding the concept 

Here, the port 30002 is listing to where we have to give password which we loged in to this level along with 4 digit numeric code 

Fun thin is we don't have that 4 digit numeric number , we have to find the 4 digit numeric code by using brute force we will write a script where we will try all 4 digit possible from (0000 to 9999) and along with a password we will send that to port 30002

***Run***

`for i in {0000..9999}; do echo "gb8KRRCsshuZXI0tUuR6ypOFjiZbf3G8 $i" done | nc localhost 30002 `

so this is our script to what it does is,

- `for (loop)` : is where we will try all the possible 4 digit numbers
- `do done`: for people whom bash might be new, if you have learned any programming language the concept is same as "do while" .
- `nc localhost 30002`: so basically we are sending the output to port 30002 to check 

After you press enter you will see something like "Wrong! Please enter the correct current passowrd and pincode .Try again." and after few line you will see a passsword 

> iCi86ttT4KSNe1armKiwbQNmB3YJP3q4
---

***Alish***  
