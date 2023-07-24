---
toc: true
layout: post
description: A way to restrict/unrestrict user login in linux system
author: Zeel B Patel
categories: [Linux]
title: Restrict/unrestrict user login
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
