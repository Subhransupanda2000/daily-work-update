# 🌍 AWS Masterclass Notes

> Lesson 2 - AWS Global Infrastructure

---

# 📚 What is AWS Global Infrastructure?

AWS Global Infrastructure is the worldwide network of AWS data centers that allows applications to run reliably, securely, and with low latency.

It consists of:

- Regions
- Availability Zones (AZs)
- Edge Locations
- Local Zones

```
AWS Global Infrastructure

│

├── Regions
│      │
│      ├── Availability Zone A
│      ├── Availability Zone B
│      └── Availability Zone C
│
├── Edge Locations
│
└── Local Zones
```

---

# Why Does AWS Need Global Infrastructure?

Suppose your application is hosted in the USA.

If users access it from India:

```
India User
     │
Internet
     │
USA Server
```

The request travels thousands of kilometers, increasing **latency**.

To reduce latency, AWS has data centers around the world.

---

# Region

## Definition

A **Region** is a **geographical location** where AWS operates multiple Availability Zones.

Examples:

- US East (N. Virginia)
- US West (Oregon)
- Asia Pacific (Mumbai)
- Asia Pacific (Hyderabad)
- Europe (London)
- Asia Pacific (Singapore)

Each Region is completely independent.

---

## Characteristics

- Geographical location
- Contains multiple Availability Zones
- Independent from other Regions
- Resources are Region-specific

---

## Example

```
India

│

├── Mumbai Region

└── Hyderabad Region
```

---

# Availability Zone (AZ)

## Definition

An **Availability Zone (AZ)** is one or more physically separate data centers within a Region.

Example:

```
Mumbai Region

│

├── AZ-A

├── AZ-B

└── AZ-C
```

Each AZ has:

- Independent power supply
- Independent cooling
- Independent networking
- Independent security

AWS connects AZs using high-speed private fiber.

---

# Why Multiple Availability Zones?

Suppose your application is deployed only in AZ-A.

```
EC2

↓

AZ-A
```

If AZ-A experiences a power outage:

❌ Your application becomes unavailable.

---

Deploying across multiple AZs:

```
Internet

     │

Load Balancer

     │

──────────────

│            │

AZ-A      AZ-B

EC2        EC2
```

If AZ-A fails:

Traffic is automatically routed to AZ-B.

This is called **High Availability**.

---

# High Availability (HA)

## Definition

High Availability means an application continues running even if one server or Availability Zone fails.

AWS recommends deploying production applications across **at least two Availability Zones**.

---

# Edge Locations

## Definition

Edge Locations are AWS sites located closer to users.

They cache frequently accessed content to reduce latency.

Example:

Without CloudFront:

```
Delhi User

↓

Mumbai Server
```

With CloudFront:

```
Delhi User

↓

Delhi Edge Location

↓

Content Delivered
```

Benefits:

- Faster content delivery
- Lower latency
- Reduced load on origin servers

---

# Local Zones

## Definition

Local Zones extend AWS infrastructure closer to large metropolitan areas for ultra-low latency applications.

Common use cases:

- Online Gaming
- Video Editing
- Financial Trading
- Media Rendering
- Real-time Analytics

---

# Region vs Availability Zone

| Region | Availability Zone |
|---------|-------------------|
| Geographical location | One or more data centers |
| Contains multiple AZs | Located inside a Region |
| Independent from other Regions | Independent from other AZs |
| Example: Mumbai | Example: ap-south-1a |

---

# Region vs Edge Location

| Region | Edge Location |
|---------|---------------|
| Runs applications | Caches content |
| Hosts compute and databases | Delivers cached content faster |
| Contains AZs | Used by CloudFront |

---

# How to Choose an AWS Region

Choose a Region based on:

### 1. Latency

Select the Region closest to your users.

Example:

Users in India → Mumbai or Hyderabad.

---

### 2. Cost

Pricing differs between Regions.

---

### 3. Compliance

Some applications require data to remain in a specific country.

---

### 4. Service Availability

Not every AWS service is available in every Region.

---

# Your AWS Console

Current Region (from your console):

```
US East (N. Virginia)
```

Why it is popular:

- Most AWS tutorials use it
- Many services launch there first
- Often among the lowest-cost Regions

---

# Real-World Architecture

```
Users

↓

Route53

↓

Application Load Balancer

↓

AZ-A               AZ-B

EC2                 EC2

↓

Amazon RDS (Multi-AZ)

↓

Amazon S3

↓

Amazon CloudWatch
```

Benefits:

- High Availability
- Fault Tolerance
- Scalability

---

# Key Terms

| Term | Meaning |
|------|---------|
| Region | Geographical area containing multiple Availability Zones |
| Availability Zone | One or more isolated data centers inside a Region |
| Edge Location | AWS site that caches content close to users |
| Local Zone | AWS infrastructure closer to cities for low-latency workloads |
| High Availability | Keeping applications running despite failures |
| Latency | Time taken for data to travel between client and server |

---

# Interview Questions

## Q1. What is an AWS Region?

A geographical location containing multiple Availability Zones.

---

## Q2. What is an Availability Zone?

One or more physically separate data centers within a Region.

---

## Q3. Why do we deploy applications across multiple AZs?

To achieve High Availability and Fault Tolerance.

---

## Q4. What is an Edge Location?

An AWS site that caches and delivers content closer to users, reducing latency.

---

## Q5. Why should we choose the Region closest to our users?

To reduce network latency and improve application performance.

---

# Memory Trick

```
Region
↓

Contains Multiple Availability Zones

↓

Availability Zones Run Applications

↓

Edge Locations Deliver Content Faster

↓

Local Zones Provide Ultra-Low Latency
```

---

# Lesson Summary

- AWS has a global network of data centers.
- A Region is a geographical location.
- A Region contains multiple Availability Zones.
- Availability Zones improve High Availability.
- Edge Locations cache content closer to users.
- Local Zones support applications requiring ultra-low latency.
- Resources are isolated between Regions.
- Choose Regions based on latency, cost, compliance, and service availability.

---

# Homework

- [ ] Explain the difference between Region and Availability Zone.
- [ ] What is High Availability?
- [ ] Why are applications deployed across multiple AZs?
- [ ] What is an Edge Location?
- [ ] What is the purpose of a Local Zone?
- [ ] Why are resources isolated between Regions?
- [ ] How do you choose the best AWS Region for an application?

---
