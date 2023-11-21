---
layout: post
title: "SSH and SCP: Whats and Whys"
date: 2023-11-20 23:45:13 -0400
background: '/img/posts/02.jpg'
author: 'miguel'
---
This article explores the basics of SSH (Secure Shell) and SCP (Secure Copy Protocol). SSH acts like a secure key to control and communicate with remote computers, while SCP serves as a trustworthy courier for securely transferring files between them. Join me as we unravel the simplicity and importance of these secure protocols, making remote access and file transfers a breeze.

## What is SSH and why do we use it?
SSH, or Secure Shell is a network protocol that lets us securely access and control computers or servers over a network. We use it to remotely manage systems, execute commands, transfer files, and ensure our communications are private and protected from unauthorized access. It's like a secure key to unlock the door to another computer.

I had heard of SSH before, but I didn't know how it worked until our manager gave us a lesson. He showed us how to use SSH to connect to a server, It was pretty neat, and he used his server to demonstrate it to us.

#### Public Keys and Private Keys
In SSH, we have two special keys the private and public keys. Think of private keys like a secret key that opens the door to your computer or server. It's a secret, so you never share it with anyone. Now, your public key is like a lock that matches your secret key. You can share it freely, and others can use it to talk to your computer or server, but they can't open the door with it. You can find these keys in your home directory, in a folder called `~/.ssh`. You can easily identify which is a public key because it has a `.pub` at the end, while the private key doesn't have any extension.

Before we can enter a server using SSH, we need to prove who we are. For our practice, we gave our manager our public keys. He put them in a file called `~/.ssh/authorized_keys` on his server. With our public keys there, the server recognizes us, and we become like friends. Now we can access it securely. The private key is our identity, and it matches with our public key. After SSH, we also talked about SCP or Secure Copy Protocol.

To connect to a server using SSH, you can use the following command:

`ssh username@servername` or `ssh username@ip_address`

Replace `username` with your username on the server, and `servername` or `ip_address` with the server's domain name or its IP address.

## What is SCP and why do we use it?
SCP, or Secure Copy Protocol is a way to copy files securely between computers over a network. We use it to send and receive files while ensuring they remain safe from unauthorized access. It's like a trusted courier service for our files. 

The `scp` command is used to securely copy files and directories between two computers over an SSH connection.

`scp <source> <destination>`

- `source` is the file or directory you want to copy from your local machine or another remote server.
- `destination` is where you want to copy the file or directory, which can be on your local machine or a remote server.

Example:

1. Copy a file from your local machine to a remote server:

`scp /path/to/local/file username@servername:/path/to/destination/`

2. Copy a file from a remote server to your local machine:

`scp username@servername:/path/to/remote/file /path/to/destination/`