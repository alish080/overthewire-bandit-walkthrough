### Level 21 > Level 22

### Goal
A program is running automatically at regular intervals from cron, the time-based job scheduler. Look in /etc/cron.d/ for the configuration and see what command is being executed.

### Solution
Cron is the time based schedular

so basically what we know us there is a shell script that is being running in a `/etc/cron.d` 
**Run**

`cd /etc/cron.d`
`ls`

Now you will see a bunch of files as we are searching password for level 22 we whould foucs on a file  "cronjob_bandit22"

**Run**

`cat cronjob_bandit22`
you will see,

`@reboot bandit22 /usr/bin/cronjob_bandit22.sh &> /dev/null`
`* * * * * bandit22 /usr/bin/cronjob_bandit22.sh &> /dev/null`

> This means that the script is owned by the bandit22 and that path is also given and a script is also there "bandit22.sh, this script is running every second"

If you read the script file

You will see a script

cat /usr/bin/cronjob_bandit22.sh
#!/bin/bash
chmod 644 /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv
cat /etc/bandit_pass/bandit22 > /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv


Here the password is stored in a temp folder 

***Run***

`cat /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv`

you will receive the passswd
- tRae0UfB9v0UzbCdn9cY0gQnds9GF58Q
---
***Alish***
