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

## Remove read access to other users

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

* To apply this restriction to all users, run the following command:

```bash
sudo chmod 700 /home/*
```

> All sudo users can still access the contents of the home directories of their own as well as others.