# Module 1 — Introduction to DevOps

> **Course:** DevOps
> **Module:** 1 — Introduction to DevOps
> **Type:** Introductory and conceptual
> **Scope:** Theory, explanations, comparisons and block diagrams. Hands-on work (Linux, Git, Docker, cloud, Kubernetes, Terraform, CI/CD tools) is covered in later modules.
> **Estimated study time:** about 25 minutes of lecture, plus self-study of this document

---

## Module Overview

This module explains **what DevOps is, why it exists, and how its main building blocks fit together**. Each topic below matches a section of the lecture and the slide deck *"DevOps Unlocked: Code to Cloud"*.

| # | Course topic | Section in this document |
|---|--------------|--------------------------|
| 1 | What is DevOps? | [Section 1](#1-what-is-devops) |
| 2 | DevOps Main Objectives | [Section 2](#2-devops-main-objectives) |
| 3 | DevOps and Software Development Life Cycle | [Section 3](#3-devops-and-software-development-life-cycle-sdlc) |
| 4 | Continuous Integration & Deployment | [Section 4](#4-continuous-integration--deployment-cicd) |
| 5 | Containers and Virtual Development | [Section 5](#5-containers-and-virtual-development) |
| 6 | Cloud Providers | [Section 6](#6-cloud-providers) |
| 7 | Scripting | [Section 7](#7-scripting) |
| 8 | Configuration Management Tools | [Section 8](#8-configuration-management-tools) |

Supporting sections for the DevOps journey:

| Section | Topic |
|---------|-------|
| [9](#9-supporting-concepts-you-will-meet-next) | Supporting concepts: Version Control, Infrastructure as Code, Monitoring, DevSecOps, Agile vs DevOps, DORA metrics |
| [10](#10-how-everything-fits-together) | How everything fits together (the big picture) |
| [11](#11-learning-roadmap) | Learning roadmap for the course |
| [12](#12-glossary) | Glossary |
| [13](#13-interview-questions-and-answers) | Interview questions and answers |
| [14](#14-self-check-quiz) | Self-check quiz |
| [15](#15-module-summary) | Module summary |

### Learning outcomes

After this module you should be able to:

- Define DevOps and explain why it is a culture and set of practices, not just a tool or job title.
- List the main objectives of DevOps (speed, reliability, scalability, collaboration, automation, quality, agility).
- Describe how DevOps relates to the SDLC.
- Distinguish Continuous Integration, Continuous Delivery and Continuous Deployment.
- Compare virtual machines and containers.
- Explain why cloud platforms matter to DevOps and name the three major providers.
- Explain the role of scripting and configuration management.
- Draw the big picture of a delivery pipeline from code to cloud.

---

# 1. What is DevOps?

## 1.1 Definition

**DevOps = Development + Operations.**

DevOps is a combination of **culture, practices and tools** that brings software development (Dev) and IT operations (Ops) teams closer together. Its goal is to build, test, release, deploy and operate software **faster, more reliably and continuously**.

DevOps is **culture first, tools second**. It is *not* only a job title or a list of tools. It emphasizes:

- Collaboration between teams
- Automation of repetitive work
- Shared responsibility
- Continuous integration and delivery
- Monitoring and feedback
- Continuous improvement

## 1.2 Understanding Dev and Ops

| Team | Typical responsibilities |
|------|--------------------------|
| **Development (Dev)** | Understand requirements, design software, write and maintain code, do development-level testing, build new features and fixes |
| **Operations (Ops)** | Manage infrastructure and environments, deploy and configure applications, keep systems available and reliable, monitor systems and respond to incidents |

Traditionally these teams worked in **silos** and handed work over to each other. That created misunderstandings and deployment problems, summed up by a familiar argument:

> **Developer:** "It works on my machine."
> **Operations:** "But it doesn't work on the server."

DevOps reduces this gap by making both sides collaborate across the whole software lifecycle.

## 1.3 Traditional approach vs DevOps approach

**Traditional (handoff-based) approach**

```text
┌─────────────┐   ┌─────────────┐   ┌─────────────┐   ┌─────────────┐   ┌─────────────┐
│ Development │ → │   Testing   │ → │ Operations  │ → │ Deployment  │ → │ Production  │
└─────────────┘   └─────────────┘   └─────────────┘   └─────────────┘   └─────────────┘
      Work is "thrown over the wall" from one team to the next.
      Result: delays, late feedback, blame, and errors.
```

**DevOps approach**

```text
                ┌──────────────────────────────────────────────┐
                │                  DevOps                      │
                │                                              │
                │        Development  ⇄  Operations            │
                │                                              │
                │   Collaboration • Automation                 │
                │   Shared responsibility • Continuous feedback│
                └──────────────────────┬───────────────────────┘
                                       ↓
                           Fast, reliable software delivery
```

| | Traditional silos | DevOps |
|---|---|---|
| Team structure | Separate Dev and Ops | Cross-functional, collaborating teams |
| Responsibility | Handed off between teams | Shared ("you build it, you run it" mindset) |
| Releases | Large, infrequent | Small, frequent |
| Feedback | Late | Continuous |
| Process | Mostly manual | Automated |
| Problem solving | Delays and blame | Faster resolution through shared knowledge |

## 1.4 Roles in a DevOps culture

DevOps changes how people work together:

- **Faster resolution** – issues are detected and fixed quickly through shared knowledge.
- **Higher-quality releases** – automated testing and continuous feedback.
- **Culture of accountability** – collective ownership of customer value, including shared on-call responsibility.

> "DevOps" is also used as a job title (DevOps Engineer). That role usually focuses on building and maintaining pipelines, automation and infrastructure, but the *practice* of DevOps belongs to the whole team.

## 1.5 Why is DevOps needed?

Consider an application made of a backend, a database, a cache, background workers, a web server and an application server. Writing the code is only one part of delivery. The application must also be **tested, packaged, deployed, configured, monitored and maintained**.

When those activities are done manually or by disconnected teams, delivery becomes slow and error-prone. DevOps introduces **collaboration and automation** so the process is consistent, repeatable and efficient.

---

# 2. DevOps Main Objectives

The primary goals of DevOps are **Speed, Reliability and Scalability**, supported by **Collaboration, Automation, Quality and Agility**.

```text
        ┌─────────┐        ┌─────────────┐        ┌─────────────┐
        │  SPEED  │        │ RELIABILITY │        │ SCALABILITY │     ← The three pillars
        └────┬────┘        └──────┬──────┘        └──────┬──────┘
             │                    │                      │
   ┌─────────┴──────┬─────────────┴───────┬──────────────┴────┐
   │ Collaboration  │     Automation      │  Quality  │ Agility │   ← The enablers
   └────────────────┴─────────────────────┴───────────┴─────────┘
```

## 2.1 The three pillars

| Pillar | What it means | Examples |
|--------|---------------|----------|
| **Speed** | Shorten the time from idea to running software | Shorter delivery cycles, rapid response to issues and feedback |
| **Reliability** | Software and systems behave consistently | Fewer manual errors, stable systems, quick recovery |
| **Scalability** | Systems can grow or shrink with demand | Adapt to market changes, high availability, flexible infrastructure |

## 2.2 The four enablers

| Enabler | What it means |
|---------|---------------|
| **Collaboration** | Dev, Ops, QA and Security share goals and responsibility |
| **Automation** | Build, test, deploy, configure and monitor without repetitive manual steps |
| **Quality** | Continuously improve processes and product quality through testing and feedback |
| **Agility** | Respond rapidly to changing market and customer needs |

## 2.3 Summary of objectives

| Objective | Explanation |
|-----------|-------------|
| Faster delivery | Release small changes more often and more efficiently |
| Automation | Reduce repetitive manual work and human error |
| Reliability and consistency | Same behaviour in development, testing and production |
| Fast feedback | Find problems early through tests, logs and monitoring |
| Scalability | Handle growth and demand changes smoothly |
| Collaboration | Shared responsibility across teams |
| Continuous improvement | Learn from users, tests, monitoring and incidents |

---

# 3. DevOps and Software Development Life Cycle (SDLC)

## 3.1 What is the SDLC?

**SDLC (Software Development Life Cycle)** is a structured description of the stages used to plan, create, test, release and maintain software.

1. **Plan** – requirements, scope, priorities
2. **Develop / Code** – design and write the application
3. **Build** – compile and package the application
4. **Test** – verify it works as expected
5. **Release** – prepare the version for delivery
6. **Deploy** – put it into an environment
7. **Operate** – run and maintain it
8. **Monitor** – observe performance, availability and errors
9. **Feedback** – use findings to plan improvements

## 3.2 Traditional SDLC

```text
Planning → Development → Testing → Release → Deployment → Operations
```

Each stage usually finishes before the next begins, with **hand-offs** in between. This causes waiting time, late discovery of defects and slow feedback.

## 3.3 DevOps lifecycle (the infinity loop)

DevOps turns the straight line into a **continuous loop**. The left side is "Dev" and the right side is "Ops":

```text
        ┌────────── DEV ──────────┐     ┌────────── OPS ──────────┐
        │                         │     │                         │
        │   Plan → Develop → Build│ ⇄   │ Release → Deploy        │
        │              ↓          │     │            ↓            │
        │            Test         │     │   Operate ← Monitor     │
        └─────────────────────────┘     └─────────────────────────┘
                     ↑                               │
                     └───── Continuous feedback ─────┘
                         & real-time insights
```

Benefits shown in the slides:

- **No hand-off delays** – work flows continuously between stages.
- **Early defect detection** – automated tests find problems sooner.
- **Rapid and safe delivery** – small, tested, repeatable releases.

## 3.4 Does DevOps replace the SDLC?

**No.** The SDLC describes *what stages exist*. DevOps improves *how teams collaborate and automate across those stages*. DevOps also pairs well with Agile development (see [Section 9.5](#95-agile-vs-devops)).

---

# 4. Continuous Integration & Deployment (CI/CD)

**CI/CD** is the set of practices that automates integrating, validating, releasing and deploying software. The pipeline is often called the **heartbeat of DevOps**.

```text
 Code Commit → [ CI: Build → Test ] → [ CD: Release → Deploy → Operate ] → Production
                                                     ↑                         │
                                                     └──── Rollback ◄──────────┘
```

## 4.1 Continuous Integration (CI)

**Continuous Integration** means developers frequently merge code changes into a shared repository, and every change is automatically **built and tested**.

```text
Developers commit code
        ↓
Shared repository (e.g., GitHub)
        ↓
Automated pipeline:  Build (compile & package)
                       → Test (unit & integration)
                       → Integrate (merge & verify)
        ↓
Feedback: pass or fail  ──→ back to the developer (rapid feedback loop)
```

**Key outcomes**

- **Deployable codebase** – always ready for the next stage (CD).
- **Reduced risk** – small, frequent merges are easier to fix than big, rare ones.
- **Collective ownership** – the team shares responsibility for the code.

**Popular CI tools:** Jenkins, GitHub Actions, GitLab CI.

## 4.2 Continuous Delivery

Every change is automatically built, tested and **prepared for release**. A human still approves or triggers the production release.

```text
Code → Build → Test → Package → Ready for release → Manual approval → Production
```

## 4.3 Continuous Deployment

Every change that passes the pipeline is **automatically deployed to production**, with no manual approval for each change.

```text
Code → Build → Test → Package → Automatic deployment → Production
```

**Benefits:** faster releases (small, frequent updates), reduced human error, quick **rollback** from failures, improved Dev/Ops collaboration, and faster time-to-market.

**Popular CD tools:** Jenkins, GitHub Actions, GitLab CI, CircleCI, Argo CD.

## 4.4 Comparison

| Practice | Main purpose | Production approval |
|----------|--------------|---------------------|
| **Continuous Integration** | Merge code frequently and validate it automatically | Not applicable |
| **Continuous Delivery** | Keep validated changes always ready to release | Usually required (manual) |
| **Continuous Deployment** | Automatically release every passing change | Not required |

> **Note:** "CD" can mean either *Continuous Delivery* or *Continuous Deployment*, depending on context. Always check which one is meant.

## 4.5 What is a pipeline?

A **pipeline** is an automated sequence of steps (build, test, scan, package, deploy) that every change passes through. A failed step stops the pipeline and notifies the team.

---

# 5. Containers and Virtual Development

## 5.1 Why isolate environments?

An application may work on one machine and fail on another because the environments differ:

```text
Developer machine              Production server
-----------------              -----------------
Python 3.12                    Python 3.10
Dependency version A           Dependency version B
System library A               System library B
```

Differences in runtime versions, libraries and configuration cause the classic "works on my machine" problem. Virtual environments, containers and virtual machines each provide a different level of **isolation** to solve it.

## 5.2 What is a container?

A **container** is an isolated environment that runs an application together with the files and dependencies it needs. It **shares the host operating system's kernel**. A **container image** is the packaged template used to create containers.

```text
┌────────────────────────────────────┐
│           Container Image          │
│  ┌──────────────────────────────┐  │
│  │ Application code             │  │
│  │ Dependencies / libraries     │  │
│  │ Runtime                      │  │
│  │ Required files               │  │
│  └──────────────────────────────┘  │
└────────────────────────────────────┘
                 ↓
         Container Engine (e.g., Docker)
                 ↓
         Running Container
```

## 5.3 What is a virtual machine (VM)?

A **VM** is a software-based computer with its **own guest operating system** running on virtualized hardware. A **hypervisor** creates and manages VMs.

```text
┌───────────────────────────────────────────┐
│ Hardware                                  │
│  ┌─────────────────────────────────────┐  │
│  │ Host OS (or bare-metal hypervisor)  │  │
│  ├─────────────────────────────────────┤  │
│  │ Hypervisor                          │  │
│  └───────────┬─────────────┬───────────┘  │
│        ┌─────┴─────┐ ┌─────┴─────┐        │
│        │   VM 1    │ │   VM 2    │        │
│        │ App       │ │ App       │        │
│        │ Libs/Bins │ │ Libs/Bins │        │
│        │ Guest OS  │ │ Guest OS  │        │
│        └───────────┘ └───────────┘        │
└───────────────────────────────────────────┘
```

## 5.4 Container architecture

```text
┌───────────────────────────────────────────────┐
│ Hardware                                      │
│  ┌─────────────────────────────────────────┐  │
│  │ Host OS (shared kernel)                 │  │
│  ├─────────────────────────────────────────┤  │
│  │ Container Engine (e.g., Docker)         │  │
│  ├───────────────┬───────────────┬─────────┤  │
│  │ Container 1   │ Container 2   │ Cont. 3 │  │
│  │ App+Libs/Bins │ App+Libs/Bins │ App+Libs│  │
│  └───────────────┴───────────────┴─────────┘  │
└───────────────────────────────────────────────┘
```

## 5.5 Virtual machines vs containers

| Feature | Virtual Machine | Container |
|---------|-----------------|-----------|
| Operating system | Own guest OS per VM | Shares the host OS kernel |
| Size | Larger (GBs) | Smaller (often MBs) |
| Startup | Slower (minutes) | Faster (seconds) |
| Overhead | Higher | Lower; denser utilization |
| Isolation | Strong (virtualized hardware) | Process and filesystem level |
| Portability | Moderate | High ("same app runs everywhere") |
| Typical use | Full OS environments, strong workload separation | Portable application services, microservices |

Neither is "better" in every case. The choice depends on compatibility, security, isolation and operational needs. Many organizations run **containers inside VMs**.

**Key benefit of containers:** simplified dependency management and scaling across laptops, data centers and clouds. **Docker** is the most popular container tool.

## 5.6 Virtual development environments

A **virtual development environment** isolates project dependencies so different projects can use different package versions without conflict.

```text
                Development Machine
                        │
             ┌──────────┴──────────┐
             ↓                     ↓
         Project A             Project B
             │                     │
       Virtual Env A         Virtual Env B
             │                     │
        Django 4.x            Django 5.x
```

| Isolation type | What it isolates |
|----------------|------------------|
| Python virtual environment (`venv`) | Python packages only |
| Container | Application, dependencies and runtime environment (shares host kernel) |
| Virtual machine | A complete guest operating system |

## 5.7 Container orchestration (preview)

Running many containers across many servers needs a manager for scheduling, scaling, networking and self-healing. This is called **container orchestration**. **Kubernetes** is the most widely used orchestrator and is covered in a later module.

---

# 6. Cloud Providers

## 6.1 What is cloud computing?

**Cloud computing** delivers computing resources — servers, storage, databases, networking and managed platforms — **over a network (usually the internet)**, on demand. Instead of buying and maintaining all hardware, organizations **rent** what they need from a cloud provider. (Module 2 covers cloud fundamentals and Module 8 covers AWS in detail.)

## 6.2 Why cloud matters to DevOps

| Benefit | Explanation |
|---------|-------------|
| **On-demand, automated resources** | Spin up identical environments in minutes using APIs, which fits DevOps automation |
| **Elastic scalability & cost efficiency** | Scale up or down with user demand; pay-as-you-go pricing |
| **Global availability & resilience** | Use multiple regions and availability zones for high availability and business continuity |

## 6.3 Major cloud providers

1. **AWS** – Amazon Web Services
2. **Microsoft Azure**
3. **GCP** – Google Cloud Platform

## 6.4 Common service categories

| Category | Purpose |
|----------|---------|
| Compute | Processing power to run applications |
| Storage | Files, objects, backups and data |
| Database | Managed database services |
| Networking | Connect systems and control traffic |
| Identity & Security | Users, permissions and protection |
| Containers | Container registries and container/Kubernetes services |
| Serverless | Run code without managing servers directly |
| Monitoring | Metrics, logs and alerts |

## 6.5 Equivalent services (examples)

| Category | AWS | Azure | GCP |
|----------|-----|-------|-----|
| Virtual machines | Amazon EC2 | Azure Virtual Machines | Compute Engine |
| Object storage | Amazon S3 | Azure Blob Storage | Cloud Storage |
| Serverless functions | AWS Lambda | Azure Functions | Cloud Functions / Cloud Run functions |
| Container registry | Amazon ECR | Azure Container Registry | Artifact Registry |
| Managed Kubernetes | Amazon EKS | Azure Kubernetes Service (AKS) | Google Kubernetes Engine (GKE) |

These services serve similar purposes, but features, configuration, pricing and integrations differ. Always check current provider documentation.

## 6.6 Cloud service models (preview)

| Model | You manage | Example |
|-------|------------|---------|
| **IaaS** (Infrastructure as a Service) | OS, runtime, applications | Virtual machines |
| **PaaS** (Platform as a Service) | Application and data | Managed app platforms |
| **SaaS** (Software as a Service) | Just use the software | Email, CRM tools |

## 6.7 What teams do with the cloud in DevOps

- Provision infrastructure and environments
- Host and deploy applications
- Store data and files
- Configure networking and security
- Run containerized workloads
- Automate infrastructure changes
- Monitor application and infrastructure health

---

# 7. Scripting

## 7.1 What is scripting?

**Scripting** means writing small programs or command sequences to **automate tasks**. In DevOps, scripts reduce repetitive manual work, make operations **repeatable**, and act as **executable documentation** — the steps are written down and can be run again by anyone.

## 7.2 Common scripting languages

| Language | Typical use |
|----------|-------------|
| **Bash** | Linux/Unix command-line automation and system administration |
| **Python** | Automation, API calls, cloud operations, log processing, monitoring utilities |
| **PowerShell** | Windows administration; also cross-platform automation |

## 7.3 Where scripting is used

```text
                         Scripting
                             │
     ┌───────────┬───────────┼───────────┬────────────┐
     ↓           ↓           ↓           ↓            ↓
Server patching  Backup    Log rotation  Deployment   Health checks &
(automated       verification  & mgmt    checks       monitoring
 updates)        (data integrity)        (pre/post release)
```

Typical tasks:

- Automated server patching and updates
- Verifying that backups succeeded and are usable
- Rotating and cleaning logs
- Pre- and post-deployment checks
- Checking application health
- Calling APIs and automating cloud tasks

## 7.4 Key benefits

- **Reduced human error** – consistent execution every time
- **Engineer efficiency** – people focus on high-value work
- **Executable documentation** – processes document themselves

## 7.5 A tiny example (for illustration only)

You do not need to master this now; Linux and scripting modules come later.

```bash
#!/bin/bash
# Simple health check: report whether a website responds
URL="https://example.com"

if curl -s --head "$URL" | head -n 1 | grep -q "200"; then
  echo "OK: $URL is up"
else
  echo "ALERT: $URL is not responding"
fi
```

## 7.6 Why Python is popular in DevOps

Python has a readable syntax and a large library ecosystem, which makes it well suited to API interaction, cloud automation, log processing and monitoring tools.

---

# 8. Configuration Management Tools

## 8.1 What is configuration management?

**Configuration management** is the practice of defining, applying and maintaining the **desired configuration** of systems in a consistent, controlled way.

Imagine managing many servers. Each might need a web server installed, services enabled, config files in the right place, users and permissions set, and packages installed. Doing this by hand leads to differences and mistakes. Configuration management tools **automate and standardize** it.

```text
   Code                  Configuration Management           Infrastructure
(Infrastructure   →            Engine              →       in the Desired State
   as Code)             (Ansible, Puppet, Chef, Salt)      (consistent servers)
```

## 8.2 Why is it important?

| Benefit | Meaning |
|---------|---------|
| **Consistency** | Systems are configured predictably |
| **Automation** | Less repetitive manual setup |
| **Scalability** | Easier to manage many servers |
| **Maintainability** | Changes are controlled and trackable |
| **Repeatability** | A known configuration can be recreated |

## 8.3 Core ideas

| Idea | Explanation |
|------|-------------|
| **Idempotent provisioning** | Running the same configuration multiple times gives the same end state, regardless of the starting state |
| **Preventing configuration drift** | Automation keeps systems matching the desired state and avoids unintended manual changes |
| **Immutable infrastructure** | Replace servers with new pre-configured ones instead of patching them in place |
| **Review & collaboration** | Infrastructure changes go through version control and pull requests, like application code |

## 8.4 Common tools

| Tool | Description |
|------|-------------|
| **Ansible** | Agentless automation for configuration, deployment and orchestration; uses YAML playbooks |
| **Puppet** | Declarative configuration management using an agent model |
| **Chef** | Configuration automation using code ("recipes" and "cookbooks") |
| **Salt (SaltStack)** | Configuration management and remote execution |
| **Terraform** | Infrastructure provisioning tool (creates cloud resources) — see note below |

> **Configuration management vs provisioning:** *Provisioning* tools such as **Terraform** create infrastructure (servers, networks, databases). *Configuration management* tools such as **Ansible** set up what runs on that infrastructure. In practice they are often used together, and both belong to **Infrastructure as Code**.

## 8.5 Conceptual Ansible architecture

```text
           ┌────────────────────────┐
           │  Ansible Control Node  │
           │  (playbooks, inventory)│
           └───────────┬────────────┘
                       │  (usually over SSH)
        ┌──────────────┼──────────────┐
        ↓              ↓              ↓
   ┌─────────┐    ┌─────────┐    ┌─────────┐
   │ Server 1│    │ Server 2│    │ Server 3│
   └─────────┘    └─────────┘    └─────────┘
```

Ansible usually needs no agent on the managed machines; the control node applies the defined configuration to them.

## 8.6 A tiny Ansible playbook (for illustration only)

```yaml
- name: Configure web servers
  hosts: webservers
  become: true
  tasks:
    - name: Install nginx
      ansible.builtin.package:
        name: nginx
        state: present

    - name: Ensure nginx is running
      ansible.builtin.service:
        name: nginx
        state: started
        enabled: true
```

Notice that it describes the **desired state** ("nginx present and running"), not step-by-step commands.

---

# 9. Supporting Concepts You Will Meet Next

These topics are not separate lecture items, but they are essential to understanding the rest of the course.

## 9.1 Version control (Git)

**Version control** records every change to code (and configuration) so teams can collaborate, review, track history and roll back. **Git** is the standard tool; **GitHub**, **GitLab** and **Bitbucket** host repositories. Almost every DevOps practice — CI/CD, Infrastructure as Code, configuration management — starts from a Git repository.

## 9.2 Infrastructure as Code (IaC)

**IaC** means defining infrastructure (servers, networks, databases) in **code files** instead of clicking through consoles. IaC files are stored in Git, reviewed, tested and versioned like application code. Tools: **Terraform**, **AWS CloudFormation**, **Ansible**, **Pulumi**.

## 9.3 Monitoring, logging and observability

You cannot improve what you cannot see.

| Concept | Purpose |
|---------|---------|
| **Monitoring** | Track health and performance with metrics and alerts |
| **Logging** | Record events and errors for troubleshooting |
| **Observability** | Understand the internal state of a system from its metrics, logs and traces |

Common tools: Prometheus, Grafana, ELK/EFK stack, Datadog, cloud-native monitoring services. Monitoring closes the feedback loop of the DevOps lifecycle.

## 9.4 DevSecOps

**DevSecOps** adds **security** to every stage of the lifecycle instead of checking it only at the end ("shift left"). Examples: dependency scanning, container image scanning, secrets management, and security checks inside the CI/CD pipeline.

## 9.5 Agile vs DevOps

| | Agile | DevOps |
|---|-------|--------|
| Focus | How teams **plan and build** software iteratively | How software is **delivered and operated** continuously |
| Main collaboration | Developers, product owners, customers | Developers, operations, QA, security |
| Typical practices | Sprints, user stories, retrospectives | CI/CD, IaC, monitoring, automation |

They are **complementary**: Agile speeds up development; DevOps speeds up delivery and operations.

## 9.6 Measuring DevOps success (DORA metrics)

| Metric | Question it answers |
|--------|---------------------|
| **Deployment frequency** | How often do we release? |
| **Lead time for changes** | How long from commit to running in production? |
| **Change failure rate** | What percentage of releases cause problems? |
| **Time to restore service** | How quickly do we recover from failures? |

High-performing teams deploy more often **and** have fewer failures and faster recovery — speed and stability improve together.

## 9.7 The CALMS framework

A popular way to remember what DevOps involves:

| Letter | Meaning |
|--------|---------|
| **C**ulture | Collaboration and shared responsibility |
| **A**utomation | Automate repetitive work |
| **L**ean | Small batches, remove waste |
| **M**easurement | Use data to improve |
| **S**haring | Share knowledge and feedback |

## 9.8 Common DevOps toolchain

| Stage | Example tools |
|-------|---------------|
| Plan | Jira, Azure Boards, Trello |
| Code | Git, GitHub, GitLab |
| Build / CI | Jenkins, GitHub Actions, GitLab CI |
| Test | JUnit, pytest, Selenium |
| Package | Docker, container registries |
| Deploy / CD | Argo CD, CircleCI, Jenkins |
| Infrastructure | Terraform, Ansible, Kubernetes |
| Monitor | Prometheus, Grafana, ELK |

Tools change over time. **Concepts matter more than any single tool.**

---

# 10. How Everything Fits Together

```text
┌──────────────────────────┐
│ Development              │  Write application code
└────────────┬─────────────┘
             ↓
┌──────────────────────────┐
│ Version Control (Git)    │  Store and review changes
└────────────┬─────────────┘
             ↓
┌──────────────────────────┐
│ CI/CD Pipeline           │  Build, test, package, release
└────────────┬─────────────┘
             ↓
┌──────────────────────────┐
│ Containers               │  Package app with dependencies
└────────────┬─────────────┘
             ↓
┌──────────────────────────┐
│ Cloud / Servers          │  Host and scale the application
└────────────┬─────────────┘
             ↓
┌──────────────────────────┐
│ Configuration Mgmt & IaC │  Keep infrastructure consistent
└────────────┬─────────────┘
             ↓
┌──────────────────────────┐
│ Monitoring & Feedback    │  Observe, learn, improve
└────────────┬─────────────┘
             │
             └──────────────► Back to planning the next change

   Scripting and automation run through every stage.
   Culture and collaboration connect all of it.
```

**In one sentence:** DevOps is **culture first, tools second** — automation and collaboration are the engines, CI/CD is the heartbeat, containers and cloud provide agility, and united teams deliver fast, reliable and continuously improving software.

---

# 11. Learning Roadmap

| Order | Module | What you will learn |
|-------|--------|---------------------|
| 1 | **Introduction to DevOps** (this module) | Concepts and big picture |
| 2 | Cloud Computing | Cloud fundamentals and providers |
| 3 | Linux Basics | Command line, files, permissions, processes |
| 4 | Scripting (Bash/Python) | Automating tasks |
| 5 | REST APIs using Flask and MongoDB | Building REST APIs and storing data in MongoDB |
| 6 | Git & version control | Collaboration and history |
| 7 | Docker & containers | Building and running containers |
| 8 | AWS | AWS Services and Deployment |
| 9 | Kubernetes | Container orchestration |
| 10 | Terraform & Ansible | Infrastructure as Code and configuration management |
| 11 | CI/CD | Building and managing pipelines |

*(Follow the order in your course player; this table is a suggested path.)*

---

# 12. Glossary

| Term | Meaning |
|------|---------|
| **DevOps** | Culture, practices and tools connecting development and operations |
| **SDLC** | Software Development Life Cycle |
| **CI** | Continuous Integration |
| **CD** | Continuous Delivery or Continuous Deployment (depends on context) |
| **Pipeline** | Automated sequence of steps to build, test, package and release software |
| **Rollback** | Returning to a previous working version after a failed release |
| **Container** | Isolated application runtime sharing the host OS kernel |
| **Container image** | Packaged template used to create containers |
| **Docker** | Popular container platform |
| **Kubernetes** | Container orchestration platform |
| **VM** | Virtual Machine with its own guest OS |
| **Hypervisor** | Software that creates and manages VMs |
| **Cloud computing** | On-demand computing resources delivered over a network |
| **AWS / Azure / GCP** | The three major cloud providers |
| **Region / Availability Zone** | Geographic location / isolated data-center group within a cloud |
| **Scripting** | Writing commands or programs to automate tasks |
| **Configuration management** | Maintaining consistent desired configuration across systems |
| **Idempotent** | Running an operation repeatedly gives the same result |
| **Configuration drift** | Systems gradually diverging from their intended configuration |
| **Immutable infrastructure** | Replacing servers instead of modifying them |
| **IaC** | Infrastructure as Code |
| **Ansible** | Agentless automation and configuration management tool |
| **Terraform** | Infrastructure provisioning tool |
| **Git** | Distributed version control system |
| **Observability** | Understanding system state from metrics, logs and traces |
| **DevSecOps** | DevOps with security built into every stage |
| **DORA metrics** | Four metrics that measure software delivery performance |

---

# 13. Interview Questions and Answers

**Q1. What is DevOps?**
A set of cultural practices, processes and tools that bring development and operations together to improve collaboration and automate software delivery, so releases are faster and more reliable.

**Q2. Is DevOps a tool?**
No. It is a culture and set of practices. Tools such as Git, Docker, Jenkins, GitHub Actions, Terraform and Ansible support DevOps workflows.

**Q3. What are the main objectives of DevOps?**
Speed, reliability and scalability, supported by collaboration, automation, quality, agility, fast feedback and continuous improvement.

**Q4. What problem does DevOps solve?**
It removes the silos and manual hand-offs between Dev and Ops that cause delays, errors and the "it works on my machine" problem.

**Q5. What is the SDLC, and does DevOps replace it?**
The SDLC describes the stages of planning, building, testing, releasing and maintaining software. DevOps does not replace it; it improves collaboration and automation across those stages.

**Q6. What is Continuous Integration?**
Frequently merging code into a shared repository and validating each change with automated builds and tests.

**Q7. What is the difference between Continuous Delivery and Continuous Deployment?**
Continuous Delivery keeps validated changes ready to release, usually with manual production approval. Continuous Deployment releases every passing change to production automatically.

**Q8. What is a pipeline?**
An automated sequence of steps (build, test, package, deploy) that every code change passes through.

**Q9. What is a container?**
An isolated application runtime that shares the host OS kernel and packages the app with the dependencies it needs.

**Q10. What is the difference between a VM and a container?**
A VM runs its own guest OS on virtualized hardware (heavier, slower to start, strong isolation). A container shares the host kernel (lightweight, fast, portable).

**Q11. What is cloud computing, and why is it important for DevOps?**
It provides on-demand compute, storage, databases and networking over a network. It lets teams create environments quickly through APIs, scale elastically, and automate infrastructure.

**Q12. Name the three major cloud providers.**
AWS, Microsoft Azure and Google Cloud Platform (GCP).

**Q13. Why is scripting important in DevOps?**
It automates repetitive tasks (patching, backups, log management, deployment checks, health checks), reduces human error and serves as executable documentation.

**Q14. What is configuration management?**
Defining and maintaining the desired configuration of systems consistently. Tools include Ansible, Puppet, Chef and Salt.

**Q15. What is Ansible?**
An agentless automation tool for configuration management, deployment and orchestration, using YAML playbooks.

**Q16. What is Infrastructure as Code?**
Managing infrastructure through versioned code files instead of manual console work, so it is repeatable and reviewable.

**Q17. What is configuration drift?**
When systems gradually differ from their intended configuration because of manual or untracked changes.

**Q18. How do you measure DevOps success?**
Using DORA metrics: deployment frequency, lead time for changes, change failure rate and time to restore service.

---

# 14. Self-Check Quiz

Try answering before reading the answers.

1. What does DevOps combine, and why is it "culture first, tools second"?
2. Name the three pillars and four enablers of DevOps.
3. Why is the DevOps lifecycle drawn as a loop?
4. In which practice does a human approve the production release: Continuous Delivery or Continuous Deployment?
5. Which is heavier and slower to start: a VM or a container? Why?
6. Give two benefits of using a public cloud for DevOps.
7. Give three tasks that are good candidates for scripting.
8. What is the difference between Terraform and Ansible?

<details>
<summary><strong>Answers</strong></summary>

1. Development + Operations. Culture (collaboration, shared responsibility) comes first because tools alone do not remove silos.
2. Pillars: speed, reliability, scalability. Enablers: collaboration, automation, quality, agility.
3. Because monitoring and feedback from operations flow back into planning the next change.
4. Continuous Delivery.
5. A VM, because it runs a full guest OS, while containers share the host kernel.
6. Any two: on-demand resources, elastic scaling, pay-as-you-go cost, global availability and resilience.
7. Any three: server patching, backup verification, log rotation, deployment checks, health checks.
8. Terraform provisions infrastructure (creates resources); Ansible configures what runs on it. They are often used together.

</details>

---

# 15. Module Summary

1. **DevOps** connects development and operations through collaboration, automation and shared responsibility — culture first, tools second.
2. **Objectives:** speed, reliability and scalability, enabled by collaboration, automation, quality and agility.
3. **SDLC and DevOps:** DevOps turns the linear SDLC into a continuous loop with no hand-off delays, early defect detection and rapid, safe delivery.
4. **CI/CD** automates integration, testing, release and deployment; Continuous Delivery keeps a manual approval, Continuous Deployment does not.
5. **Containers** give portable, lightweight, isolated environments; **VMs** include a full guest OS; both have their place.
6. **Cloud providers** (AWS, Azure, GCP) supply on-demand, elastic, globally available infrastructure that suits DevOps automation.
7. **Scripting** (Bash, Python, PowerShell) automates repetitive work and acts as executable documentation.
8. **Configuration management** (Ansible, Puppet, Chef, Salt) keeps systems consistent, prevents drift and works hand in hand with Infrastructure as Code.
9. **Version control, monitoring, DevSecOps and metrics** complete the picture and prepare you for the hands-on modules ahead.

> **Next up:** Module 2 — Cloud Computing, followed by Module 3 — Linux Basics.