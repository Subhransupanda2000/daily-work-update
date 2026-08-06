# 🔐 AWS Masterclass Notes

> Lesson 3 - IAM (Identity and Access Management)

---

# 📚 What is IAM?

IAM (Identity and Access Management) is the AWS service used to securely manage **who can access AWS resources** and **what actions they are allowed to perform**.

IAM controls:

- Authentication (Who are you?)
- Authorization (What are you allowed to do?)

---

# Why Do We Need IAM?

Imagine a company with different employees:

- Developers
- Testers
- DevOps Engineers
- Finance Team
- HR Team

Not everyone should have full access to AWS.

Examples:

- Developers → Deploy applications
- Finance → View billing
- HR → No access to EC2
- DevOps → Manage infrastructure

IAM ensures each person gets only the permissions they need.

---

# Authentication vs Authorization

## Authentication

Verifies **who you are**.

Examples:

- Username
- Password
- MFA

Question:

> Who are you?

---

## Authorization

Determines **what you can do**.

Examples:

- Launch EC2
- Read S3
- Delete RDS

Question:

> What are you allowed to do?

---

# Root User

## Definition

The Root User is created automatically when an AWS account is created.

It has **full administrative access** to every AWS service and account setting.

### Root User Can

- Delete the AWS Account
- Change Billing Information
- Create IAM Users
- Delete Resources
- Access All AWS Services

### Best Practice

- Use Root User only for account-level tasks.
- Never use Root User for daily work.
- Always enable MFA.

---

# IAM User

## Definition

An IAM User represents a person or application that needs access to AWS.

Each IAM User has:

- Username
- Password (Console Login)
- Access Keys (Programmatic Access)
- Permissions

Example:

```
AWS Account

│

├── Root User

│

├── Rahul

├── Priya

├── Amit

└── DevOps
```

---

# IAM Group

## Definition

An IAM Group is a collection of IAM Users.

Instead of assigning permissions to each user individually, assign permissions to the group.

Example:

```
Developers Group

├── Rahul

├── Priya

└── Amit
```

Assign permissions once to the group.

All members automatically receive them.

---

# IAM Policy

## Definition

A Policy is a JSON document that defines permissions.

Example:

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Action": [
        "ec2:StartInstances",
        "ec2:StopInstances"
      ],
      "Resource": "*"
    }
  ]
}
```

This policy allows:

- Start EC2
- Stop EC2

It does NOT allow deleting EC2 instances.

---

# IAM Role

## Definition

An IAM Role is a temporary identity that AWS services or applications can assume to obtain permissions.

Unlike IAM Users, Roles do not have:

- Passwords
- Long-term Access Keys

Example:

```
EC2 Instance

↓

IAM Role

↓

Amazon S3
```

The EC2 instance can securely access S3 without storing AWS credentials.

---

# IAM User vs IAM Role

| IAM User | IAM Role |
|----------|----------|
| Permanent identity | Temporary identity |
| Used by people | Used by AWS services or applications |
| Has password and access keys | No password or long-term keys |
| Example: Developer | Example: EC2 accessing S3 |

---

# Principle of Least Privilege

## Definition

Grant users only the minimum permissions required to perform their tasks.

### Bad Practice

Developer has:

```
AdministratorAccess
```

### Good Practice

Developer has permission to:

- Read S3
- Start EC2
- Stop EC2

Nothing more.

---

# Multi-Factor Authentication (MFA)

## Definition

MFA adds an extra layer of security.

Login requires:

- Password
- One-Time Verification Code

Benefits:

- Protects against stolen passwords
- Reduces unauthorized access

Always enable MFA for:

- Root User
- Privileged IAM Users

---

# Access Keys

## Definition

Access Keys allow programmatic access to AWS.

Used by:

- AWS CLI
- SDKs
- Applications

Each Access Key includes:

- Access Key ID
- Secret Access Key

Example:

```
Application

↓

AWS SDK

↓

Access Key

↓

AWS Services
```

### Best Practices

- Never commit keys to GitHub.
- Rotate keys regularly.
- Prefer IAM Roles over Access Keys on AWS resources.

---

# AWS Managed Policies vs Customer Managed Policies

## AWS Managed Policy

Created and maintained by AWS.

Examples:

- AmazonS3ReadOnlyAccess
- AmazonEC2FullAccess
- AdministratorAccess

---

## Customer Managed Policy

Created and maintained by your organization.

Used for custom permission requirements.

---

# Real-World Example

Company Structure:

```
AWS Account

│

├── Developers Group

├── Testers Group

├── DevOps Group

└── Finance Group
```

Permissions:

- Developers → EC2 + S3
- Testers → Read-only
- DevOps → Full Infrastructure
- Finance → Billing Only

When a new developer joins:

- Create IAM User
- Add to Developers Group

No need to assign permissions individually.

---

# IAM Best Practices

- Never use Root User for daily work.
- Enable MFA for Root User.
- Create IAM Users for each person.
- Use IAM Groups for permission management.
- Follow the Principle of Least Privilege.
- Prefer IAM Roles over Access Keys.
- Rotate credentials regularly.
- Never share AWS credentials.

---

# Key Terms

| Term | Meaning |
|------|---------|
| IAM | Identity and Access Management |
| Authentication | Verifying identity |
| Authorization | Determining permissions |
| Root User | AWS account owner with full access |
| IAM User | Identity for a person or application |
| IAM Group | Collection of IAM Users |
| IAM Role | Temporary identity for AWS services or users |
| IAM Policy | JSON document defining permissions |
| MFA | Multi-Factor Authentication |
| Access Key | Credentials for programmatic access |

---

# Interview Questions

## Q1. What is IAM?

IAM is the AWS service used to manage authentication and authorization.

---

## Q2. What is the difference between Authentication and Authorization?

Authentication verifies identity.

Authorization determines permissions.

---

## Q3. Why should the Root User not be used daily?

Because it has unrestricted access and increases security risks.

---

## Q4. What is an IAM Role?

A temporary identity that provides permissions to AWS services, applications, or users without long-term credentials.

---

## Q5. Why are IAM Roles preferred over Access Keys?

Roles automatically provide temporary credentials and eliminate the need to store secrets.

---

## Q6. What is the Principle of Least Privilege?

Grant users only the permissions required to perform their tasks.

---

# Memory Trick

```
IAM

↓

Authentication
(Who are you?)

↓

Authorization
(What can you do?)

↓

Users

↓

Groups

↓

Policies

↓

Roles

↓

Secure AWS Access
```

---

# Lesson Summary

- IAM controls access to AWS resources.
- Authentication verifies identity.
- Authorization defines permissions.
- Root User has unrestricted access and should not be used daily.
- IAM Users represent people or applications.
- IAM Groups simplify permission management.
- IAM Policies define permissions using JSON.
- IAM Roles provide temporary credentials for AWS services.
- MFA adds an extra layer of security.
- Always follow the Principle of Least Privilege.

---

# Homework

- [ ] Explain Authentication and Authorization.
- [ ] What is the difference between Root User and IAM User?
- [ ] Why do we use IAM Groups?
- [ ] What is an IAM Policy?
- [ ] What is an IAM Role?
- [ ] Why are IAM Roles preferred over Access Keys?
- [ ] Explain the Principle of Least Privilege.
- [ ] Why should MFA always be enabled?

---
