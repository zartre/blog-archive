---
title: "Set up a local SFTP server in minutes with SFTPGo"
date: 2022-09-07
categories:
  - "Tutorial"
tags:
  - "dev"
coverImage: "./images/1_PkYJWJ3n4G07W0CNCysYwg.webp"
public: true
---

I had to work with SFTP and needed to set up an SFTP server on my Mac for development. It was very difficult to find software to set up an SFTP server on a Mac. Then I found _SFTPGo_, a very simple solution to SFTP servers.

Github: [https://github.com/drakkan/sftpgo](https://github.com/drakkan/sftpgo)

SFTPGo, as the name implies, is an SFTP server written in Go language. It can be run on Linux, macOS and Windows. This blog post will proceed with macOS but everything should be the same on all platforms, except for the installation part.

# Installation

Run the below command in a terminal to install SFTPGo using `brew` on macOS.

```
brew install sftpgo
```

Run the below command to start the server. This will create an SQLite database and host keys in the current working directory, and run a web interface on port `8080` and an SFTP server on port `2022`. We can configure these settings through a configuration file, but for now let’s just start the server the simplest way.

```
sftpgo serve
```

Open [http://localhost:8080/web/admin](http://localhost:8080/web/admin) to create an administrator account.

![](./images/1_gyTnflYTOMct_0fNDuxkVQ.webp)

# Creating a user

Open [http://localhost:8080/web/admin](http://localhost:8080/web/admin) to enter the admin console. In _Users_ page, click _Add_ (+) to create a new user.

![](./images/1_un07bOSQeyxyFLwOwoTJiQ.webp)

Fill in details: a username, a password, a public key (optional if you want to use public key authentication), and a home directory for the user. Click _Submit_ and you are ready to test.

![](./images/1_Yy52wrzlyP-ac72SmYn9zQ.webp)

# Testing the connection

Run the below command to open an SFTP connection. Of course, replace _user_ with the username you have set in the previous step. This command will open a connection to `127.0.0.1` at port `2022` with user `user`. It should prompt you to enter a password and establish a successful connection.

```
sftp -P 2022 user@127.0.0.1
```

Voilà! You have just—hopefully—successfully set up a local SFTP server!

# Further configuration

If you want to configure how SFTPGo works, the simplest way is to create a configuration file named as `sftpgo` with an extension of either JSON or YAML (see the [doc](https://github.com/drakkan/sftpgo/blob/main/docs/full-configuration.md) for more extensions).

You can configure which public-private key pairs the SFTP server should use as host keys, which port the server should run on, etc.
