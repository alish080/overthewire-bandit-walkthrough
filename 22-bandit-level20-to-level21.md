### Level 20 > Level21

### Goal

There is a setuid binary in the homedirectory that does the following: it makes a connection to localhost on the port you specify as a commandline argument. It then reads a line of text from the connection and compares it to the password in the previous level (bandit20). If the password is correct, it will transmit the password for the next level (bandit21).

### Understanding the question
> There is a setuid file in a home directory what we need to do is
>In 2nd terminal, first make our own listining server and we will send the passswd there send it to  suconnect which will verify and if correct give you correct paswd

### Command

First we will openanother terminal and log into server bandit20 
`ssh bandit20@bandit.labs.overthewire.org -p 2220`

Now, we will make our own server here which will be for listining,so suconnect will connect and read the passwd

`nc -l -p 1234`

Now,
GO to your first terminal and 
**Run**

`./suconnect 1234`
> now our suconnect will connect to port that we made 

Again,
Go,to the 2nd terminal and paste the passswd we found in bandit19  once it matched you will get your passwd.

passwd for next level is given in 2nd terminal
>EeoULMCra2q0dSkYj561DX7s1CpBuOBt

---
***Alish*** 
 
