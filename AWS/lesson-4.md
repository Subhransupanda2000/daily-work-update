# 💻 AWS Masterclass Notes

> Lesson 4 - Amazon EC2 (Elastic Compute Cloud)

---

# 📚 What is EC2?

EC2 (Elastic Compute Cloud) is AWS's Virtual Machine service.

It allows you to create and manage servers in the cloud within minutes.

Instead of buying physical servers, AWS provides virtual servers that you can start, stop, resize, and terminate whenever needed.

---

# Real Life Example

Without AWS

```

Buy Physical Server
↓
Install OS
↓
Configure Network
↓
Install Java
↓
Deploy Application

```

With AWS

```

Click Launch Instance
↓
Wait 2 Minutes
↓
Virtual Server Ready

```

---

# Why EC2?

EC2 is used to:

- Host Spring Boot Applications
- Host React Applications
- Host NodeJS Applications
- Run Databases
- Run Docker Containers
- Run Microservices
- Host APIs

---

# What is a Virtual Machine?

A Virtual Machine (VM) is a software-based computer.

It has:

- CPU
- RAM
- Storage
- Network
- Operating System

Just like your laptop.

Difference:

It runs inside AWS instead of your home.

---

# EC2 Architecture

```

Internet

↓

Elastic IP

↓

Security Group

↓

EC2 Instance

↓

Operating System

↓

Application

↓

EBS Storage

```

---

# EC2 Components

## 1. AMI (Amazon Machine Image)

An AMI is a template used to launch an EC2 instance.

It contains:

- Operating System
- Pre-installed Software
- Configuration

Examples:

- Ubuntu
- Amazon Linux
- RedHat
- Windows Server

Think of an AMI like an ISO image used to install an operating system.

---

## 2. Instance Type

Instance Type defines the hardware configuration of the virtual machine.

It specifies:

- CPU
- RAM
- Network Performance
- Storage Performance

Example:

| Instance | vCPU | RAM |
|-----------|------|-----|
| t2.micro | 1 | 1 GB |
| t3.micro | 2 | 1 GB |
| t3.small | 2 | 2 GB |
| t3.medium | 2 | 4 GB |

For learning:

Use:

```
t2.micro
```

or

```
t3.micro
```

---

## 3. Key Pair

A Key Pair is used to securely connect to an EC2 instance.

It consists of:

```

Public Key

↓

Stored in EC2

Private Key (.pem)

↓

Stored on Your Laptop

```

Never share your private key.

If you lose it, you cannot SSH into the instance.

---

## 4. Security Group

A Security Group acts as a virtual firewall.

It controls:

- Incoming Traffic (Inbound Rules)
- Outgoing Traffic (Outbound Rules)

Example:

```

Internet

↓

Security Group

↓

EC2

```

Common Rules

| Port | Service |
|------|----------|
|22|SSH|
|80|HTTP|
|443|HTTPS|
|3306|MySQL|
|8080|Spring Boot|

---

## 5. Elastic IP

Normally:

```

Stop EC2

↓

Start Again

↓

Public IP Changes

```

Elastic IP provides a permanent public IP address.

Useful for production servers.

---

## 6. EBS (Elastic Block Store)

EBS is the hard disk attached to EC2.

It stores:

- Operating System
- Java
- Application
- Logs
- Files

Without EBS:

No data would be stored.

---

# EC2 Lifecycle

```

Launch

↓

Running

↓

Stop

↓

Start

↓

Reboot

↓

Terminate

```

---

## Running

Server is active.

Charges:

Compute + Storage

---

## Stop

Server is powered off.

Charges:

Storage only (EBS)

---

## Start

Server starts again.

New Public IP (unless Elastic IP is attached).

---

## Reboot

Restarts Operating System.

Public IP remains the same.

---

## Terminate

Deletes the EC2 instance permanently.

Important:

The instance is gone.

If Delete on Termination is enabled, attached EBS volumes are also deleted.

---

# Public IP vs Private IP

Every EC2 instance gets:

Private IP

Used inside AWS.

Example:

```
172.x.x.x
```

Public IP

Used from Internet.

Example:

```
13.x.x.x
```

---

# User Data

User Data is a startup script that runs automatically when the EC2 instance launches.

Example:

```bash
#!/bin/bash
sudo apt update
sudo apt install openjdk-21-jdk -y
sudo apt install git -y
```

Useful for automating server setup.

---

# SSH Connection

Linux:

```bash
chmod 400 key.pem

ssh -i key.pem ubuntu@public-ip
```

Windows:

- PuTTY
- Windows Terminal (OpenSSH)

---

# Launching EC2 (Hands-On)

## Step 1

Open AWS Console

↓

Search

```
EC2
```

---

## Step 2

Click

```
Launch Instance
```

---

## Step 3

Choose

```
Ubuntu Server 24.04 LTS
```

---

## Step 4

Choose Instance Type

```
t2.micro
```

or

```
t3.micro
```

---

## Step 5

Create Key Pair

Download

```
my-key.pem
```

Store it safely.

---

## Step 6

Network Settings

Allow

```
SSH (22)

HTTP (80)

HTTPS (443)
```

---

## Step 7

Launch Instance

Wait approximately one minute.

---

## Step 8

Copy Public IP

Example

```
13.234.xx.xx
```

---

## Step 9

SSH into the server

---

## Step 10

Run

```bash
sudo apt update
```

Congratulations!

You are now inside your own cloud server.

---

# Interview Questions

## Q1. What is EC2?

EC2 is AWS's virtual machine service that provides scalable compute capacity in the cloud.

---

## Q2. What is an AMI?

A preconfigured template containing an operating system and software used to launch EC2 instances.

---

## Q3. What is a Security Group?

A virtual firewall controlling inbound and outbound traffic for EC2 instances.

---

## Q4. Difference between Security Group and Firewall?

Security Group is AWS's virtual firewall attached to resources.

A traditional firewall usually protects physical or virtual servers at the operating system or network level.

---

## Q5. What is EBS?

Elastic Block Store is persistent block storage attached to EC2 instances.

---

## Q6. Difference between Stop and Terminate?

Stop

- Instance is powered off.
- EBS remains.
- You can start it again.

Terminate

- Instance is deleted permanently.
- EBS may also be deleted if configured.

---

# Memory Trick

```

AMI

↓

Launch EC2

↓

Attach EBS

↓

Configure Security Group

↓

Connect using SSH

↓

Deploy Application

```

---

# Lesson Summary

- EC2 is AWS's Virtual Machine service.
- AMI is the operating system template.
- Instance Type defines CPU and RAM.
- Key Pair is used for secure SSH access.
- Security Group acts as a firewall.
- Elastic IP provides a static public IP.
- EBS provides persistent storage.
- User Data automates server initialization.
- EC2 instances move through Launch → Running → Stop → Start → Reboot → Terminate.

---

# Homework

- [ ] What is EC2?
- [ ] What is an AMI?
- [ ] Explain the purpose of a Key Pair.
- [ ] What does a Security Group do?
- [ ] What is EBS?
- [ ] Difference between Public IP and Private IP?
- [ ] Difference between Stop and Terminate?
- [ ] Why would you use an Elastic IP?
- [ ] What is User Data?
- [ ] Launch your first EC2 instance and connect to it using SSH.
