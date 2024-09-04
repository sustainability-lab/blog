---
author: Zeel B Patel
categories:
- dev
date: '2024-09-04'
description: Internet login in servers. K different ways.
layout: post
title: Internet Login in IITGN Network from CLI Servers
toc: true

---

# What is Internet Login in CLI Servers?

We have multiple servers e.g. Ramanujan which are rack servers and internet often expires in these servers at a regular interval. So, we need to login to the internet when it expires.

# OS agnostic ways

## Using `browsh` CLI Browser
- We have `browsh` installed in the servers.
- Simply type `browsh` in the terminal and hit enter.
- It should open a CLI browser.
- Press `Ctrl + L` to go to the URL bar.
- Go to https://internet.iitgn.ac.in/ and login with your credentials.

## Dynamic Port Forwarding (SOCKS Proxy)
- Login from CMD/terminal using `ssh` command with dynamic port forwarding.
```bash
ssh -D 8080 username@server
```
- Now, set the proxy in your browser to `localhost:8080` and you are good to go.
- Go to https://internet.iitgn.ac.in/ and login with your credentials.
- You can turn off the proxy in your browser after you are done.

# Windows
## Using MobaXterm
- Download and install MobaXterm from [here](https://mobaxterm.mobatek.net/download.html).
- Open MobaXterm and setup a new session for the server.
- Once you are able to login via ssh. Simply type `firefox` in the terminal and hit enter.
- It should automatically open a separate window with the browser.
- Go to https://internet.iitgn.ac.in/ and login with your credentials.


> This could be slower than the OS agnostic ways.

# Linux (Ubuntu)
- Use `ssh` with additional `-X` flag.
```bash
ssh -X username@server
```
- Now, type `firefox` in the terminal and hit enter.
- It should automatically open a separate window with the browser.
- Go to https://internet.iitgn.ac.in/ and login with your credentials.

> This could be slower than the OS agnostic ways.

# Mac
- Install `XQuartz` from [here](https://www.xquartz.org/).
- In XQuartz terminal, type `ssh -X username@server`.
- Now, type `firefox` in the terminal and hit enter.
- It should automatically open a separate window with the browser.

> This could be slower than the OS agnostic ways.