---
author: Zeel B Patel
categories:
- Linux
date: '2023-07-25'
description: Simple solution to prevent multiple users to see each other's files.
layout: post
title: Remove read access to other users
toc: true

---

## Remove read access to other users for existing users

* To prevent other users from reading a user's data:

```bash
sudo chmod 700 /home/username
```

* Check if the access is restricted:

```bash
ls /home/username
```
It will show a message similar to the following:

```
ls: cannot open directory '/home/username': Permission denied
```

* To apply this restriction to all existing users, run the following command:

```bash
sudo chmod 700 /home/*
```

> All sudo users can still access the contents of the home directories of their own as well as others.

## How to set this by default for all new user accounts?

A solution is given [here](https://ubuntu.com/server/docs/security-users).

We can simply change the `DIR_MODE` in `/etc/adduser.conf` file to this:

```bash
DIR_MODE=0700
# DIR_MODE=0755  # This is default
```

Where:
- 0 means octal numbering system.
- 7 means read (4) + write (2) + execute (1) access to the owner.
- Last two zeros means no access to other users.