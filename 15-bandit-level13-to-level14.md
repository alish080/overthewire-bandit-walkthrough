# Bandit Level 13 → 14 Walkthrough

## Goal

Log in to **bandit14** using the private SSH key provided in the **bandit13** home directory and retrieve the password for the next level.

---

# Theory — SSH Key Authentication (Bandit Level 13 → 14)

## 1. What is SSH?

**SSH (Secure Shell)** is a protocol used to securely connect to remote systems over a network.
It provides encrypted communication between a client and a server.

SSH is commonly used for:

* Remote server administration
* Secure file transfer
* DevOps and cloud infrastructure management
* Secure remote login

Basic SSH command:

```
ssh username@host
```

Example:

```
ssh bandit13@bandit.labs.overthewire.org -p 2220
```

---

# 2. Password Authentication vs Key Authentication

SSH supports two main authentication methods.

## Password Authentication

The user enters a password when connecting.

Example:

```
ssh bandit13@bandit.labs.overthewire.org -p 2220
```

The server verifies the password before allowing access.

---

## SSH Key Authentication

Instead of a password, SSH uses a **key pair**:

* **Private Key** – kept secret on the client machine
* **Public Key** – stored on the server in `authorized_keys`

When a user connects:

1. The client proves ownership of the **private key**
2. The server checks if the corresponding **public key** is trusted
3. If they match, access is granted

This method is more secure than passwords.

---

# 3. Structure of an SSH Key

A private key typically looks like:

```
-----BEGIN RSA PRIVATE KEY-----
...
-----END RSA PRIVATE KEY-----
```

Important properties:

* Must be kept secret
* Used only by the owner
* Never shared publicly

---

# 4. SSH Key Permissions

SSH requires strict permissions for private keys.

If a key file is readable by others, SSH refuses to use it.

Correct permission:

```
chmod 600 sshkey.private
```

Meaning:

| Permission | Description  |
| ---------- | ------------ |
| Owner      | Read + Write |
| Group      | No access    |
| Others     | No access    |

This ensures only the owner can read the key.

---

# 5. Using the `-i` Option

The `-i` flag tells SSH which private key to use.

Example:

```
ssh -i sshkey.private bandit14@bandit.labs.overthewire.org -p 2220
```

Explanation:

| Component                   | Meaning                     |
| --------------------------- | --------------------------- |
| ssh                         | SSH client                  |
| -i sshkey.private           | Identity file (private key) |
| bandit14                    | Username                    |
| bandit.labs.overthewire.org | Remote server               |
| -p 2220                     | SSH port                    |

---

# 6. Secure Copy (SCP)

`scp` is used to securely copy files between machines over SSH.

Example:

```
scp -P 2220 bandit13@bandit.labs.overthewire.org:sshkey.private .
```

Explanation:

* `scp` – secure copy command
* `-P 2220` – SSH port
* `bandit13@bandit.labs.overthewire.org` – remote server
* `sshkey.private` – file being copied
* `.` – current directory on the local machine

---

	Identity file (private key)
bandit14	Username
bandit.labs.overthewire.org	Remote server
-p 2220	SSH port

6. Secure Copy (SCP)

scp is used to securely copy files between machines over SSH.

Example:

scp -P 2220 bandit13@bandit.labs.overthewire.org:sshkey.private .

Explanation:

scp – secure copy command

-P 2220 – SSH port

bandit13@bandit.labs.overthewire.org – remote server

sshkey.private – file being copied

. – current directory on the local machine

### Bandit Level 13 → 14 Concept

In this level:

- The user cannot read the password file directly

- Instead, a private SSH key is provided

- The key is used to authenticate as bandit14

- Once logged in, the password is retrieved from:

`/etc/bandit_pass/bandit14`

### Command

## Step 1 — Identify the key file

After logging in as `bandit13`, list the files:

```
ls
```

Output:

```
HINT
sshkey.private
```

The file `sshkey.private` is a **private SSH key** that can be used to authenticate as `bandit14`.

---

## Step 2 — Copy the key to your local machine

The Bandit server blocks SSH connections from `localhost`, so the key must be used from your **local machine**.

Run this from your local terminal:

```
scp -P 2220 bandit13@bandit.labs.overthewire.org:sshkey.private .
```

Explanation:

* `scp` → secure copy command
* `-P 2220` → SSH port used by Bandit
* `bandit13@bandit.labs.overthewire.org` → remote server
* `sshkey.private` → file being copied
* `.` → current directory on your local machine

---

## Step 3 — Fix the key permissions

SSH requires private keys to be readable only by the owner.

```
chmod 600 sshkey.private
```

Meaning of `600`:

* Owner: read + write
* Group: no permissions
* Others: no permissions

This ensures **only you can read the key**, which is required by SSH for security reasons.

---

## Step 4 — Log in as bandit14 using the key

Use the private key with SSH:

```
ssh -i sshkey.private bandit14@bandit.labs.overthewire.org -p 2220
```

Explanation:

* `-i sshkey.private` → use this private key for authentication
* `bandit14@bandit.labs.overthewire.org` → user and server
* `-p 2220` → SSH port used by the Bandit server

If successful, you will see:

```
bandit14@bandit:~$
```

---

## Step 5 — Retrieve the password for the next level

The password for the next level is stored in:

```
/etc/bandit_pass/bandit14
```

Run:

```
cat /etc/bandit_pass/bandit14
```

Output:

```
MU4VWeTyJk8ROof1qqmcBPaLh7lDCPvS
```

This password is used to log in as **bandit15**.

---
***Alish***
