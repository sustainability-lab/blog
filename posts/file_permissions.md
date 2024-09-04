---
author: Zeel B Patel
categories:
- linux
date: '2023-07-25'
description: Managing file permissions in a shared server
layout: post
title: File Permissions
toc: true

---

## CheatSheet

* 3 positions in the permission string:
  - 1st position: Owner
  - 2nd position: Group
  - 3rd position: Others

* All useful combinations of permissions:

| Permission          | Number | Symbol |
| ------------------- | ------ | ------ |
| No access           | 0      | -      |
| Read                | 4      | r      |
| Write               | 2      | w      |
| Execute             | 1      | x      |
| Read + Write        | 6      | rw     |
| Read + Exec         | 5      | rx     |
| Read + Write + Exec | 7      | rwx    |

* Permissions such as "Write + Execute" are not useful because if we don't want a user to read a file, we should not allow them to write to it either.

* Meaning of `umask xxxx` 



* Some useful commands:

| To Do                                                     | How To Do            |
| --------------------------------------------------------- | -------------------- |
| Prevent everyone else from reading a file                 | `chmod 600 filename` |
| Prevent everyone else from entering a dir                 | `chmod 600 dirname`  |
| Prevent everyone else from reading dir content            | `chmod 700 dirname`  |
| Prevent everyone else from reading every new file and dir | `umask 0077`         |