---
aliases:
- /Linux/2023/07/24/Prevent-login
author: Zeel B Patel
categories:
- Linux
date: '2023-07-24'
description: A way to restrict/unrestrict user login in linux system
layout: post
title: Restrict/unrestrict user login
toc: true

---

## Restrict/unrestrict user login in linux system

* To restrict user login:

```bash
sudo usermod -s /usr/sbin/nologin username
```

* Check if the user has been restricted:

```bash
sudo su - username
```
It will show a message similar to the following:

```
This account is currently not available.
```

* To unrestrict user login:

```bash
sudo usermod -s /bin/bash username
```
