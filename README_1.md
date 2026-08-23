# Resilient AWS Web Infrastructure

*Working title: "The Battle-Scars Project"*

![Status](https://img.shields.io/badge/status-in%20progress-b97a1e)
![AWS](https://img.shields.io/badge/cloud-AWS-orange)
![IaC](https://img.shields.io/badge/IaC-Terraform-623ce4)
![Phase](https://img.shields.io/badge/phase-0%20of%2010-blue)

A highly available, 3-tier web application built on AWS — provisioned with Terraform, deployed through CI/CD, monitored end to end, hardened for security, and deliberately broken at every stage so I have real incidents to talk about, not textbook answers.

## Why this exists

I passed AWS Certified Cloud Practitioner, then missed Solutions Architect Associate by one question — twice. That told me something: the knowledge was there, the applied, hands-on experience wasn't yet.

So instead of studying harder for another multiple-choice attempt, I'm building one real AWS environment end to end, on my own AWS account (not a sandbox), and intentionally causing failures at every stage — a bad deploy, a database failover, a simulated AZ outage — so I have to actually diagnose and fix them. The exam comes after, once the experience is real.

## The problem this project solves

*(the scenario I'm building against)*

A small company runs its application on a single server: no redundancy, no automated deployments, no monitoring. One failure takes the whole thing down, with no early warning and no fast way to recover. This project builds the fix for that, one deliberate piece at a time.

## What this demonstrates

- Designing and operating highly available cloud infrastructure, not just describing it
- Infrastructure as Code discipline — nothing is a manual console click that isn't also in version control
- A working CI/CD pipeline for both application and infrastructure changes
- Real observability — dashboards and alarms that have actually fired
- Security hardening to least-privilege, verified rather than assumed
- A measured recovery time from an actual disaster recovery drill, not a theoretical one
- Cost awareness, with a real before/after number

## Tech stack

**AWS:** VPC, EC2, ALB, Auto Scaling, RDS (Multi-AZ), S3, IAM, Secrets Manager, CloudWatch, SNS, GuardDuty, Security Hub, WAF, CloudTrail
**IaC:** Terraform (remote state in S3 + DynamoDB lock)
**CI/CD:** GitHub Actions
**Other:** Git, Linux, k6 (load testing)
**Region:** `ca-central-1`, chosen for latency reasoning 

## Progress

| Phase | What it covers | Status |
|---|---|---|
| 0 | Account foundations — root lockdown, IAM admin, billing alarms | ✅ [Complete](docs/phases/phase-0-account-foundations.md) |
| 1 | Custom networking — VPC, subnets, routing | ⬜ Not started |
| 2 | Compute + load balancing — EC2, ALB, Auto Scaling | ⬜ Not started |
| 3 | Database layer — RDS Multi-AZ | ⬜ Not started |
| 4 | Infrastructure as Code — Terraform rebuild | ⬜ Not started |
| 5 | CI/CD pipeline | ⬜ Not started |
| 6 | Observability | ⬜ Not started |
| 7 | Security hardening | ⬜ Not started |
| 8 | Cost optimization | ⬜ Not started |
| 9 | Disaster recovery drill | ⬜ Not started |
| 10 | Case study & architecture diagram | ⬜ Not started |

Each completed phase gets its own write-up in [`docs/phases/`](docs/phases/) — what I built, what I broke on purpose, and what I learned from fixing it.

## Battle scars log


| Phase | Incident | Root cause | Fix |
|---|---|---|---|
| — | — | — | — |

## About

Built by Kavya Katariya — web developer moving into cloud/DevOps. [LinkedIn](https://www.linkedin.com/in/katariyakavya097/)
