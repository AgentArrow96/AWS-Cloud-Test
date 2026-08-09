# Intuitive Explanation Covering Module 1 - 8 of Distributed & Parallel Computing

---


<details>
<summary><strong>Module 1: Cloud Concepts Overview — Intuitive and Narrative Explanation</strong></summary>

# Module 1: Cloud Concepts Overview — Intuitive and Narrative Explanation

Module 1 is basically the **“why cloud exists”** chapter.

Before AWS teaches you EC2, S3, VPC, IAM, databases, and all the alphabet soup, this module answers four bigger questions:

1. **What is cloud computing?**
2. **Why would a company use cloud instead of its own data center?**
3. **What exactly is AWS?**
4. **How does a company actually prepare itself to move to the cloud?**

Those are exactly the four major sections in the module. 

---

# 1. Start with the big idea

Imagine a company called **QuickMart**.

QuickMart wants to launch an online store.

In the traditional world, management might say:

> “We need servers.”

So the IT team must:

```text
Estimate how much traffic will come
↓
Choose servers
↓
Get budget approval
↓
Order hardware
↓
Wait for delivery
↓
Install servers
↓
Configure networking
↓
Install operating systems
↓
Maintain everything
```

That may take weeks or months.

And the really amusing part is that their original estimate may be completely wrong.

If they buy too much:

```text
Demand:
████

Capacity:
████████████

Unused:
████████
```

Money is wasted.

If they buy too little:

```text
Demand:
████████████

Capacity:
████

Result:
Site struggles or fails
```

Cloud computing exists largely because companies got tired of playing this very expensive guessing game.

---

# 2. What is cloud computing?

The module gives a very important definition:

> Cloud computing is the **on-demand delivery** of compute power, databases, storage, applications, and other IT resources **via the internet**, with **pay-as-you-go pricing**. 

There are three phrases you should absolutely notice:

```text
ON DEMAND
VIA THE INTERNET
PAY AS YOU GO
```

Those three phrases explain most of cloud computing.

---

# 3. What does “on demand” mean?

Suppose QuickMart suddenly needs five servers.

Traditional approach:

> “Submit purchase request. Wait. Procurement is investigating the emotional state of the invoice.”

Cloud:

> “Create five virtual servers now.”

That is **on-demand access**.

You don't normally need to buy a physical server first.

Conceptually:

```text
Need resource
↓
Request resource
↓
Resource becomes available
```

That speed becomes one of the major cloud advantages later in the chapter.

---

# 4. What does “via the internet” mean?

The resources do not need to physically sit inside your company's building.

You can access computing services remotely.

For example:

```text
Your laptop
    ↓
Internet
    ↓
AWS
    ↓
Server / database / storage
```

You are consuming IT infrastructure as a service.

---

# 5. What does “pay-as-you-go” mean?

Instead of necessarily purchasing a large amount of hardware before you know how much you need, cloud lets you pay based more closely on usage.

Traditional:

```text
Buy server first
↓
Use it later
```

Cloud:

```text
Use resource
↓
Pay for usage
```

This is the financial idea that Module 2 expands much further.

---

# 6. Infrastructure as hardware vs infrastructure as software

Page 7 introduces one of the best conceptual ideas in the module:

> Cloud computing lets you stop thinking of infrastructure only as **hardware** and instead think of it as **software**. 

This sounds abstract, but it is actually simple.

## Traditional infrastructure

Suppose you need another server.

A server is a physical thing.

You might need to:

```text
Buy it
Ship it
Rack it
Wire it
Configure it
Maintain it
```

## Cloud infrastructure

A virtual server can instead be created through:

```text
Console
Command
Script
API
```

So infrastructure begins behaving more like software.

---

# 7. Why “infrastructure as software” matters

Imagine increasing capacity.

### Hardware world

You want 20 additional servers.

That involves physical procurement.

### Cloud world

You can create additional resources programmatically.

This means infrastructure can become:

* faster to deploy;
* easier to modify;
* easier to automate;
* more flexible.

The module contrasts the traditional computing model with cloud specifically in this way. Traditional infrastructure requires space, staff, physical security, planning and capital expenditure, while cloud infrastructure can change more quickly and flexibly. 

---

# 8. “Undifferentiated heavy lifting”

Page 9 says cloud can eliminate **undifferentiated heavy-lifting tasks**. 

That phrase sounds like AWS hired a philosopher, but the idea is straightforward.

QuickMart wants to sell products.

Its competitive advantage probably does not come from:

```text
Replacing broken hard drives
Installing rack equipment
Maintaining cooling systems
Running electrical infrastructure
```

Those things are necessary.

But they do not make QuickMart a better retailer.

AWS's argument is:

> Spend more effort on what makes your business unique, and less effort maintaining generic infrastructure.

---

# Section 1B: Cloud service models

# 9. IaaS, PaaS and SaaS

The module introduces three cloud service models:

```text
IaaS
PaaS
SaaS
```

The central difference is:

> **How much do you manage yourself?**

Page 10 shows the spectrum from more control to less control. 

The easiest analogy is food.

---

# 10. IaaS — Infrastructure as a Service

Imagine renting a kitchen.

The kitchen gives you:

```text
Building
Gas
Electricity
Oven
Fridge
```

But **you cook the food**.

That is roughly IaaS.

The cloud provider gives you infrastructure.

You still manage many things yourself.

Example later in AWS:

```text
Amazon EC2
```

With EC2, AWS provides the underlying infrastructure and virtual machine, but you still have substantial control over the operating system and configuration.

Memory:

```text
IaaS
= infrastructure provided
= most control of the three
```

---

# 11. PaaS — Platform as a Service

Now imagine a restaurant kitchen where much more is already prepared.

You mainly focus on:

```text
Your recipe
Your application
Your data
```

rather than building and maintaining the kitchen.

That is PaaS.

AWS examples you encounter later include services such as:

```text
AWS Elastic Beanstalk
```

The idea is:

> “I want to deploy my application without spending as much effort managing the underlying infrastructure.”

Memory:

```text
PaaS
= focus more on the application
= provider manages more underneath
```

---

# 12. SaaS — Software as a Service

Now imagine you do not cook at all.

You just go to the restaurant and eat.

The entire application is delivered to you.

That is SaaS.

Examples outside AWS might include services you simply use through a browser.

You normally do not manage:

```text
Server
Operating system
Runtime
Application infrastructure
```

You simply use the software.

Memory:

```text
SaaS
= finished software
= least infrastructure control
```

---

# 13. Service model spectrum

The clean mental picture is:

```text
MORE CONTROL
     ↓

IaaS
↓
PaaS
↓
SaaS

     ↓
LESS CONTROL
```

But the other side of that is:

```text
MORE YOU MANAGE
IaaS

LESS YOU MANAGE
SaaS
```

This becomes extremely important later in AWS security because **more control usually also means more responsibility**.

---

# 14. IaaS vs PaaS vs SaaS scenario thinking

If a question says:

> “The company wants maximum control over the operating system and virtual server.”

Think:

**IaaS**

If it says:

> “Developers want to focus on application code instead of managing the underlying infrastructure.”

Think:

**PaaS**

If it says:

> “Users simply access a finished application.”

Think:

**SaaS**

---

# Section 1C: Deployment models

# 15. Cloud deployment models

The module teaches three deployment models:

```text
Cloud
Hybrid
On-premises / private cloud
```



These answer a different question from IaaS/PaaS/SaaS.

Service models ask:

> **What level of service are you consuming?**

Deployment models ask:

> **Where does the computing environment live?**

Students often mix those up.

---

# 16. Cloud deployment

In a cloud model, workloads are deployed in a cloud environment such as AWS.

Conceptually:

```text
Company
   ↓
Internet
   ↓
AWS Cloud
```

The company does not need to host all the underlying physical infrastructure itself.

---

# 17. On-premises / private cloud

This means the organisation operates the infrastructure within its own environment.

Conceptually:

```text
Company building
│
├── Servers
├── Storage
├── Network
└── Private infrastructure
```

The organisation keeps more direct control but also carries much more infrastructure responsibility.

---

# 18. Hybrid deployment

Hybrid means:

> **Some workloads stay on-premises and some use the cloud.**

Example:

```text
Company data center
        ↕
      Network
        ↕
     AWS Cloud
```

This is extremely common conceptually because organisations rarely wake up on Tuesday and teleport their entire IT estate into AWS by lunch.

---

# 19. When would hybrid make sense?

Imagine a bank.

It may have:

```text
Old internal systems
Sensitive legacy databases
Existing data center infrastructure
```

But it also wants:

```text
Cloud scalability
New applications
Cloud backups
Analytics
```

So it uses both.

That is hybrid.

---

# 20. Don't confuse service model and deployment model

This distinction is exam-worthy.

```text
IaaS / PaaS / SaaS
→ WHO manages WHAT

Cloud / Hybrid / On-premises
→ WHERE the environment exists
```

---

# 21. AWS is not completely alien compared with traditional IT

Page 12 gives a very useful comparison between traditional IT and AWS. 

Traditional IT has:

```text
Firewalls
Routers
Servers
Storage
Databases
Administrators
```

AWS has equivalent cloud concepts such as:

```text
Security groups
Network ACLs
Amazon VPC
Amazon EC2
Amazon EBS
Amazon EFS
Amazon S3
Amazon RDS
IAM
```

So cloud computing does not erase the ideas of networking, servers, storage and security.

It changes **how those things are delivered and managed**.

---

# Section 2: Six advantages of cloud computing

This is probably one of the most examinable parts of Module 1.

The six advantages are:

1. Trade capital expense for variable expense
2. Benefit from massive economies of scale
3. Stop guessing capacity
4. Increase speed and agility
5. Stop spending money running and maintaining data centers
6. Go global in minutes 

You should know what each one actually means, not just chant them like an AWS ritual.

---

# 22. Advantage 1 — Trade capital expense for variable expense

Traditional IT often requires **capital expenditure**.

Suppose QuickMart wants a server farm.

Before earning anything, it might spend:

```text
RM500,000 servers
RM100,000 networking
RM100,000 storage
RM50,000 installation
```

That is a major upfront investment.

Cloud shifts toward **variable expense**.

Instead of buying everything upfront:

```text
Use resources
↓
Pay based on consumption
```

The page 15 diagram contrasts investment based on forecasts with paying for what is consumed. 

Memory:

```text
CAPEX
= buy infrastructure upfront

VARIABLE EXPENSE
= pay as usage occurs
```

---

# 23. Why this is useful

Imagine QuickMart fails after six months.

### On-premises

It may still own:

```text
100 servers
Network equipment
Storage equipment
```

which it no longer needs.

### Cloud

It can stop resources and reduce future usage.

So cloud decreases the need to gamble large amounts of money on uncertain future demand.

---

# 24. Advantage 2 — Massive economies of scale

AWS serves huge numbers of customers.

Because of that aggregate demand, AWS operates at a much larger scale than one ordinary company could.

Page 16 says AWS can achieve economies of scale and pass savings to customers. 

Think wholesale purchasing.

A person buying:

```text
1 server
```

has little purchasing leverage.

AWS operates enormous infrastructure.

So its per-unit economics can be different.

Memory:

```text
Huge AWS scale
↓
Lower unit economics
↓
Potential savings for customers
```

---

# 25. Advantage 3 — Stop guessing capacity

This one is particularly important.

With traditional infrastructure, companies must forecast future demand.

Suppose QuickMart predicts:

```text
Expected peak:
10,000 users
```

If it prepares capacity for:

```text
20,000 users
```

it overestimates.

Money is wasted.

If it prepares for:

```text
5,000 users
```

it underestimates.

Performance suffers.

The slide on page 17 explicitly contrasts **overestimated capacity**, **underestimated capacity**, and **scaling on demand**. 

---

# 26. Cloud solution to capacity guessing

Cloud allows capacity to scale more dynamically.

Conceptually:

```text
Low demand
→ fewer resources

High demand
→ more resources

Demand falls
→ reduce resources
```

So instead of guessing the theoretical maximum years in advance, the system can adapt more closely to real demand.

---

# 27. Advantage 4 — Increase speed and agility

Traditional infrastructure:

```text
Need server
↓
Approval
↓
Purchase
↓
Delivery
↓
Installation
↓
Configuration

Weeks
```

Cloud:

```text
Need server
↓
Launch

Minutes
```

Page 18 literally contrasts **weeks** with **minutes**. 

That speed matters because developers can experiment faster.

---

# 28. Why agility matters to business

Suppose QuickMart wants to test a new recommendation engine.

Traditional environment:

> “Infrastructure will be ready in six weeks.”

The idea may already be irrelevant by then.

Cloud:

> “Create the resources today.”

That makes experimentation cheaper and faster.

So agility is not just an IT benefit.

It can become a **business advantage**.

---

# 29. Advantage 5 — Stop spending money running data centers

A data center costs more than servers.

Page 19 illustrates costs such as:

```text
Payroll
Utilities
Maintenance
Landscaping
Hardware
```



The idea is that organisations can redirect resources away from generic infrastructure operation and toward their actual business.

For QuickMart:

```text
Less effort:
"How do we cool this server room?"

More effort:
"How do we improve customer experience?"
```

That is the real business argument.

---

# 30. Advantage 6 — Go global in minutes

Suppose QuickMart starts in Malaysia.

Then it gets customers in:

```text
Europe
United States
Japan
Australia
```

Traditional approach might require setting up international infrastructure.

Cloud lets the company deploy workloads in other AWS geographical locations far more quickly.

The page 20 diagram shows a world map and deployment across AWS Regions. 

Memory:

```text
New geographic market
↓
Deploy resources closer to users
↓
Global reach faster
```

---

# 31. The six advantages as one story

Imagine QuickMart moves to AWS.

### Before cloud

```text
Buy hardware upfront
Guess future demand
Wait weeks for servers
Maintain data center
Expand internationally slowly
```

### With cloud

```text
Pay based on consumption
Use AWS economies of scale
Scale according to demand
Launch resources quickly
Avoid much data-center heavy lifting
Deploy globally faster
```

That single before/after story covers all six advantages.

---

# 32. Six advantages memory shortcut

You can remember them as:

```text
MONEY
SCALE
CAPACITY
SPEED
DATA CENTER
GLOBAL
```

Expanded:

```text
Money
→ CapEx to variable expense

Scale
→ Economies of scale

Capacity
→ Stop guessing

Speed
→ Agility

Data center
→ Stop maintaining everything yourself

Global
→ Deploy worldwide quickly
```

---

# Section 3: What is AWS?

# 33. AWS in simple terms

The module defines AWS as a **secure cloud platform** offering a broad set of global cloud-based products.

It provides on-demand access to things such as:

```text
Compute
Storage
Networking
Database
Management tools
```

and AWS services are designed to work together like **building blocks**. 

That building-block analogy is excellent.

---

# 34. AWS as LEGO

Imagine AWS as a giant box of LEGO.

You may choose:

```text
EC2 → Compute
S3 → Storage
RDS → Database
VPC → Networking
IAM → Security / access
```

You combine the pieces to build an application.

AWS is not one enormous product.

It is a collection of services.

---

# 35. Simple AWS architecture

Page 26 shows a simple architecture consisting of:

```text
Users
↓
Amazon VPC
↓
Amazon EC2
↓
Amazon DynamoDB
↓
Amazon S3
```

The diagram groups them by categories:

```text
Networking → VPC
Compute    → EC2
Database   → DynamoDB
Storage    → S3
```



This is worth understanding because later modules simply zoom in on each block.

---

# 36. Core categories you should recognise

The slides list many categories, but for Cloud Foundations, some especially important ones are:

```text
Compute
Storage
Database
Networking and Content Delivery
Security, Identity and Compliance
Management and Governance
Cost Management
```

The module then lists the specific services covered later in the course. 

---

# 37. Important AWS service map

A useful mental map:

| Need                | Think         |
| ------------------- | ------------- |
| Virtual server      | EC2           |
| Object storage      | S3            |
| Block storage       | EBS           |
| Shared file storage | EFS           |
| Relational database | RDS           |
| NoSQL database      | DynamoDB      |
| Private network     | VPC           |
| Permissions         | IAM           |
| DNS                 | Route 53      |
| Content delivery    | CloudFront    |
| Monitoring          | CloudWatch    |
| Audit activity      | CloudTrail    |
| Cost analysis       | Cost Explorer |

You will learn the details in later modules.

Module 1 only wants you to understand that AWS has categories and services that work together.

---

# 38. Choosing an AWS service

Page 27 gives a crucial rule:

> The service selected depends on **business goals** and **technology requirements**. 

There is no universally “best AWS service.”

Example:

> “Which is better: EC2 or Lambda?”

That question is incomplete.

It depends on the workload.

It is like asking:

> “Which is better: a truck or a motorcycle?”

For transporting 20 tonnes?

Truck.

For slipping through Kuala Lumpur traffic?

Probably not the truck.

The requirement determines the service.

---

# 39. What is a web service?

Page 23 defines a web service as software available over the internet that uses standard formats such as XML or JSON for API request-response interactions. 

Think:

```text
Client
   ↓ request
Internet
   ↓
Web service
   ↓ response
Client
```

This is important because AWS services can be controlled through APIs rather than only through graphical screens.

---

# 40. Three ways to interact with AWS

The module teaches three primary ways:

```text
AWS Management Console
AWS CLI
AWS SDKs
```



---

# 41. AWS Management Console

This is the graphical interface.

Think:

```text
Browser
↓
Click buttons
↓
Configure AWS resources
```

Good for:

```text
Beginners
Manual configuration
Visual interaction
```

Memory:

```text
Console
= GUI
```

---

# 42. AWS CLI

CLI means **Command Line Interface**.

Instead of clicking:

```text
Create instance
```

you execute commands.

This is useful for:

```text
Automation
Scripts
Repeatable tasks
```

Memory:

```text
CLI
= commands/scripts
```

---

# 43. AWS SDK

SDK means **Software Development Kit**.

This lets application code interact directly with AWS.

Examples from the module include languages such as:

```text
Java
Python
```

So your application can programmatically say:

```text
Store this file in S3
Create a resource
Read a database record
```

Memory:

```text
SDK
= AWS from your application code
```

---

# 44. Console vs CLI vs SDK

Easy comparison:

| Method             | Think        |
| ------------------ | ------------ |
| Management Console | Click        |
| CLI                | Type command |
| SDK                | Write code   |

If a question says:

> “A developer wants to automate AWS operations through Python code.”

Think:

**SDK**

If it says:

> “An administrator wants to execute AWS commands in scripts.”

Think:

**CLI**

If it says:

> “A user wants a graphical interface.”

Think:

**Management Console**

---

# Section 4: AWS Cloud Adoption Framework

This is the part students often memorize badly.

AWS CAF is easier if you understand the problem it is trying to solve.

---

# 45. Why does AWS CAF exist?

Suppose QuickMart says:

> “We are moving to AWS tomorrow.”

The IT team may be ready.

But what about:

```text
Finance?
HR?
Security?
Management?
Operations?
Governance?
Training?
Policies?
Business strategy?
```

Cloud adoption is not merely:

> “Move the servers.”

It affects the entire organisation.

The module says AWS CAF provides guidance and best practices to help organisations build a comprehensive approach to cloud adoption. 

---

# 46. AWS CAF in one sentence

**AWS CAF helps an organisation prepare for cloud adoption from both business and technical perspectives.**

The module organises AWS CAF into **six perspectives**.

---

# 47. The six AWS CAF perspectives

The version taught in this 2022 module uses:

```text
Business
People
Governance
Platform
Security
Operations
```



The slide groups them into two broad sides.

### Business-focused

```text
Business
People
Governance
```

### Technical-focused

```text
Platform
Security
Operations
```

That grouping is extremely useful.

---

# 48. AWS CAF as building a new city

Imagine QuickMart is not just moving servers.

It is building a new digital city.

Different groups ask different questions.

---

# 49. Business perspective

The **Business perspective** asks:

> “Does this cloud investment actually help the business?”

It includes things such as:

```text
IT finance
IT strategy
Benefits realization
Business risk management
```

Stakeholders in the slide include business managers, finance managers, budget owners and strategy stakeholders. 

Think:

```text
Money
Business value
Strategy
Return
Risk
```

Example:

> “How will migrating to AWS improve profitability?”

That is mainly **Business perspective**.

---

# 50. People perspective

The **People perspective** asks:

> “Do our employees have the skills and organisational structure needed for cloud?”

It includes:

```text
Resource management
Incentive management
Career management
Training management
Organizational change management
```



Think:

```text
Employees
Training
Staffing
Skills
Culture
Change
```

Example:

> “Developers do not yet understand cloud technologies. We need training.”

**People perspective**

---

# 51. Governance perspective

The **Governance perspective** asks:

> “How do we keep cloud adoption aligned with business strategy, projects, policies and risk?”

It includes:

```text
Portfolio management
Program/project management
Business performance measurement
License management
```



Think:

```text
Rules
Oversight
Projects
Measurement
Control
Risk
```

Example:

> “Who ensures cloud projects remain aligned with corporate goals?”

**Governance perspective**

---

# 52. Platform perspective

The **Platform perspective** focuses on the technical architecture.

It includes:

```text
Compute provisioning
Network provisioning
Storage provisioning
Database provisioning
Systems and solution architecture
Application development
```



Think:

```text
What do we actually build?
```

Example:

> “What networking, compute, database and storage architecture should we design?”

**Platform perspective**

---

# 53. Security perspective

The **Security perspective** asks:

> “How do we meet security objectives?”

Capabilities include:

```text
Identity and access management
Detective controls
Infrastructure security
Data protection
Incident response
```



Think:

```text
Protect
Detect
Respond
Control access
Protect data
```

Example:

> “How should employee access to AWS resources be controlled?”

**Security perspective**

---

# 54. Operations perspective

The **Operations perspective** asks:

> “How will this environment be run every day after we build it?”

It includes:

```text
Service monitoring
Application performance monitoring
Resource inventory management
Release/change management
Reporting and analytics
Business continuity/disaster recovery
IT service catalog
```



Think:

```text
Day-to-day running
Monitoring
Maintenance
Recovery
Changes
```

Example:

> “How do we monitor applications and recover from failures?”

**Operations perspective**

---

# 55. AWS CAF perspectives as six questions

This is probably the easiest way to memorize them:

```text
BUSINESS
→ Why are we moving?

PEOPLE
→ Who needs skills and change?

GOVERNANCE
→ What rules and oversight do we need?

PLATFORM
→ What will we build?

SECURITY
→ How will we protect it?

OPERATIONS
→ How will we run it?
```

If you remember those six questions, CAF becomes far easier than memorising dozens of bullet points.

---

# 56. CAF scenario practice

### Scenario A

> Finance wants to know whether cloud investment produces measurable business value.

**Business**

---

### Scenario B

> Staff need AWS training before migration.

**People**

---

### Scenario C

> Management wants cloud projects aligned with company strategy and controlled through proper project governance.

**Governance**

---

### Scenario D

> Architects are designing compute, storage, networking and databases.

**Platform**

---

### Scenario E

> The company needs identity controls, data protection and incident-response procedures.

**Security**

---

### Scenario F

> The organisation needs monitoring, change management and disaster recovery processes.

**Operations**

---

# 57. Common exam traps

## Trap 1 — Cloud means “everything is free”

No.

The module explicitly emphasizes **pay-as-you-go**, not “pay nothing.”

---

## Trap 2 — Cloud means no infrastructure exists

Also no.

AWS still owns physical infrastructure.

The difference is that **you consume it as a service** rather than necessarily owning the hardware yourself.

---

## Trap 3 — Cloud automatically means SaaS

No.

Cloud services can be:

```text
IaaS
PaaS
SaaS
```

---

## Trap 4 — Hybrid means using two AWS services

No.

Hybrid refers to using both:

```text
Cloud
+
On-premises environment
```

---

## Trap 5 — IaaS gives less control than SaaS

Backwards.

```text
Most control → IaaS
Least control → SaaS
```

---

## Trap 6 — The six cloud advantages are all just “cheaper”

No.

Some are financial.

Others are about:

```text
Speed
Agility
Capacity
Global reach
Operational focus
```

---

## Trap 7 — “Stop guessing capacity” means capacity never needs planning

Not quite.

It means cloud allows capacity to adjust dynamically rather than requiring companies to lock in huge fixed physical capacity based solely on long-term guesses.

---

## Trap 8 — Go global means one server automatically serves the world with perfect latency

No.

The idea is that AWS provides infrastructure in multiple geographic locations, making global deployment much faster.

---

## Trap 9 — AWS CAF is a technical architecture diagram

No.

CAF is a framework for **organisational cloud adoption**.

It includes business, people and governance—not just technology.

---

## Trap 10 — Platform and Operations are the same

No.

```text
Platform
→ design/build architecture

Operations
→ run/monitor/manage it
```

---

## Trap 11 — Business and Governance are the same

Not quite.

```text
Business
→ business value, finance, strategy

Governance
→ oversight, alignment, projects, measurement
```

---

# 58. The sample question in the module

The module asks:

> Why is AWS more economical than traditional data centers for applications with varying compute workloads?

The correct answer is:

> **Amazon EC2 instances can be launched on demand when needed.** 

Why?

Because the important keyword is:

```text
varying workloads
```

If workload changes, AWS allows capacity to follow demand more closely.

The wrong answer saying:

> “Run enough instances permanently for peak workload”

would recreate the exact traditional overprovisioning problem cloud is supposed to solve.

---

# 59. Subjective answer — What is cloud computing?

A good answer:

> Cloud computing is the on-demand delivery of IT resources such as compute power, storage, databases and applications over the internet using pay-as-you-go pricing. Instead of purchasing and maintaining all physical infrastructure upfront, organisations can request cloud resources when required and adjust them according to changing demand.

---

# 60. Subjective answer — Traditional vs cloud computing

> In traditional computing, infrastructure is treated mainly as physical hardware that must be purchased, installed, maintained and planned in advance. This can involve long procurement cycles, large upfront capital expenditure and capacity forecasting. In cloud computing, infrastructure can be treated more like software because resources can be created, changed and removed programmatically. This gives organisations greater flexibility, faster provisioning and the ability to scale resources according to actual demand.

---

# 61. Subjective answer — Six advantages

> The six main advantages of cloud computing are trading capital expense for variable expense, benefiting from economies of scale, stopping the need to guess capacity, increasing speed and agility, reducing the burden of running and maintaining data centers, and gaining the ability to deploy globally more quickly. Together, these advantages allow organisations to align infrastructure more closely with actual demand while focusing more resources on business value.

---

# 62. Subjective answer — AWS CAF

> The AWS Cloud Adoption Framework provides guidance and best practices to help organisations plan and manage successful cloud adoption. The framework recognises that cloud migration affects not only technology but the entire organisation. In the module, AWS CAF is divided into six perspectives: Business, People, Governance, Platform, Security and Operations. Business, People and Governance focus mainly on business capabilities, while Platform, Security and Operations focus mainly on technical capabilities.

---

# 63. Exam keyword map

| Question mentions...                   | Think...                  |
| -------------------------------------- | ------------------------- |
| On-demand IT resources                 | Cloud computing           |
| Pay only for consumption               | Variable expense          |
| Large AWS purchasing/usage scale       | Economies of scale        |
| Over/under provisioning                | Stop guessing capacity    |
| Resources in minutes instead of weeks  | Speed and agility         |
| Not maintaining physical facilities    | Stop running data centers |
| Deploy closer to international users   | Go global                 |
| Maximum control over infrastructure    | IaaS                      |
| Focus mainly on application            | PaaS                      |
| Finished software                      | SaaS                      |
| Cloud + on-premises                    | Hybrid                    |
| Click through AWS                      | Management Console        |
| Commands/scripts                       | CLI                       |
| Access AWS from application code       | SDK                       |
| Finance/business value                 | CAF Business              |
| Training/staffing                      | CAF People                |
| Policies/project oversight             | CAF Governance            |
| Architecture/compute/network/storage   | CAF Platform              |
| IAM/data protection                    | CAF Security              |
| Monitoring/recovery/day-to-day support | CAF Operations            |

---

# 64. Whole module as one continuous story

QuickMart wants to launch online.

### Traditional IT

```text
Buy servers
↓
Install infrastructure
↓
Guess capacity
↓
Maintain data center
↓
Expand slowly
```

Management discovers this is expensive and inflexible.

So it investigates **cloud computing**.

Cloud allows QuickMart to:

```text
Request resources on demand
Access them via the internet
Pay according to usage
```

Instead of treating infrastructure purely as physical hardware, the company can increasingly treat it as **software**.

Then QuickMart decides what type of cloud service it needs:

```text
IaaS
PaaS
SaaS
```

and where the system will live:

```text
Cloud
Hybrid
On-premises
```

It chooses AWS, combining services like:

```text
VPC
EC2
DynamoDB
S3
```

The company manages AWS through:

```text
Console
CLI
SDK
```

But moving to AWS is not merely an IT project.

Finance asks:

> “Does this make business sense?”

HR asks:

> “Do employees have the skills?”

Management asks:

> “How will this be governed?”

Architects ask:

> “What should we build?”

Security asks:

> “How do we protect it?”

Operations asks:

> “How do we run it every day?”

Those six questions become the **six AWS CAF perspectives**.

And that is essentially the entire Module 1 story.

---

# 65. Ultra-short revision sheet

```text
CLOUD COMPUTING
───────────────
On-demand IT resources
Via internet
Pay-as-you-go
```

```text
SERVICE MODELS
──────────────
IaaS → most control
PaaS → focus on application
SaaS → use finished software
```

```text
DEPLOYMENT MODELS
─────────────────
Cloud
Hybrid
On-premises/private cloud
```

```text
6 CLOUD ADVANTAGES
──────────────────
1. CapEx → variable expense
2. Economies of scale
3. Stop guessing capacity
4. Speed and agility
5. Stop maintaining data centers
6. Go global quickly
```

```text
AWS INTERACTION
───────────────
Console → Click
CLI     → Commands
SDK     → Code
```

```text
AWS CAF
───────
Business   → Why / value
People     → Skills / training
Governance → Rules / oversight
Platform   → Build
Security   → Protect
Operations → Run
```

---

# The single most important idea in Module 1

Module 1 is really teaching one shift:

```text
OLD THINKING

"How much hardware should we buy now
for what we think we might need later?"
```

becomes:

```text
CLOUD THINKING

"What resources do we need now,
and how can we adjust them as requirements change?"
```

Everything else in the chapter—pay-as-you-go pricing, elasticity, agility, global reach, service models, and even AWS CAF—grows out of that change in thinking. 





</details>

<details>
<summary><strong>Module 2: Cloud Economics and Billing — Intuitive and Narrative Explanation</strong></summary>

# Module 2: Cloud Economics and Billing — Intuitive and Narrative Explanation

This module is essentially the **finance department of AWS**.

Modules such as Compute, Storage and Databases ask:

> “Which technology should I use?”

Module 2 asks:

> **“What will it cost, how do I control that cost, how do I manage billing across accounts, and what happens when I need help?”**

The module is divided into five main ideas:

1. Fundamentals of AWS pricing  
2. Total Cost of Ownership (TCO)  
3. AWS Organizations  
4. AWS Billing and Cost Management  
5. AWS Technical Support fileciteturn14file0

One important note: these slides are from **2022**. For your module/exam, learn the pricing, Free Tier and support-plan wording as presented in the slides. Some real-world AWS commercial details can change over time, so don't assume every number in an old slide is permanently current.

---

# 1. The entire module as one company story

Imagine a company called **CloudMart**.

CloudMart currently owns a small data centre.

It has to pay for:

```text
Servers
Storage
Network equipment
Electricity
Cooling
Building space
Software licences
IT administrators
Maintenance
```

Management asks:

> “Would moving to AWS be cheaper?”

That sounds like a simple question.

It isn't.

If you compare:

```text
Price of AWS EC2
vs
Price of one physical server
```

you are missing half the story.

CloudMart also needs to ask:

```text
What does the server cost to maintain?
What does the data centre cost?
How much are the administrators paid?
How much electricity does it consume?
What happens when we need more capacity?
What happens when equipment becomes obsolete?
```

That leads us to **Total Cost of Ownership**.

After CloudMart moves to AWS, new questions appear:

```text
How do we estimate AWS costs before deploying?
How do we see what we are spending?
How do we receive alerts before overspending?
How do we manage 20 AWS accounts?
Who do we contact when something goes wrong?
```

And that produces the rest of Module 2.

So mentally, the module flows like this:

```text
HOW AWS CHARGES
      ↓
IS AWS CHEAPER THAN ON-PREMISES?
      ↓
ESTIMATE BEFORE BUILDING
      ↓
MANAGE MULTIPLE ACCOUNTS
      ↓
MONITOR ACTUAL SPENDING
      ↓
GET AWS SUPPORT WHEN NEEDED
```

---

# Section 1: Fundamentals of Pricing

# 2. The three fundamental AWS cost drivers

Page 5 gives you one of the most important diagrams in the chapter.

AWS costs can broadly be understood through three drivers:

```text
1. Compute
2. Storage
3. Data transfer
```

fileciteturn16file3

Think of running a restaurant.

You pay for:

```text
People cooking       → Compute
Space holding food   → Storage
Moving food around   → Data transfer
```

AWS is obviously more complicated than a restaurant, but the financial logic is surprisingly similar.

---

# 3. Compute cost

**Compute** means processing power.

Examples include services such as EC2.

The module describes compute as being charged according to things such as:

- how long it runs;
- the type of instance used.

Conceptually:

```text
Compute cost ≈
Amount of compute
×
Time used
```

Suppose:

```text
Small server:
RM-equivalent $0.02/hour

Runs 10 hours
→ $0.20
```

If it runs 100 hours:

```text
100 × $0.02
= $2.00
```

The point is not that AWS servers magically become free.

The point is that you can often pay according to **actual usage** rather than buying the physical server beforehand.

---

# 4. Storage cost

Storage is generally based on how much data you keep.

The module simplifies this as:

```text
Storage → typically charged per GB
```

Example:

```text
10 GB stored
vs
10 TB stored
```

Obviously, storing 10 TB generally costs more.

But storage cost can also depend on the type of storage you choose.

You encountered this later with:

```text
S3 Standard
S3 Standard-IA
Glacier
EBS
EFS
```

Different storage exists because paying premium prices for data you barely touch would be an imaginative way of wasting money.

---

# 5. Data-transfer cost

The module's simplified rule is:

```text
Data IN  → generally no charge, with exceptions
Data OUT → generally charged
```

fileciteturn16file3

Think of AWS as a hotel.

Getting your luggage **into** the hotel is often free.

Shipping ten tonnes of luggage **out** across the world is where somebody eventually sends you a bill.

For exam purposes, when you see:

> “Large amounts of data transferred OUT of AWS”

you should immediately think:

> **Potential data-transfer cost.**

---

# 6. AWS pricing philosophy

Page 6 reduces AWS's pricing philosophy to three ideas:

```text
Pay for what you use

Pay less when you reserve

Pay less when you use more
and as AWS grows
```

fileciteturn15file0

That is the backbone of this entire section.

---

# 7. Principle 1 — Pay for what you use

Suppose CloudMart needs additional servers only during a three-day sales event.

### Traditional approach

CloudMart buys enough physical servers for peak demand.

```text
Normal demand:  ███
Peak demand:    ██████████

Physical capacity purchased:
██████████
```

Most of the year:

```text
Used:      ███
Unused:    ███████
```

But CloudMart already bought the hardware.

The empty capacity does not politely refund itself.

### AWS approach

CloudMart can increase capacity when necessary and reduce it afterward.

```text
Normal:
███

Sale:
██████████

After sale:
███
```

Page 7's diagram contrasts the fixed/committed nature of traditional infrastructure with AWS expenditure following actual usage. fileciteturn15file0

This is why **elasticity is also an economic idea**, not merely a technical one.

---

# 8. No large upfront expense

Traditional infrastructure might require:

```text
Day 1:
Buy servers             $$
Buy storage              $$
Buy switches             $$
Prepare data centre      $$
Install everything       $$
```

Money is spent before the company even knows how successful the system will become.

Cloud can instead look more like:

```text
Use resources
↓
Receive charge
↓
Scale according to demand
```

So the business avoids purchasing a large amount of infrastructure before it is actually needed.

---

# 9. Principle 2 — Pay less when you reserve

Suppose CloudMart knows:

> “This application will definitely run continuously for the next few years.”

AWS can offer lower pricing in exchange for a longer commitment.

The 2022 module explains this using **Reserved Instances (RIs)**.

It gives three payment approaches:

| RI payment option | Module's idea |
|---|---|
| No Upfront | Smaller discount |
| Partial Upfront | Larger discount |
| All Upfront | Largest discount |

The slide states that RIs could provide savings of **up to 75%** in the course material. Treat that as the module's historical pricing statement rather than a timeless guarantee. fileciteturn15file0

---

# 10. Why does reservation produce a discount?

Imagine renting an apartment.

### Option A

You tell the landlord:

> “Maybe I'll stay tonight. Maybe not. No promises.”

The landlord has uncertainty.

### Option B

You say:

> “I'll commit for a longer period.”

Now the landlord has predictable income.

Cloud economics follows similar logic.

```text
More flexibility for customer
→ Usually higher unit price

More commitment from customer
→ Potential discount
```

This creates an important exam pattern:

```text
Unpredictable workload
→ pay-as-you-go flexibility

Predictable long-term workload
→ consider commitment/reservation
```

---

# 11. Don't reserve something merely because it is cheaper

A 40% discount on something you don't need is not a saving.

Suppose:

```text
Large instance = $100/month
Reserved discount = 40%

Cost = $60/month
```

Wonderful.

Except the application only needed:

```text
Small instance = $30/month
```

Then the “discounted” oversized instance still wastes:

```text
$60 - $30 = $30/month
```

This is why later AWS cost optimisation teaches:

```text
Right-size first
Then consider commitment
```

Buying unnecessary capacity at a discount remains buying unnecessary capacity.

---

# 12. Principle 3 — Pay less by using more

Page 9 introduces **volume-based discounts**.

As usage increases, some services use tiered pricing so that the cost per unit may decrease.

The module gives examples including:

- Amazon S3;
- Amazon EBS;
- Amazon EFS. fileciteturn12file18

Conceptually:

```text
First amount of usage
→ Price A per GB

Larger usage tier
→ Lower effective price per GB
```

Do not interpret this as:

> “Using more AWS always reduces your total bill.”

If you store 1 PB rather than 10 GB, your total cost certainly does not become smaller through the spiritual power of volume discounts.

The idea is:

> **Your price per unit may fall at higher volumes.**

---

# 13. Economies of scale

AWS operates enormous infrastructure.

Because AWS buys and operates computing resources at massive scale, the module argues that AWS can lower its own unit costs and pass some of those efficiencies to customers.

This is called an **economy of scale**.

Imagine:

```text
Person A buys 1 server
Company B buys 20 servers
AWS buys enormous quantities of infrastructure
```

The purchasing and operating economics are completely different.

Page 10 illustrates this principle and includes a historical claim about AWS price reductions through September 2019. fileciteturn14file17

For your exam, remember the concept rather than memorising an obsolete count of historical price cuts:

> **AWS's scale can reduce unit costs.**

---

# 14. Custom pricing

Page 11 says custom pricing can be available for high-volume projects with unique requirements. fileciteturn14file17

Imagine a tiny company using:

```text
2 EC2 instances
100 GB storage
```

It probably uses published standard pricing.

Now imagine a multinational company committing to enormous AWS usage.

It may have commercial requirements that justify negotiated pricing.

So:

```text
Ordinary usage
→ Standard published pricing

Very large / specialised usage
→ Potential custom pricing
```

---

# 15. AWS Free Tier

The **2022 module** describes AWS Free Tier as a way for new users to gain hands-on experience and says it is free for one year for new customers in the version taught in these slides. fileciteturn15file0

For your exam using this material, remember its purpose:

> **Free Tier allows limited AWS usage so customers can learn and experiment without immediately paying normal full usage charges.**

The dangerous misconception is:

```text
Free Tier ≠ everything in AWS is free.
```

Usage beyond eligible limits or use of non-covered resources can generate charges.

---

# 16. “Free service” does not always mean “free architecture”

Page 13 gives examples of services described as having no separate charge in the module, including:

- Amazon VPC;
- Elastic Beanstalk;
- Auto Scaling;
- CloudFormation;
- IAM.

But it also warns that **other resources used by those services can still cost money**. fileciteturn15file0

This distinction matters enormously.

Consider Elastic Beanstalk.

```text
Elastic Beanstalk service
        ↓ provisions
EC2 instances
Load balancer
Storage
Data transfer
```

You might not pay an extra “Beanstalk fee,” but you still pay for underlying billable resources.

It's rather like a shopping assistant saying:

> “My service is free.”

and then handing you a trolley containing RM5,000 of products.

The assistant may indeed be free. The trolley is not.

---

# 17. Section 1 exam summary

The fundamental pricing logic is:

```text
AWS COST DRIVERS
Compute
Storage
Data transfer

AWS PRICING PHILOSOPHY
Pay for what you use
Pay less when you commit/reserve
Pay less per unit at suitable volume tiers
Benefit from economies of scale
```

And remember:

```text
Free AWS service
≠
Everything that service creates is free
```

---

# Section 2: Total Cost of Ownership

# 18. What is TCO?

**Total Cost of Ownership (TCO)** is a financial estimate used to identify the **direct and indirect costs** of owning and operating a system.

The module says TCO can help:

- compare running infrastructure on-premises versus AWS;
- build the financial case for moving to the cloud. fileciteturn13file5

The important word is:

> **TOTAL**

Not:

> “Price printed on the server box.”

---

# 19. The car analogy

Suppose you buy a car for RM80,000.

Is the total cost of owning that car RM80,000?

Obviously not.

You also pay for:

```text
Fuel
Insurance
Road tax
Tyres
Maintenance
Repairs
Parking
Depreciation
```

A server works similarly.

Buying a RM20,000 physical server does not mean:

```text
TCO = RM20,000
```

You also have to operate it.

---

# 20. The hidden costs of an on-premises server

Page 18's TCO diagram groups costs into areas such as:

```text
Server costs
Storage costs
Network costs
IT labour costs
```

and repeatedly includes facilities costs such as:

```text
Space
Power
Cooling
```

fileciteturn8file0

This is one of the most important subjective-exam ideas in the chapter.

---

# 21. Server costs

Running physical servers can require:

```text
Server hardware
Rack chassis
Power distribution units
Top-of-rack switches
Hardware maintenance
Operating-system licences
Virtualisation licences
Administration
Space
Power
Cooling
```

That RM20,000 server was becoming lonely, so naturally it brought an entire data centre with it.

---

# 22. Storage costs

On-premises storage can include:

```text
Storage disks
Storage arrays
SAN equipment
Fibre Channel switches
Maintenance
Storage administrators
Space
Power
Cooling
```

Again, comparing:

```text
AWS storage price per GB
vs
price of one physical disk
```

is incomplete.

---

# 23. Network costs

The module includes costs such as:

```text
LAN switches
Load balancers
Bandwidth
Network administration
Space
Power
Cooling
```

fileciteturn8file0

The network does not construct itself out of professional enthusiasm.

Someone buys it, configures it, monitors it and replaces it.

---

# 24. IT labour

People must operate infrastructure.

That can involve:

```text
Server administrators
Storage administrators
Network administrators
Security staff
Support engineers
```

TCO therefore includes the labour required to keep the environment functioning.

This is why cloud cost comparisons that pretend employees, electricity and maintenance are somehow “free because we already have them” are financially dubious.

---

# 25. Facilities cost

Physical infrastructure needs a physical location.

Think:

```text
Building space
Power
Cooling
Backup power
Environmental systems
```

A cloud provider takes much of that physical infrastructure burden away from the customer.

This does **not** mean AWS has no data-centre costs.

It means those costs are built into AWS's service economics rather than the customer personally constructing the data centre.

---

# 26. On-premises versus AWS

Page 16 contrasts traditional infrastructure with AWS Cloud.

Traditional environments involve things such as:

```text
Equipment
Administration
Contracts
Infrastructure cost
```

while AWS highlights:

```text
Scale up and down
No large upfront infrastructure purchase
Pay for usage
Self-service infrastructure
Improved agility / time to market
```

fileciteturn16file5

This gives us an important insight:

> Cloud economics is not only about whether one server is cheaper.

It is also about **flexibility and business speed**.

---

# 27. Example: Black Friday

Imagine a retailer normally needs:

```text
20 servers
```

For Black Friday it needs:

```text
100 servers
```

### On-premises approach

It might purchase 100 servers.

For most of the year:

```text
Required: 20
Owned:    100

Idle:      80
```

### Cloud approach

```text
Normal:
20

Black Friday:
100

After:
20
```

That difference affects TCO because the company is not permanently owning peak capacity.

---

# 28. TCO isn't guaranteed to make AWS cheaper

This is worth understanding because the slide includes an example showing extremely large savings.

Page 19 presents a particular illustrative comparison with large annual and three-year savings. That is an **example case**, not a universal law saying:

```text
Move anything to AWS
→ automatically save 96%
```

That conclusion would be spectacularly optimistic accounting.

The real lesson is:

```text
Calculate ALL costs
↓
Compare the specific alternatives
↓
Then decide
```

fileciteturn8file0

---

# 29. TCO can include non-cost business benefits

The TCO case study later in the module highlights outcomes involving:

- resource optimisation;
- security/compliance;
- disaster recovery;
- increased computing capacity;
- faster provisioning;
- faster service deployment;
- continuous cost optimisation. fileciteturn16file2

So the decision can be:

```text
Financial cost
+
Operational efficiency
+
Business agility
+
Resilience
```

not merely:

```text
Which number is smaller?
```

---

# 30. AWS Pricing Calculator

Suppose CloudMart has decided:

> “We might deploy 10 EC2 instances, storage and a database.”

Before creating anything, it wants to know approximately what that architecture will cost.

That is the purpose of the **AWS Pricing Calculator**.

The module says it can be used to:

- estimate monthly cost;
- model solutions before building them;
- explore the calculations behind an estimate;
- compare relevant configurations and terms;
- group services within an estimate. fileciteturn13file2

---

# 31. Calculator versus actual bill

This distinction is easy to test.

```text
AWS Pricing Calculator
→ BEFORE deployment
→ Estimate

AWS Billing tools
→ AFTER / DURING usage
→ Actual or accumulated spending data
```

Suppose:

```text
Pricing Calculator says:
Estimated monthly cost = $120
```

That does not guarantee:

```text
Actual invoice = exactly $120
```

Real usage may differ.

Perhaps:

```text
You ran more instances.
You transferred more data.
You stored more objects.
You forgot to stop something.
```

The calculator predicts from your assumptions.

The bill charges from reality.

AWS infrastructure is unfortunately unable to bill based on the student's good intentions.

---

# 32. TCO versus Pricing Calculator

These are related but different.

| Tool/concept | Main question |
|---|---|
| **TCO** | Is the overall cost of AWS favourable compared with alternatives such as on-premises? |
| **AWS Pricing Calculator** | What might my proposed AWS architecture cost? |

Memory trick:

```text
TCO
→ Compare worlds

Pricing Calculator
→ Estimate AWS
```

---

# Section 3: AWS Organizations

# 33. Why would a company have multiple AWS accounts?

Imagine CloudMart grows.

It now has:

```text
Production
Development
Testing
Finance
HR
Security
Research
```

Putting every workload, every team and every permission into one enormous AWS account can become messy.

So the organisation might use several AWS accounts.

Example:

```text
CloudMart
├── Production AWS account
├── Development AWS account
├── Security AWS account
├── Finance AWS account
└── Testing AWS account
```

Now another problem appears:

> “Who manages all these accounts?”

Enter **AWS Organizations**.

---

# 34. What is AWS Organizations?

AWS Organizations provides **central management of multiple AWS accounts**.

The module highlights features including:

- policy-based account management;
- group-based account management;
- APIs for automating account management;
- consolidated billing. fileciteturn12file7

Think of AWS Organizations as the company's **head office**.

Individual AWS accounts are its branches.

---

# 35. Organizational Units

Accounts can be grouped logically.

Conceptually:

```text
CloudMart Organization
│
├── Production OU
│   ├── Website account
│   └── Database account
│
├── Development OU
│   ├── Dev account
│   └── Test account
│
└── Security OU
    └── Security account
```

**OU** means **Organizational Unit**.

An OU is useful because policies can be applied to a logical collection of accounts rather than manually treating every account independently.

---

# 36. School analogy for OUs

Imagine a university.

```text
University
├── Engineering Faculty
│   ├── Computer Science
│   └── Mechanical Engineering
│
└── Business Faculty
    ├── Accounting
    └── Finance
```

A rule applied to the Engineering Faculty may affect departments under it.

AWS Organizations uses a similar hierarchy:

```text
Organization
↓
OU
↓
AWS accounts
```

---

# 37. Consolidated billing

One of the major economic features of AWS Organizations is **consolidated billing**.

Without central billing:

```text
Account A → Bill A
Account B → Bill B
Account C → Bill C
Account D → Bill D
```

With consolidated billing:

```text
Account A ┐
Account B ├─→ Consolidated billing
Account C ┤
Account D ┘
```

The organisation gets centralized visibility into spending.

This is especially useful when a finance team needs to understand:

```text
Total company AWS expenditure
Cost by account
Cost by department
```

---

# 38. AWS Organizations versus IAM

This is a common confusion.

### AWS Organizations

Think:

> **Multiple AWS accounts.**

### IAM

Think:

> **Users, roles and permissions.**

So:

```text
Need to centrally manage 30 AWS accounts
→ AWS Organizations

Need to control what a developer can do
inside an AWS account
→ IAM
```

They can work together, but they solve different layers of the problem.

---

# 39. Service Control Policies

AWS Organizations can use **Service Control Policies**, usually abbreviated **SCPs**, to impose organisation-level permission boundaries.

Conceptually:

```text
Organization says:
"No production account may use Service X."
              ↓
Individual account cannot simply ignore that rule
```

The most important distinction to remember is:

```text
SCP → Limits maximum permissions
IAM → Grants/controls permissions for identities
```

So an SCP is more like the fence surrounding the property.

IAM determines which doors a particular employee can actually open.

---

# 40. SCP versus IAM example

Suppose:

```text
SCP permits S3
```

Does that automatically mean:

```text
Every user gets S3 access?
```

No.

IAM must still grant the user permission.

Conceptually:

```text
Allowed by Organization boundary
AND
Allowed by IAM
=
Effective access
```

This distinction becomes even more explicit in the security module, but it is useful here because otherwise “Organizations policies” and “IAM policies” start blending into the same grey AWS soup.

---

# 41. How AWS Organizations can be accessed

The module shows AWS Organizations being accessible through mechanisms including:

```text
AWS Management Console
AWS CLI
AWS SDKs
HTTPS Query API
```

fileciteturn6file6

The point is that Organizations can be administered manually or programmatically.

---

# Section 4: AWS Billing and Cost Management

# 42. Why cost-management tools exist

Suppose CloudMart estimates:

```text
$5,000/month
```

After deployment, the company needs to answer different questions:

```text
How much have we actually spent?
Which service costs the most?
Which account caused the cost?
Are costs increasing?
Are we approaching our budget?
Can we get detailed usage data?
```

One tool would become cluttered trying to solve all of those perfectly.

So AWS provides several cost-management tools.

The module specifically highlights:

```text
AWS Budgets
AWS Cost Explorer
AWS Cost and Usage Report
```

along with AWS Bills and the Billing Dashboard. fileciteturn14file0 fileciteturn17file0

---

# 43. The easiest way to remember all billing tools

Think of running a household.

| AWS tool | Household analogy |
|---|---|
| Billing Dashboard | Quick financial overview |
| AWS Bills | Itemised utility bill |
| Cost Explorer | Graphs showing spending patterns |
| AWS Budgets | Monthly spending limit and warning |
| Cost and Usage Report | Detailed transaction-level spreadsheet/report |

This distinction is much more useful than memorising five definitions separately.

---

# 44. AWS Billing Dashboard

The **AWS Billing Dashboard** provides a central place for viewing billing information.

Think:

```text
"What is happening with my AWS spending?"
```

rather than:

```text
"Give me every individual usage record in raw detail."
```

Page 40 introduces the Billing Dashboard, and page 46 contains the recorded demonstration. fileciteturn17file11 fileciteturn17file1

---

# 45. AWS Bills

Use the **Bills** area when you want to inspect the charges that make up the AWS bill.

Think of your electricity invoice.

The top might say:

```text
Total = RM300
```

But you might ask:

```text
Where did RM300 come from?
```

The itemisation explains it.

Same idea:

```text
AWS total cost
      ↓
Which services?
Which Regions?
Which usage?
```

So the memory question is:

> **“What was I charged for?” → AWS Bills**

---

# 46. AWS Cost Explorer

**AWS Cost Explorer** helps analyse AWS costs and usage visually.

Think:

```text
Bill:
"You spent $500."

Cost Explorer:
"Here is how that spending changed over time
and where it came from."
```

Useful questions include:

```text
Why did costs increase?
Which service costs the most?
How does this month compare with earlier periods?
What happens when I filter by service/account?
```

The module lists Cost Explorer among its key cost-management tools. fileciteturn16file0

Memory:

```text
Cost Explorer
= investigate spending
```

---

# 47. AWS Budgets

**AWS Budgets** is about setting financial or usage targets and monitoring whether you are approaching them.

Suppose:

```text
Monthly AWS budget = $1,000
```

You might configure warning thresholds.

Conceptually:

```text
Spend reaches warning level
        ↓
Budget condition triggered
        ↓
Notification / action workflow
```

Memory:

```text
Budgets
= "Warn me when spending approaches my limit."
```

---

# 48. Budget does not mean AWS magically refuses to bill you

A frequent conceptual error is:

> “I set a $100 budget, so AWS physically cannot charge more than $100.”

Do not assume that.

A **budget is primarily a cost-control and monitoring mechanism**, not a magical force field surrounding the credit card.

If resources continue running, they can continue consuming billable services.

This is why monitoring matters.

---

# 49. AWS Cost and Usage Report

The **AWS Cost and Usage Report** is for detailed cost and usage information.

Think of it as:

```text
Billing Dashboard
→ executive summary

Cost and Usage Report
→ accountant/data analyst wants the detailed records
```

The module identifies it as one of the three central cost-management tools. fileciteturn13file1

It is useful when an organisation wants to perform detailed analysis, reporting or integration with its own systems.

---

# 50. Billing tools comparison

| Question | Best match |
|---|---|
| “Give me a quick billing overview.” | Billing Dashboard |
| “What charges make up my bill?” | AWS Bills |
| “Show me cost trends and let me analyse them.” | Cost Explorer |
| “Warn me when cost approaches a threshold.” | AWS Budgets |
| “Give me detailed cost and usage data.” | Cost and Usage Report |
| “What might this architecture cost before I build it?” | AWS Pricing Calculator |

This table is worth learning almost verbatim conceptually.

---

# 51. Pricing Calculator versus Cost Explorer

Another exam favourite:

```text
Pricing Calculator
→ future/planned architecture
→ estimate

Cost Explorer
→ existing AWS spending
→ analyse
```

Scenario:

> “A company wants to estimate the monthly cost of an architecture before deploying it.”

**Answer:** AWS Pricing Calculator.

Scenario:

> “A company wants to understand why its AWS spending increased over the past several months.”

**Answer:** AWS Cost Explorer.

---

# 52. Cost Explorer versus Budgets

```text
Cost Explorer:
"What happened to my costs?"

Budgets:
"Tell me when my costs approach a target."
```

Explorer investigates.

Budgets watches against limits.

---

# 53. Bills versus Cost and Usage Report

```text
Bills
→ Human-readable billing breakdown

Cost and Usage Report
→ Detailed data for deep analysis/reporting
```

A manager asking:

> “How much did EC2 cost?”

may look at the bill.

A finance-data team building its own analytical system may prefer detailed cost-and-usage reporting.

---

# Section 5: AWS Technical Support

# 54. Why AWS Support exists

Eventually, something goes wrong.

CloudMart might experience:

```text
Configuration problem
Production issue
Architecture concern
Service health problem
Business-critical outage
```

Different organisations need different levels of assistance.

A student experimenting with AWS does not need the same support arrangement as a bank running mission-critical payment systems.

AWS therefore provides different support plans.

The 2022 module describes AWS Support as covering experimentation, production usage and business-critical use. fileciteturn13file0

---

# 55. The four support plans in this module

The **2022 module** teaches four plans:

| Plan | Intended use in the module |
|---|---|
| **Basic** | Basic resources and account/service-health information |
| **Developer** | Early development |
| **Business** | Production workloads |
| **Enterprise** | Business- and mission-critical workloads |

fileciteturn14file3

For your module exam, use these four because that is the model the slides teach.

---

# 56. Basic Support

Think:

> “I am using AWS, but I do not require a premium technical-support relationship.”

The slide lists resources such as:

- Resource Center;
- Service Health Dashboard;
- product FAQs;
- discussion forums;
- health-check support. fileciteturn14file3

Exam clue:

```text
Basic/general support resources
→ Basic Support
```

---

# 57. Developer Support

The module associates **Developer Support** with:

> early development on AWS. fileciteturn14file3

Example:

```text
Small development team
Building/test-stage application
Needs technical guidance
Not yet mission-critical production
```

Think:

```text
Development
→ Developer
```

AWS clearly spent several minutes ensuring that naming scheme would remain survivable in an exam.

---

# 58. Business Support

The module associates **Business Support** with customers running **production workloads**. fileciteturn14file3

The key word is:

> **Production**

Example:

```text
Company website
Live ecommerce service
Business application
Real customers depend on it
```

Think:

```text
Production
→ Business Support
```

---

# 59. Enterprise Support

The module associates **Enterprise Support** with:

```text
Business-critical workloads
Mission-critical workloads
```

fileciteturn14file3

Example:

```text
International payment system
Critical hospital platform
Core banking service
Large enterprise application
```

The business impact of failure is much greater, so a higher level of proactive support becomes more valuable.

---

# 60. Support plans are about business impact

The cleanest mental model is:

```text
Experiment / ordinary access
        ↓
Basic

Early development
        ↓
Developer

Production
        ↓
Business

Mission-critical
        ↓
Enterprise
```

The more severe the business consequences of failure, the stronger the support relationship becomes.

---

# 61. Case severity and response

Page 52 introduces **case severity and response times**.

You do not need to invent complex logic here.

The intuitive principle is:

```text
Minor issue
→ lower urgency

Production impaired
→ higher urgency

Business-critical system down
→ highest urgency
```

Support level and issue severity influence the support response expectations.

Do not memorise random response-time numbers unless your lecturer specifically requires the exact table, because those details are precisely the sort of commercial terms that change over time.

---

# 62. Technical Account Manager

The module identifies a **Technical Account Manager (TAM)** with **proactive guidance**. fileciteturn13file0

Think of the TAM as:

> A technical advisor who understands the customer's AWS environment and helps them make better decisions proactively.

The word to associate is:

```text
TAM
→ Proactive technical guidance
```

Not:

```text
TAM
→ ordinary automated monitoring service
```

---

# 63. AWS Trusted Advisor

The module associates **AWS Trusted Advisor** with **best-practice guidance**. fileciteturn13file0

Think of it as an AWS consultant robot examining your environment and saying:

```text
"This could be improved."
"This resource may be inefficient."
"This configuration has a potential issue."
```

The module's own sample exam question asks which AWS service provides infrastructure **security optimisation recommendations**, and the answer is **AWS Trusted Advisor**. fileciteturn9file2

Memory:

```text
Trusted Advisor
→ Recommendations / best practices
```

---

# 64. AWS Support Concierge

The module associates **AWS Support Concierge** with **account assistance**. fileciteturn13file0

Think:

```text
TAM
→ Technical guidance

Trusted Advisor
→ Best-practice recommendations

Support Concierge
→ Account assistance
```

Those three are easy to mix up if you merely memorise names.

---

# 65. Support trio

This is worth memorising:

| AWS support feature | Think |
|---|---|
| **TAM** | Proactive technical guidance |
| **Trusted Advisor** | Best-practice recommendations |
| **Support Concierge** | Account assistance |

---

# 66. Common exam traps

### Trap 1 — Pricing Calculator shows actual spending

No.

```text
Pricing Calculator → estimate
```

---

### Trap 2 — Cost Explorer estimates a planned architecture

Wrong tool.

```text
Pricing Calculator → planning
Cost Explorer → analyse spending
```

---

### Trap 3 — AWS Budgets automatically means spending cannot exceed the budget

No. Budgets help monitor and alert against targets.

---

### Trap 4 — TCO means only the purchase price of hardware

No.

TCO includes **direct and indirect costs**.

Think:

```text
Hardware
Storage
Networking
Facilities
Maintenance
Labour
```

---

### Trap 5 — A free AWS management service means all underlying infrastructure is free

No.

Example:

```text
Elastic Beanstalk itself
may have no separate service charge

BUT

EC2 + load balancer + storage
can still incur charges
```

---

### Trap 6 — AWS Organizations and IAM do the same thing

No.

```text
Organizations → multiple AWS accounts
IAM           → identities and permissions
```

---

### Trap 7 — SCP directly gives a user permission

No.

Think:

```text
SCP → boundary
IAM → actual identity permissions
```

---

### Trap 8 — Cost Explorer and AWS Budgets are interchangeable

No.

```text
Explorer → investigate
Budget   → monitor against target
```

---

### Trap 9 — Trusted Advisor is a human support engineer

No.

It is an AWS service that provides recommendations.

---

### Trap 10 — TAM means account-billing assistant

No.

```text
TAM → Technical guidance
Concierge → Account assistance
```

---

### Trap 11 — Enterprise Support is meant mainly for someone experimenting with AWS

No.

The module positions Enterprise for **business- and mission-critical workloads**.

---

### Trap 12 — Data transfer into AWS is always charged

The module's simplified pricing rule says inbound transfer generally has no charge, with exceptions, while outbound transfer is commonly where charges occur. fileciteturn16file3

---

# 67. Exam keyword guide

| Question says... | Think... |
|---|---|
| Estimate AWS architecture before deployment | AWS Pricing Calculator |
| Compare AWS versus on-premises financially | TCO |
| Direct + indirect infrastructure costs | TCO |
| Central management of multiple AWS accounts | AWS Organizations |
| Group AWS accounts | Organizational Unit |
| Consolidated billing | AWS Organizations |
| Analyse historical spending | Cost Explorer |
| Cost trends/visualisation | Cost Explorer |
| Spending threshold / alert | AWS Budgets |
| Detailed usage and cost data | Cost and Usage Report |
| Itemised charges | AWS Bills |
| Quick billing overview | Billing Dashboard |
| Early development | Developer Support |
| Production workloads | Business Support |
| Mission-critical workload | Enterprise Support |
| Proactive technical guidance | TAM |
| Best-practice recommendations | Trusted Advisor |
| Account assistance | Support Concierge |

---

# 68. Scenario practice

## Scenario A

> A company has not deployed its AWS architecture yet. It wants to estimate the monthly cost of EC2, storage and databases.

**Answer: AWS Pricing Calculator**

Why?

Because the infrastructure does not exist yet.

```text
Before deployment
→ Pricing Calculator
```

---

## Scenario B

> A company is considering closing its physical data centre and wants to compare all direct and indirect costs with AWS.

**Answer: Total Cost of Ownership analysis**

Because it must compare:

```text
Hardware
Storage
Network
Facilities
Labour
Maintenance
vs
AWS
```

---

## Scenario C

> A company has 40 AWS accounts and wants centralized management and consolidated billing.

**Answer: AWS Organizations**

The words:

```text
multiple accounts
centralized
consolidated billing
```

are practically holding up a neon AWS Organizations sign.

---

## Scenario D

> Finance wants to know why AWS expenditure has increased over the last several months.

**Answer: AWS Cost Explorer**

Because it needs to **analyse cost trends**.

---

## Scenario E

> Management wants an alert when spending approaches the company's monthly target.

**Answer: AWS Budgets**

Because:

```text
Target + warning
→ Budget
```

---

## Scenario F

> The finance team wants highly detailed AWS usage and cost information for its own reporting system.

**Answer: AWS Cost and Usage Report**

---

## Scenario G

> A developer is building an early-stage application and requires additional technical support.

**Answer: Developer Support**

According to the support model taught by this module.

---

## Scenario H

> A company's mission-critical system runs on AWS and requires the strongest support relationship shown in the slides.

**Answer: Enterprise Support**

---

## Scenario I

> An organisation wants proactive technical guidance from AWS.

**Answer: Technical Account Manager**

---

## Scenario J

> A company wants AWS best-practice and security optimisation recommendations.

**Answer: AWS Trusted Advisor**

The module even uses this in its sample examination question. fileciteturn9file2

---

# 69. Subjective exam answer — AWS pricing philosophy

A good answer would be:

> AWS follows a consumption-based pricing philosophy in which customers generally pay for the resources they use instead of purchasing large amounts of infrastructure upfront. Major cost drivers include compute, storage and data transfer. Customers may also reduce unit costs through suitable commitment or reservation models, volume-based pricing and economies of scale. This allows organisations to align infrastructure expenditure more closely with actual workload requirements.

---

# 70. Subjective exam answer — Total Cost of Ownership

> Total Cost of Ownership is a financial estimate that considers both direct and indirect costs of operating an IT system. It can be used to compare an on-premises environment with AWS and to build a business case for cloud migration. TCO should consider not only server hardware but also storage, networking, software, administration, maintenance, physical space, power, cooling and IT labour. Therefore, comparing only the purchase price of a physical server with an AWS service price would not provide a complete cost comparison.

---

# 71. Subjective exam answer — AWS Organizations

> AWS Organizations enables an organisation to centrally manage multiple AWS accounts. Accounts can be grouped logically and controlled using organisation-level policies. AWS Organizations also supports consolidated billing, which gives the organisation centralized visibility over charges from its member accounts. This simplifies governance, account management and financial administration for organisations that operate many AWS accounts.

---

# 72. Subjective exam answer — Cost-management services

> AWS provides several tools for monitoring and managing cloud expenditure. The Billing Dashboard provides a billing overview, while AWS Bills shows the charges that contribute to the bill. AWS Cost Explorer is used to analyse and visualise cost and usage patterns. AWS Budgets enables organisations to establish cost or usage targets and receive notifications when thresholds are approached. The AWS Cost and Usage Report provides detailed cost and usage information for deeper analysis and reporting.

---

# 73. Subjective exam answer — AWS Support

> AWS provides different support plans according to the customer's workload and business requirements. In the module, Basic Support provides general support resources, Developer Support is intended for early development, Business Support is intended for production workloads, and Enterprise Support is intended for business- and mission-critical workloads. AWS support capabilities also include Technical Account Managers for proactive technical guidance, AWS Trusted Advisor for best-practice recommendations, and AWS Support Concierge for account assistance. fileciteturn13file0 fileciteturn14file3

---

# 74. The whole chapter as one decision map

```text
"I want to understand what AWS generally charges for."
        ↓
Compute + Storage + Data Transfer


"I haven't built it yet. What might AWS cost?"
        ↓
AWS Pricing Calculator


"Should we move from our data centre to AWS?"
        ↓
Total Cost of Ownership


"We have many AWS accounts."
        ↓
AWS Organizations


"I want a quick billing overview."
        ↓
Billing Dashboard


"What exactly am I being charged for?"
        ↓
AWS Bills


"Why have my costs changed?"
        ↓
AWS Cost Explorer


"Warn me when spending approaches my target."
        ↓
AWS Budgets


"I need detailed billing and usage data."
        ↓
AWS Cost and Usage Report


"I need best-practice recommendations."
        ↓
AWS Trusted Advisor


"I need proactive technical guidance."
        ↓
Technical Account Manager


"I need account assistance."
        ↓
AWS Support Concierge
```

---

# 75. Five distinctions you absolutely should know

### 1. Pricing Calculator vs Cost Explorer

```text
Calculator = BEFORE
Explorer   = AFTER / DURING
```

### 2. TCO vs AWS bill

```text
TCO  = entire ownership comparison
Bill = AWS charges
```

### 3. Organizations vs IAM

```text
Organizations = Accounts
IAM           = Identities
```

### 4. Cost Explorer vs Budgets

```text
Explorer = Analyse
Budgets  = Alert against targets
```

### 5. TAM vs Trusted Advisor vs Concierge

```text
TAM             = Technical guidance
Trusted Advisor = Recommendations
Concierge       = Account assistance
```

If those five are clear, a large proportion of Module 2 becomes considerably less annoying.

---

# 76. Ultra-short memory sheet

```text
AWS PRICING
───────────
Compute
Storage
Data transfer

Pay for what you use
Pay less with suitable commitment
Volume discounts
Economies of scale
```

```text
TCO
───
TOTAL ownership cost

Server
Storage
Network
IT labour
Facilities
Power
Cooling
Maintenance

Use:
Compare on-premises vs AWS
```

```text
AWS PRICING CALCULATOR
──────────────────────
Estimate BEFORE building
Model monthly AWS cost
```

```text
AWS ORGANIZATIONS
─────────────────
Multiple AWS accounts
Organizational Units
Policies
Consolidated billing
```

```text
COST TOOLS
──────────
Billing Dashboard → Overview
Bills             → Charges
Cost Explorer     → Analyse
Budgets           → Threshold / alert
Cost & Usage Report → Detailed data
```

```text
SUPPORT
───────
Basic      → General resources
Developer  → Early development
Business   → Production
Enterprise → Mission-critical
```

```text
SUPPORT FEATURES
────────────────
TAM             → Proactive technical guidance
Trusted Advisor → Best-practice recommendations
Concierge       → Account assistance
```

---

# Module 2 in one paragraph

**AWS Cloud Economics and Billing is about matching technology usage with financial control.** AWS costs are driven mainly by compute, storage and data transfer, with a philosophy centred on paying for actual use, obtaining lower prices through suitable commitments or volume, and benefiting from economies of scale. Total Cost of Ownership compares the complete direct and indirect costs of on-premises infrastructure with AWS rather than comparing hardware prices alone. The AWS Pricing Calculator estimates costs before deployment, while billing tools such as Bills, Cost Explorer, Budgets and the Cost and Usage Report help understand and control actual spending. AWS Organizations centrally manages multiple AWS accounts and supports consolidated billing. Finally, AWS Support provides different levels of assistance according to workload criticality, while TAMs provide proactive guidance, Trusted Advisor provides best-practice recommendations and Support Concierge provides account assistance. fileciteturn15file0













</details>

<details>
<summary><strong>Module 3: AWS Global Infrastructure — Intuitive Explanation</strong></summary>

# Module 3: AWS Global Infrastructure — Intuitive Explanation

This chapter answers two basic questions:

1. **Where does AWS run your application?**
2. **Which AWS service should you use for a particular job?**

Think of AWS as a worldwide company that owns many secure technology campuses. Instead of buying physical servers and building your own data centre, you rent parts of this global infrastructure. fileciteturn0file0

---

## 1. The overall AWS infrastructure

AWS infrastructure can be visualised like this:

```text
AWS Global Infrastructure
│
├── Region
│   ├── Availability Zone
│   │   ├── Data centre
│   │   └── Data centre
│   ├── Availability Zone
│   │   ├── Data centre
│   │   └── Data centre
│   └── Availability Zone
│
└── Edge locations around the world
```

The most important distinction is:

> **Regions run the main application, Availability Zones protect it from failure, and edge locations bring content closer to users.**

---

# 2. AWS Region: choosing the country or area

An **AWS Region** is a geographical area where AWS has infrastructure.

Examples might include regions located around London, Singapore, Tokyo or Sydney. A Region is not merely one building. It normally contains multiple Availability Zones.

### Analogy: choosing a city

Suppose a company wants to open a business.

Before choosing the exact building, it first chooses the **city**. The city affects:

- distance from customers;
- local laws;
- available facilities;
- operating costs.

An AWS Region works the same way.

## How to select a Region

The module identifies four factors.

### 1. Data governance and legal requirements

Some laws require data to remain within a particular country or geographical area.

For example, a government organisation may not be allowed to store sensitive information in another country. In that case, the closest Region is irrelevant if it violates legal requirements.

### 2. Proximity to customers

The farther data must travel, the greater the **latency**, meaning delay.

For a Malaysian application, placing resources in a nearby Asian Region will normally provide faster responses than placing everything on another continent.

### 3. Service availability

Not every AWS service is necessarily available in every Region.

A company therefore has to verify that the Region supports the services it intends to use.

### 4. Cost

AWS prices may vary between Regions. The cheapest Region, however, is not automatically the best choice. Saving a small amount while producing poor performance or violating regulations would be a spectacularly bad bargain.

---

# 3. Availability Zones: protection inside a Region

An **Availability Zone**, or **AZ**, is an isolated part of a Region.

Each AZ consists of one or more data centres, with its own:

- power;
- networking;
- cooling;
- physical facilities.

AZs within the same Region are separated from each other but connected through fast private networks.

### Analogy: separate buildings in the same city

Imagine that a company operates from three buildings in Kuala Lumpur.

- Building A has its own electricity and internet.
- Building B has separate electricity and internet.
- Building C is also independent.

The buildings are connected, but a failure in one building should not automatically destroy the others.

That is the purpose of Availability Zones.

## Why multiple AZs matter

Suppose an online shop runs only in one AZ.

```text
AZ A
└── Online shop server
```

If that AZ becomes unavailable, the shop goes offline.

A more resilient design is:

```text
Region
├── AZ A → Application copy
└── AZ B → Application copy
```

If AZ A fails, AZ B can continue operating.

This is why AWS recommends distributing resources and replicating data across multiple Availability Zones.

> **One AZ provides infrastructure. Multiple AZs provide resilience.**

---

# 4. Data centres: the physical layer

A data centre is the actual physical facility containing servers, networking equipment, storage equipment and supporting systems.

This is where:

- data is stored;
- computations are performed;
- applications physically run.

AWS data centres are designed with redundant power, networking and connectivity.

The hierarchy is therefore:

```text
Region
└── Availability Zone
    └── One or more data centres
```

A common mistake is saying that a Region is simply one data centre. It is not. A Region contains AZs, and AZs contain data centres.

---

# 5. Edge locations: bringing content closer to users

An **edge location** is different from a Region or Availability Zone.

It is mainly used to deliver cached content closer to users.

AWS uses edge locations with services such as **Amazon CloudFront**, its Content Delivery Network.

### Analogy: main warehouse versus local collection point

Imagine an online company whose main warehouse is in Singapore.

A Malaysian customer requests the same product information repeatedly. It would be inefficient to retrieve that information from the main warehouse every time.

Instead, the company keeps frequently requested information at a nearby collection point.

In AWS:

- the **Region** is where the main application and original content may exist;
- the **edge location** stores cached copies closer to users;
- **CloudFront** delivers those copies.

This reduces latency.

```text
Without edge location:
User → Distant Region → Content

With edge location:
User → Nearby edge location → Cached content
```

## Regional edge caches

A **Regional edge cache** sits between edge locations and the original content source.

A simplified flow is:

```text
User
↓
Edge location
↓
Regional edge cache
↓
Original server in AWS Region
```

Regional edge caches can retain less frequently accessed content for longer, reducing the number of requests that must reach the original server.

### Exam keyword

When a question contains:

- CloudFront;
- content delivery;
- caching;
- low latency;
- closer to users;

the likely answer is **edge location**.

---

# 6. Region, AZ and edge location compared

| Component | Intuitive meaning | Main purpose |
|---|---|---|
| **Region** | Geographical area or city | Choose where the main AWS resources operate |
| **Availability Zone** | Independent building or campus inside the city | Protect applications from local failures |
| **Data centre** | Actual server facility | Stores data and performs processing |
| **Edge location** | Nearby delivery point | Delivers cached content with lower latency |
| **Regional edge cache** | Larger intermediate cache | Stores content between edge locations and origin |

---

# 7. Important infrastructure characteristics

The chapter introduces four closely related concepts that exam questions love to mix together.

## Elasticity

**Elasticity** means automatically increasing or decreasing resources according to current demand.

Example:

```text
Morning: 2 servers
Sales period: 10 servers
Night: 2 servers
```

The capacity expands and contracts dynamically.

> Elasticity is about responding to short-term changes.

---

## Scalability

**Scalability** means the system can grow to handle a larger workload.

For example, a small application may begin with 1,000 users and later support one million users.

> Scalability is the ability to grow.  
> Elasticity is the ability to adjust dynamically.

Something can be scalable without being automatically elastic. People often treat them as synonyms because apparently two different words were not inconvenient enough.

---

## Fault tolerance

**Fault tolerance** means the system continues operating even when a component fails.

Example:

```text
Server A fails
Server B continues serving users
```

Fault tolerance generally requires redundancy, meaning extra components are available to replace failed ones.

---

## High availability

**High availability** means keeping the system operational with minimal downtime.

Using multiple AZs supports high availability because an application is not completely dependent on one physical location.

### Difference from fault tolerance

- **Fault tolerance:** service continues despite failure, ideally with no interruption.
- **High availability:** downtime is minimised, although a brief interruption may still occur.

---

# 8. AWS services as departments in a company

The second half of the chapter introduces AWS service categories.

Do not memorise them as a pile of colourful icons. That approach works wonderfully until the icons change. Instead, understand the job performed by each category.

---

## Compute: the workers

Compute services perform calculations and run applications.

### Important examples

- **Amazon EC2** – rent virtual servers.
- **EC2 Auto Scaling** – automatically add or remove EC2 instances.
- **AWS Lambda** – run code without managing servers directly.
- **Amazon ECS and Amazon EKS** – run and manage containers.
- **AWS Elastic Beanstalk** – deploy applications while AWS manages much of the underlying environment.
- **AWS Fargate** – run containers without managing the underlying servers.

### Intuitive distinction

```text
EC2      → “Give me a virtual computer.”
Lambda   → “Run this code when needed.”
ECS/EKS  → “Manage my containerised applications.”
Fargate  → “Run my containers without making me manage servers.”
```

---

## Storage: the warehouse

Storage services keep files and data.

### Amazon S3

S3 is **object storage**.

It is suitable for:

- images;
- videos;
- backups;
- documents;
- website files.

Think of S3 as a massive warehouse containing labelled objects.

### Amazon EBS

EBS is **block storage**, commonly attached to an EC2 instance.

Think of it as the virtual hard drive of a virtual server.

### Amazon EFS

EFS is a shared file system that multiple systems can access.

Think of it as a shared company drive.

### S3 Glacier

Glacier is designed for long-term archival storage where data is rarely accessed.

Think of it as putting old records into low-cost archive storage rather than keeping them on the office desk.

```text
S3       → Objects and general files
EBS      → Virtual hard disk for EC2
EFS      → Shared file system
Glacier  → Long-term archive
```

---

## Database: the organised records department

A database is not simply somewhere data exists. It stores data in a structure designed for efficient searching, updating and relationships.

### Amazon RDS

A managed relational database service.

It supports traditional table-based databases where relationships matter.

### Amazon Aurora

An AWS-designed relational database compatible with MySQL and PostgreSQL.

### Amazon DynamoDB

A managed NoSQL database designed for fast and flexible access at scale.

### Amazon Redshift

A data warehouse intended for analytics over large datasets.

```text
RDS/Aurora  → Operational relational databases
DynamoDB    → NoSQL applications
Redshift    → Large-scale analytical queries
```

A data warehouse and normal application database are not interchangeable merely because both contain tables. One supports daily operations; the other is optimised for analysis.

---

## Networking and content delivery: the roads

Networking services control how resources communicate.

### Amazon VPC

A **Virtual Private Cloud** is an isolated virtual network in AWS.

It is like creating a private fenced area where AWS resources can operate.

### Elastic Load Balancing

Distributes incoming traffic across multiple resources.

```text
Users
  ↓
Load balancer
├── Server A
├── Server B
└── Server C
```

This prevents one server from handling everything.

### Amazon Route 53

Provides Domain Name System services. It helps direct users from a domain name to the correct destination.

### Amazon CloudFront

Caches and delivers content through edge locations.

### AWS Direct Connect

Provides a dedicated network connection between an organisation and AWS.

### AWS VPN

Creates an encrypted connection over the internet.

---

## Security, identity and compliance: the security department

### AWS IAM

IAM controls:

- who may access AWS;
- what they may access;
- which actions they may perform.

Think of it as employee identity cards plus permission rules.

### AWS Organizations

Helps manage multiple AWS accounts centrally.

### Amazon Cognito

Provides authentication and identity features for application users.

### AWS Key Management Service

Creates and manages encryption keys.

### AWS Shield

Protects against Distributed Denial-of-Service attacks.

### AWS Artifact

Provides access to AWS compliance reports and agreements.

---

## Cost management: the finance department

### AWS Budgets

Sets cost or usage limits and produces alerts when spending approaches or exceeds those limits.

### AWS Cost Explorer

Visualises and analyses AWS spending patterns.

### AWS Cost and Usage Report

Provides detailed billing and usage information.

An easy distinction is:

```text
Budgets          → Warn me
Cost Explorer    → Show and analyse spending
Cost and Usage   → Give me detailed records
```

A budget does not magically stop all spending. It mainly tracks usage and sends alerts unless further controls are configured.

---

## Management and governance: the control room

### AWS Management Console

The browser-based interface for managing AWS.

### AWS Command Line Interface

Allows AWS to be controlled using commands.

### Amazon CloudWatch

Monitors resources, metrics, logs and alarms.

### AWS CloudTrail

Records actions and API activity.

A useful distinction:

```text
CloudWatch → What is happening to the system?
CloudTrail → Who did what in the AWS account?
```

### AWS Config

Tracks resource configurations and configuration changes.

### AWS Trusted Advisor

Reviews an AWS environment and provides recommendations in areas such as cost, security, performance and reliability.

### AWS Well-Architected Tool

Helps assess workloads against AWS architectural best practices.

### AWS Auto Scaling

Adjusts capacity according to demand.

---

# 9. Global versus Regional services

Some AWS services operate at a Regional level, while others are considered global.

From the services mentioned in the chapter activity:

| Service | Scope |
|---|---|
| Amazon EC2 | Regional |
| AWS Lambda | Regional |
| AWS IAM | Global |
| Amazon Route 53 | Global |

## VPC and subnet scope

A **VPC** exists at the **Region level**.

A **subnet** exists inside one **Availability Zone**.

```text
Region
└── VPC
    ├── Subnet in AZ A
    ├── Subnet in AZ B
    └── Subnet in AZ C
```

This is important:

> A subnet cannot stretch across multiple Availability Zones.

---

# 10. One complete example

Imagine a Malaysian e-commerce company building an online store.

### Step 1: Select a Region

The company chooses a suitable nearby Region based on:

- customer latency;
- data regulations;
- service availability;
- cost.

### Step 2: Build the network

It creates a **VPC** covering the Region.

### Step 3: Divide the network

It creates separate **subnets** in two Availability Zones.

```text
VPC
├── Subnet in AZ A
└── Subnet in AZ B
```

### Step 4: Run the application

EC2 instances run in both AZs.

### Step 5: Distribute traffic

Elastic Load Balancing sends users to healthy EC2 instances.

### Step 6: Store information

- Product images go into S3.
- Transaction records go into RDS.
- EC2 operating disks use EBS.

### Step 7: Improve customer speed

CloudFront caches product images at edge locations close to users.

### Step 8: Secure access

IAM controls employee permissions.

### Step 9: Monitor activity

- CloudWatch monitors system performance.
- CloudTrail records account actions.

### Step 10: Control spending

Budgets warns the company if AWS costs become excessive.

That single example captures almost the entire chapter.

---

# 11. Common exam traps

### Trap 1: “A Region is one data centre.”

Incorrect.

A Region contains multiple Availability Zones, and each AZ contains one or more data centres.

### Trap 2: “Multiple servers in one AZ guarantee protection from an AZ failure.”

Incorrect.

They protect against server failure, but all could still be affected if the entire AZ becomes unavailable. Real AZ resilience requires deployment across multiple AZs.

### Trap 3: “CloudFront runs the original application at edge locations.”

Usually incorrect.

CloudFront primarily caches and delivers content from locations closer to users.

### Trap 4: “The nearest Region is always the correct Region.”

Incorrect.

Legal requirements, service availability and cost must also be considered.

### Trap 5: “A subnet covers an entire Region.”

Incorrect.

A VPC is Regional, but each subnet belongs to one AZ.

---

# Chapter in one paragraph

AWS divides its global infrastructure into **Regions**, which are geographical areas containing multiple isolated **Availability Zones**. Each AZ contains physical data centres and is connected to other AZs through fast private networking. Applications should use multiple AZs for high availability and fault tolerance. **Edge locations** cache and deliver content closer to users, particularly through CloudFront, reducing latency. AWS services are organised into categories such as compute, storage, databases, networking, security, cost management, and management and governance, with each category performing a distinct part of running and controlling cloud applications.



---

</details>

<details>
<summary><strong>Module 4: AWS Cloud Security — Intuitive Explanation</strong></summary>

# Module 4: AWS Cloud Security — Intuitive Explanation

This chapter is built around one uncomfortable truth:

> Moving an application to AWS does not mean AWS becomes responsible for every security mistake.

AWS secures the cloud infrastructure, while the customer secures how cloud resources are configured and used. Much of the chapter then explains how to control access, protect data, monitor activity, and prove compliance. 

---

# 1. The central story: renting a secure building

Imagine a company rents an office inside a professionally managed building.

The building owner is responsible for:

* securing the building entrance;
* maintaining the elevators;
* providing electricity;
* maintaining the physical structure;
* preventing tenants from entering one another’s offices.

However, the tenant is still responsible for:

* locking its office door;
* deciding which employees receive keys;
* protecting documents;
* configuring office computers;
* removing access when an employee leaves.

AWS works in roughly the same way.

```text
AWS secures the building.
The customer secures what happens inside the rented space.
```

This is called the **AWS shared responsibility model**.

---

# 2. Shared responsibility model

The diagram on page 5 separates security into two areas:

```text
AWS
└── Security OF the cloud

Customer
└── Security IN the cloud
```

That single difference—**of** versus **in**—is the most important concept in this module.

## AWS: security of the cloud

AWS protects the underlying infrastructure used to provide cloud services.

AWS is responsible for:

* physical data centres;
* physical servers;
* networking hardware;
* storage hardware;
* power and cooling;
* virtualisation infrastructure;
* isolation between customers;
* Regions, Availability Zones and edge locations;
* physical access controls;
* disposal or decommissioning of storage devices.

### Intuitive meaning

AWS makes sure that:

* strangers cannot casually walk into a data centre;
* broken hardware is replaced;
* one AWS customer cannot access another customer’s virtual machine;
* the infrastructure supporting EC2, S3 and other services is maintained.

A customer does not patch the physical server supporting EC2 because the customer cannot even see it. That is AWS’s job.

---

## Customer: security in the cloud

The customer controls what is placed and configured inside AWS.

The customer is generally responsible for:

* customer data;
* user accounts;
* passwords and MFA;
* IAM permissions;
* application configuration;
* security groups;
* network configuration;
* encryption choices;
* operating-system patches on EC2;
* software installed on EC2;
* S3 bucket permissions.

### Example

Suppose a company creates an S3 bucket and accidentally allows public access.

AWS successfully secured:

* the physical disk;
* the data centre;
* the S3 infrastructure;
* isolation between AWS customers.

But the company deliberately—or incompetently—configured the bucket to be public.

That exposure is the **customer’s responsibility**.

AWS provides the locks. The customer still has to use them.

---

# 3. Shared responsibility changes by service type

The amount of work handled by AWS depends on the service model.

```text
More customer control                More AWS management
IaaS  ─────────────── PaaS ─────────────── SaaS
```

The more control the customer receives, the more security work the customer must perform.

---

## Infrastructure as a Service: IaaS

With IaaS, AWS provides the infrastructure, but the customer manages much of what runs on top of it.

Examples from the chapter include:

* Amazon EC2;
* Amazon EBS;
* Amazon VPC.

### EC2 example

AWS manages:

* the physical server;
* storage hardware;
* virtualisation;
* data-centre security;
* underlying network infrastructure.

The customer manages:

* the EC2 guest operating system;
* patches and updates;
* installed software;
* security groups;
* firewall configuration;
* user accounts;
* application security.

```text
AWS:      Physical computer and virtualisation
Customer: Operating system and everything installed inside it
```

If a Windows EC2 instance is not patched for two years, that is not AWS forgetting to do its homework. The customer chose an IaaS service and inherited that responsibility.

---

## Platform as a Service: PaaS

With PaaS, AWS manages more of the underlying platform.

Examples include:

* Amazon RDS;
* AWS Elastic Beanstalk;
* AWS Lambda.

The customer can focus more on:

* application code;
* data;
* access permissions;
* application-level security.

AWS handles more of:

* operating-system management;
* infrastructure maintenance;
* platform patching;
* some recovery and availability tasks.

### RDS versus database on EC2

Suppose a company runs Oracle.

**Oracle on EC2:**

```text
Customer manages Oracle patches
Customer manages the operating system
Customer configures the instance
```

**Oracle through Amazon RDS:**

```text
AWS manages much of the database platform and patching
Customer manages data, users and database-level access
```

This is why managed services reduce operational responsibility. They do not eliminate responsibility; they merely move part of it to AWS.

---

## Software as a Service: SaaS

With SaaS, the software is already hosted and managed.

Examples in the slides include:

* AWS Trusted Advisor;
* AWS Shield;
* Amazon Chime.

The customer primarily uses and configures the service rather than managing the infrastructure underneath it.

---

# 4. Quick responsibility test

When an exam asks who is responsible, ask:

### Is it physical or underlying infrastructure?

Usually **AWS**.

Examples:

* physical hardware;
* data-centre security;
* virtualisation;
* customer isolation;
* AWS global network infrastructure.

### Is it customer configuration, access or data?

Usually **the customer**.

Examples:

* IAM permissions;
* security groups;
* S3 access;
* EC2 operating-system updates;
* passwords;
* application settings;
* encryption configuration.

---

# 5. AWS Identity and Access Management

**AWS Identity and Access Management**, or **IAM**, controls access to AWS resources.

IAM answers four questions:

```text
Who are you?
How do you prove it?
What are you allowed to do?
Which resources may you access?
```

Example:

A company may allow a developer to:

* view EC2 instances;
* start and stop EC2 instances;
* read objects in one S3 bucket;

but prevent that developer from:

* deleting the S3 bucket;
* terminating production servers;
* modifying billing settings.

IAM provides this fine-grained control.

---

# 6. Authentication versus authorisation

These are related, but not identical.

## Authentication

Authentication asks:

> Who are you?

Examples:

* username and password;
* access key;
* secret access key;
* MFA code.

## Authorisation

Authorisation asks:

> Now that AWS knows who you are, what are you allowed to do?

Examples:

* read an S3 object;
* start EC2;
* delete a DynamoDB table;
* view billing information.

```text
Authentication → Prove identity
Authorisation  → Determine permissions
```

A valid login does not mean unlimited access. Your identity may be genuine while your permissions remain limited.

---

# 7. The four essential IAM components

## IAM user

An IAM user represents a person or application requiring long-term access to an AWS account.

A user can receive:

* a username and password for console access;
* access keys for programmatic access;
* permissions through policies or groups.

### Analogy

An IAM user is an employee identity card with the employee’s name on it.

---

## IAM group

An IAM group is a collection of users that need similar permissions.

Examples:

```text
Developers group
Finance group
Database administrators group
Support group
```

Rather than manually giving the same permissions to 30 developers, attach a policy to the Developers group and add the users to it.

Important characteristics:

* a user can belong to multiple groups;
* groups contain users;
* groups cannot contain other groups;
* there is no automatic default group.

### Example

Ali belongs to:

* Developers;
* S3-Support.

He receives permissions from both groups.

---

## IAM policy

An IAM policy is a JSON document that defines permissions.

A policy normally describes:

* **Effect** – Allow or Deny;
* **Action** – what operation can be performed;
* **Resource** – what the operation applies to;
* sometimes **Condition** – when the permission applies.

Simplified example:

```json
{
  "Effect": "Allow",
  "Action": "s3:GetObject",
  "Resource": "arn:aws:s3:::project-files/*"
}
```

Meaning:

> Allow the specified identity to read objects from the project-files bucket.

A policy can be attached to:

* a user;
* a group;
* a role;
* in some cases, directly to a resource.

---

## IAM role

An IAM role contains permissions but is not permanently tied to one individual.

A role can be temporarily assumed by:

* a user;
* an application;
* an AWS service;
* a user from another AWS account.

Roles provide **temporary security credentials**.

### Analogy

An IAM user is a permanent employee identity.

An IAM role is a temporary job function:

```text
Normal employee
↓ assumes role
Temporary database administrator
↓ finishes task
Returns to normal permissions
```

---

# 8. Why IAM roles matter

Suppose an application running on EC2 must read images from S3.

The bad approach is storing access keys inside the application:

```text
Application code
└── Permanent access key
```

If the key is exposed, an attacker may reuse it.

The better approach is:

1. Create a policy allowing access to the required S3 bucket.
2. Attach the policy to an IAM role.
3. Allow the EC2 instance to assume that role.
4. AWS provides temporary credentials automatically.

```text
EC2 application
↓ assumes
IAM role
↓ permits
Access to specific S3 bucket
```

The role gives the application only the permissions it needs without placing permanent credentials inside the code.

---

# 9. Console access versus programmatic access

IAM users may access AWS in two main ways.

## AWS Management Console access

Used by humans through a browser.

Authentication may require:

* AWS account ID or account alias;
* IAM username;
* password;
* MFA code.

## Programmatic access

Used through:

* AWS CLI;
* AWS SDKs;
* APIs.

Traditional IAM programmatic credentials include:

* access key ID;
* secret access key.

Think of these as a username and password designed for software.

They must not be carelessly pasted into public source-code repositories, despite the apparently irresistible human urge to upload secrets to GitHub.

---

# 10. Multi-factor authentication

MFA requires more than a password.

```text
Something you know → Password
Something you have → MFA device or authentication code
```

Even if the password is stolen, the attacker still needs the second factor.

MFA should be enabled for:

* the root user;
* privileged IAM users;
* ideally all users.

The page 20 diagram shows access requiring both the normal username/password and a separate MFA token before the console is opened.

---

# 11. How IAM evaluates permissions

IAM starts with this rule:

> Everything is denied unless it is allowed.

This is called **implicit deny**.

The decision process is:

```text
Is there an explicit Deny?
├── Yes → DENY
└── No
    └── Is there an explicit Allow?
        ├── Yes → ALLOW
        └── No  → DENY
```

## Permission priority

```text
Explicit Deny > Explicit Allow > Implicit Deny
```

### Example

Policy 1:

```text
Allow S3 access
```

Policy 2:

```text
Deny deleting S3 objects
```

Final result:

* user may access S3;
* user may not delete objects.

The explicit deny overrides the allow.

### Exam rule

When both an allow and an explicit deny apply:

> **Deny wins. Always.**

IAM does not settle disagreements through a polite committee meeting.

---

# 12. Principle of least privilege

The **principle of least privilege** means giving only the minimum permissions required to complete a task.

A developer who only needs to view EC2 instances should not receive full administrator access.

```text
Required:
ec2:DescribeInstances

Unnecessary:
ec2:TerminateInstances
iam:CreateUser
billing:ModifyAccount
```

Least privilege reduces damage caused by:

* mistakes;
* stolen credentials;
* compromised accounts;
* malicious insiders.

Permissions should also be reviewed over time. A permission that was necessary six months ago may no longer be necessary now.

---

# 13. Identity-based and resource-based policies

## Identity-based policy

Attached to an IAM identity:

* user;
* group;
* role.

It answers:

> What may this identity do?

Example:

```text
Mary may read objects from the photos bucket.
```

## Resource-based policy

Attached directly to a resource, such as an S3 bucket.

It answers:

> Who may access this resource, and what may they do?

Example:

```text
The photos bucket allows Mary to read objects.
```

The practical result can look similar, but the policy is attached in a different place.

```text
Identity-based policy → Attached to identity
Resource-based policy → Attached to resource
```

---

# 14. Root user versus IAM user

The **AWS account root user** is created when the AWS account is opened.

It uses the original account email address and has unrestricted access.

The root user can perform certain highly sensitive account actions, such as:

* changing account settings;
* modifying the support plan;
* changing the root password;
* recovering some IAM access.

Because it has enormous power, it should not be used for normal daily work.

## Root user analogy

The root user is the master key capable of opening every door in the company.

Carrying it around every day because it is “convenient” is technically possible, much like leaving the office vault open because closing it takes effort.

---

# 15. Securing a new AWS account

The module provides a practical sequence.

## Step 1: Stop using the root user

Create an administrative IAM identity for routine administration.

Then:

* remove root access keys if they exist;
* securely store root credentials;
* use root only for tasks that specifically require it.

## Step 2: Enable MFA

Enable MFA for:

* root;
* administrators;
* other IAM users.

## Step 3: Configure password policies

A password policy can require:

* minimum length;
* complexity;
* password expiration;
* prevention of password reuse.

## Step 4: Create individual identities

Do not make several employees share one username.

Individual accounts provide:

* accountability;
* easier permission management;
* easier access removal;
* better auditing.

## Step 5: Use groups

Examples:

```text
Developers → Development permissions
Auditors   → Read-only permissions
Admins     → Administrative permissions
```

## Step 6: Use roles instead of sharing credentials

Temporary role credentials are safer than distributing one permanent access key among multiple users or services.

## Step 7: Monitor activity with CloudTrail

CloudTrail records AWS API activity.

---

# 16. AWS CloudTrail: the security camera

CloudTrail records actions performed in an AWS account.

It can help answer:

* Who deleted this EC2 instance?
* Who changed the security group?
* When was the S3 bucket policy modified?
* Which API request failed?
* Which user created this IAM role?

### Analogy

CloudTrail is the account’s security-camera footage and activity log.

It records API calls and management activity rather than merely showing performance.

Basic recent event history is available by default, while a trail can be configured for longer-term storage and broader logging.

Logs can be delivered to S3 for retention and analysis.

---

# 17. CloudTrail versus CloudWatch versus Config

These services are easy to confuse.

| Service        | Main question                                       |
| -------------- | --------------------------------------------------- |
| **CloudTrail** | Who performed which action?                         |
| **CloudWatch** | How is the system performing?                       |
| **AWS Config** | How is the resource configured, and has it changed? |

### Example: public S3 bucket

* **CloudTrail:** identifies who changed the bucket policy.
* **AWS Config:** shows that the bucket became non-compliant.
* **CloudWatch:** may monitor related metrics, logs or alarms.

---

# 18. Billing and usage monitoring as security

A sudden bill can be evidence of compromised credentials.

Suppose an attacker steals an access key and launches hundreds of expensive instances.

A billing report or budget alert may reveal unusual activity.

The AWS Cost and Usage Report provides detailed usage and estimated charge information, often delivered to S3.

Security is not only about preventing data theft. Detecting unexpected resource usage also matters.

---

# 19. Securing multiple accounts with AWS Organizations

Large organisations often use multiple AWS accounts.

For example:

```text
Organisation
├── Production account
├── Development account
├── Testing account
├── Finance account
└── Security account
```

**AWS Organizations** enables central management of these accounts.

Accounts can be grouped into **Organizational Units**, or OUs.

```text
Organisation
├── Production OU
│   ├── Production account A
│   └── Production account B
└── Development OU
    ├── Development account A
    └── Testing account
```

Policies can then be applied centrally.

---

# 20. Service Control Policies

A **Service Control Policy**, or **SCP**, sets the maximum permissions available to accounts in an AWS Organization.

An SCP does **not** grant permissions.

It limits what can potentially be granted.

### Analogy

An SCP is the organisation’s outer boundary.

IAM operates inside that boundary.

```text
SCP: Maximum actions the account may ever perform
IAM: Actions a particular user or role is actually granted
```

### Example

An SCP prevents the use of a certain AWS service.

Even if an IAM administrator creates a policy allowing that service, access still fails because the organisation-level boundary blocks it.

Effective permissions are therefore approximately:

```text
Allowed by SCP
AND
Allowed by IAM
=
Actually permitted
```

---

# 21. AWS Key Management Service

**AWS KMS** is used to create and manage encryption keys.

An encryption key is used to transform readable data into unreadable encrypted data and later decrypt it.

KMS can help:

* create keys;
* control who may use keys;
* integrate encryption with AWS services;
* record key usage through CloudTrail.

### Analogy

Encryption is a locked safe.

KMS manages:

* the keys;
* who may use them;
* when they were used;
* which AWS services may access them.

Possessing encrypted data is not enough without the correct key.

---

# 22. Amazon Cognito

Amazon Cognito manages authentication for users of web and mobile applications.

It can support:

* user sign-up;
* sign-in;
* access control;
* social sign-in;
* enterprise identity providers;
* very large user populations.

### IAM versus Cognito

| Service     | Intended users                                        |
| ----------- | ----------------------------------------------------- |
| **IAM**     | Employees, administrators, AWS services and workloads |
| **Cognito** | Customers or end users of applications                |

Example:

* An AWS administrator signing into the console uses IAM.
* A customer signing into a shopping app may use Cognito.

---

# 23. AWS Shield

AWS Shield protects against **Distributed Denial-of-Service**, or DDoS, attacks.

A DDoS attack attempts to overwhelm an application with large amounts of traffic so legitimate users cannot access it.

```text
Thousands of malicious requests
                ↓
           Application
                ↓
       Slower or unavailable
```

AWS Shield provides detection and mitigation.

The chapter distinguishes:

* **AWS Shield Standard** – basic protection available automatically;
* **AWS Shield Advanced** – additional paid protection and capabilities.

---

# 24. Protecting data with encryption

Data can exist in two important states:

```text
Data at rest
Data in transit
```

Both require protection.

---

## Encryption at rest

**Data at rest** means data stored physically.

Examples:

* objects stored in S3;
* files stored in EFS;
* data stored on EBS;
* database records stored in RDS.

Encryption at rest protects stored data if the underlying storage is accessed without authorisation.

```text
Readable data
↓ encryption using key
Unreadable ciphertext
```

Services can integrate with AWS KMS for key management.

---

## Encryption in transit

**Data in transit** means data moving across a network.

Examples:

* browser to website;
* EC2 to EFS;
* corporate network to S3;
* application to database.

Data in transit is usually protected using:

* TLS;
* HTTPS;
* certificates.

The diagram on page 50 shows encrypted traffic between EC2 and EFS, and between an on-premises environment and S3.

### Simple comparison

| State      | Meaning                       | Common protection          |
| ---------- | ----------------------------- | -------------------------- |
| At rest    | Stored on disk or other media | Storage encryption and KMS |
| In transit | Moving across a network       | TLS and HTTPS              |

Encryption at rest does not automatically protect data moving across the network, and transit encryption does not replace storage encryption. Both are needed.

---

# 25. Securing Amazon S3

New S3 buckets and objects are private by default, but access must still be managed carefully when data is shared.

Important controls include:

* S3 Block Public Access;
* IAM policies;
* bucket policies;
* encryption;
* access control lists;
* Trusted Advisor checks.

## S3 Block Public Access

This helps prevent unintended public exposure.

For most private organisational data, public access should remain blocked unless the use case genuinely requires it.

## IAM policy

Useful when access is granted to authenticated IAM identities.

## Bucket policy

A resource-based policy attached directly to the bucket.

## ACL

An older access-control method. It exists, but newer policy mechanisms are generally clearer and more manageable.

---

# 26. Compliance is not automatically inherited

AWS may comply with many standards and regulations, but that does not automatically make every customer workload compliant.

AWS can provide:

* compliant infrastructure;
* certifications;
* audit reports;
* security features;
* legal agreements.

The customer must still:

* configure resources correctly;
* control data access;
* follow relevant regulations;
* maintain records;
* monitor compliance.

Using compliant infrastructure incorrectly can still produce a non-compliant system. Technology has yet to invent a certificate capable of fixing careless configuration.

---

# 27. AWS compliance programs

The module divides compliance support into broad groups.

## Certifications and attestations

These are evaluated by independent auditors.

Examples include ISO standards.

## Laws, regulations and privacy

AWS provides services and agreements that help customers address legal obligations such as privacy or healthcare requirements.

## Alignments and frameworks

These relate to industry or function-specific security guidance and best practices.

The important idea is:

> AWS provides evidence and capabilities, but the customer remains responsible for using them correctly.

---

# 28. AWS Config: the configuration inspector

AWS Config records and evaluates AWS resource configurations.

It can answer:

* Was this security group changed?
* Is this S3 bucket publicly accessible?
* Is encryption enabled?
* Does this resource comply with the required configuration?
* What did this resource look like last week?

Config can compare:

```text
Actual configuration
against
Desired configuration
```

If they do not match, the resource may be marked non-compliant.

### Example

Desired rule:

```text
Every S3 bucket must have encryption enabled.
```

AWS Config evaluates buckets and reports those that do not comply.

---

# 29. AWS Artifact: the compliance document cabinet

AWS Artifact provides access to AWS compliance documents and agreements.

It may include:

* ISO certifications;
* SOC reports;
* PCI-related reports;
* security and compliance documentation.

### Analogy

AWS Artifact is the document cabinet auditors use when they need evidence concerning AWS controls.

It does not configure security resources. It provides reports and agreements.

---

# 30. Complete security story

Imagine a company creates an online healthcare application.

## Account security

The company:

* protects the root user;
* enables MFA;
* creates individual IAM identities;
* follows least privilege.

## Application access

* Developers belong to a Developers group.
* Auditors receive read-only access.
* EC2 assumes an IAM role to access a specific S3 bucket.

## Data security

* Data in S3 and RDS is encrypted at rest.
* Connections use TLS.
* KMS manages encryption keys.

## Monitoring

* CloudTrail records account actions.
* CloudWatch monitors application performance.
* AWS Config checks whether resources remain compliant.

## Organisational control

* AWS Organizations separates production and development accounts.
* SCPs prevent developers from using prohibited services.

## Protection

* AWS Shield helps protect the public application from DDoS attacks.

## Compliance

* AWS Artifact provides relevant compliance reports.
* The company still configures the application according to its legal requirements.

This scenario covers almost the entire module.

---

# 31. Common exam traps

## Trap 1: “AWS secures everything because it is cloud-hosted.”

Incorrect.

AWS secures the underlying cloud. Customers still secure their data, permissions, applications and configurations.

---

## Trap 2: “AWS patches every EC2 operating system.”

Incorrect.

For EC2, the customer manages the guest operating system and patches.

---

## Trap 3: “An IAM role is another permanent user.”

Incorrect.

A role is assumable and normally provides temporary credentials.

---

## Trap 4: “An IAM group can contain another group.”

Incorrect.

Groups contain users and cannot be nested.

---

## Trap 5: “An explicit Allow overrides an explicit Deny.”

Incorrect.

Explicit Deny wins.

---

## Trap 6: “An SCP gives users access.”

Incorrect.

SCPs limit maximum permissions. IAM still has to grant the actual permission.

---

## Trap 7: “CloudWatch records who changed a resource.”

Usually incorrect.

CloudTrail records API actions and identities. CloudWatch focuses on metrics, logs and alarms.

---

## Trap 8: “AWS Artifact automatically makes the workload compliant.”

Incorrect.

Artifact provides reports and documents. The customer must still configure and operate the workload correctly.

---

## Trap 9: “Encryption at rest protects network traffic.”

Incorrect.

Data moving across a network requires encryption in transit, normally through TLS or HTTPS.

---

# 32. Final memory sheet

```text
SHARED RESPONSIBILITY
AWS      → Security OF the cloud
Customer → Security IN the cloud

IAM
User   → Permanent identity
Group  → Collection of users
Policy → Permission document
Role   → Temporary assumable permissions

PERMISSION LOGIC
Explicit Deny > Explicit Allow > Implicit Deny

ACCOUNT SECURITY
Protect root
Enable MFA
Use individual identities
Apply least privilege
Use roles
Enable CloudTrail

SECURITY SERVICES
Organizations → Manage multiple accounts
SCP           → Maximum permission boundary
KMS           → Manage encryption keys
Cognito       → Application-user authentication
Shield        → DDoS protection

DATA
At rest    → Stored data; use storage encryption/KMS
In transit → Moving data; use TLS/HTTPS

MONITORING AND COMPLIANCE
CloudTrail → Who did what?
CloudWatch → How is it performing?
Config     → How is it configured?
Artifact   → Where are the compliance reports?
```

## Chapter in one paragraph

AWS cloud security follows a shared responsibility model in which AWS protects the underlying global infrastructure, while customers protect their data, identities, applications and configurations. IAM controls authentication and authorisation through users, groups, policies and roles, with least privilege and explicit-deny precedence forming the basis of permission management. New accounts should protect the root user, enable MFA, use individual identities and monitor actions through CloudTrail. Organisations can centrally manage accounts with AWS Organizations and SCPs, while KMS, Cognito and Shield support encryption, application identity and DDoS protection. Data should be encrypted both at rest and in transit, and services such as AWS Config and AWS Artifact support configuration auditing and compliance evidence.



---


</details>

<details>
<summary><strong>Module 5: Networking and Content Delivery — Intuitive Explanation</strong></summary>

# Module 5: Networking and Content Delivery — Intuitive Explanation

This chapter is really about one question:

> How does traffic know where to go, what is allowed to enter, and how can AWS deliver content quickly to users around the world?

The module moves through six connected ideas:

```text
Networking basics
      ↓
Amazon VPC
      ↓
Connecting the VPC
      ↓
Securing the VPC
      ↓
Route 53 finds the destination
      ↓
CloudFront delivers content faster
```

Think of AWS networking as designing a private city. The VPC is the city boundary, subnets are neighbourhoods, route tables are road signs, gateways are exits, and security controls decide who may enter. 

---

# 1. The basic idea of a network

A **network** is a group of devices that can communicate with one another.

For example:

```text
Computer A ──┐
Computer B ──┼── Subnet 1 ── Router ── Subnet 2 ── Computer D
Computer C ──┘                              └─────── Computer E
```

The diagram on page 5 shows two subnets connected by a router.

The components have different jobs:

* A **device** sends or receives data.
* A **subnet** groups devices within part of a network.
* A **router** forwards traffic between networks.

### Road analogy

Imagine two residential neighbourhoods.

People within the same neighbourhood can move around locally. To travel from one neighbourhood to another, they use a main road and a junction.

```text
Neighbourhood → Subnet
Junction      → Router
House address → IP address
```

---

# 2. IP addresses

Every device on a network needs an address so traffic knows where to go.

An IPv4 address looks like:

```text
192.0.2.10
```

It contains four numbers, each between 0 and 255.

Although humans see decimal numbers, computers interpret the address in binary:

```text
192        .0         .2         .10
11000000   00000000   00000010   00001010
```

IPv4 uses **32 bits**, while IPv6 uses **128 bits** and supports a vastly larger address space.

Example IPv6:

```text
2600:1f18:22ba:8c00:ba86:a05e:a5ba:00ff
```

For this module, most examples use IPv4 because apparently networking was not already full of enough numbers.

---

# 3. CIDR notation

A network is normally written using **Classless Inter-Domain Routing**, or CIDR.

Example:

```text
192.0.2.0/24
```

The `/24` means that the first 24 bits identify the network. The remaining 8 bits identify individual devices.

```text
192.0.2 | 0–255
Network | Host
```

A `/24` block contains:

```text
2⁸ = 256 total IP addresses
```

The CIDR number works in the opposite direction from what beginners usually expect:

```text
Smaller prefix number → Larger network
Larger prefix number  → Smaller network
```

Examples:

| CIDR  | Total addresses |
| ----- | --------------: |
| `/16` |          65,536 |
| `/24` |             256 |
| `/28` |              16 |

Why?

Because `/16` fixes only 16 bits, leaving another 16 bits available for addresses. `/28` fixes 28 bits and leaves only 4 bits available.

```text
/16 → More flexible bits → More addresses
/28 → Fewer flexible bits → Fewer addresses
```

---

# 4. The OSI model

The OSI model divides network communication into seven conceptual layers.

It is easier to understand as the process of sending a parcel.

| Layer           | Main role                          | Parcel analogy                   |
| --------------- | ---------------------------------- | -------------------------------- |
| 7. Application  | User-facing network services       | Decide what to send              |
| 6. Presentation | Data format and encryption         | Translate and package it         |
| 5. Session      | Manages communication sessions     | Keep the conversation open       |
| 4. Transport    | End-to-end delivery                | Choose reliable or fast delivery |
| 3. Network      | Routing by IP address              | Find the city and road           |
| 2. Data Link    | Communication within local network | Find the building locally        |
| 1. Physical     | Actual signals and bits            | Roads, wires and radio signals   |

Important protocols include:

```text
Layer 7 → HTTP, HTTPS, FTP
Layer 4 → TCP, UDP
Layer 3 → IP
Layer 2 → MAC addresses
```

## TCP versus UDP

**TCP** focuses on reliable delivery.

It checks whether data arrives correctly and in order.

**UDP** focuses on speed.

It sends data without waiting to confirm every part.

```text
TCP → Registered courier with tracking
UDP → Throw the parcel toward the destination and keep moving
```

TCP is useful for:

* websites;
* file transfers;
* email.

UDP is useful for:

* video streaming;
* voice calls;
* online gaming;
* real-time communication.

---

# 5. Amazon VPC: your private network in AWS

**Amazon Virtual Private Cloud**, or **Amazon VPC**, lets a customer create a logically isolated virtual network inside AWS.

Inside a VPC, the customer controls:

* the IP address range;
* subnets;
* routing;
* internet connectivity;
* private connectivity;
* network security.

### City analogy

```text
AWS Cloud → Country
Region    → State
VPC       → Privately owned city
Subnet    → Neighbourhood
EC2       → Building
Route     → Road sign
Gateway   → City entrance or exit
```

AWS owns the underlying infrastructure, but the customer decides how the virtual city is organised.

---

# 6. VPCs and subnets

A VPC belongs to **one AWS Region**, but it can span multiple Availability Zones.

A subnet belongs to **only one Availability Zone**.

The page 12 diagram shows:

```text
Region
└── VPC
    ├── Subnet in Availability Zone 1
    └── Subnet in Availability Zone 2
```

This distinction is frequently tested:

```text
VPC    → Regional
Subnet → Availability Zone-specific
```

A subnet cannot stretch across two Availability Zones.

---

# 7. Public and private subnets

Subnets are commonly described as public or private.

## Public subnet

A public subnet has a route to an **internet gateway**.

It usually hosts resources that must receive internet traffic, such as:

* public web servers;
* load balancers;
* NAT gateways.

## Private subnet

A private subnet has no direct route to an internet gateway.

It commonly hosts:

* databases;
* internal application servers;
* backend services.

```text
Internet
   ↓
Public subnet
   ↓
Private subnet
```

The public subnet is the reception area. The private subnet is the restricted office behind it.

Importantly, a subnet is not public merely because somebody named it `public-subnet`. AWS does not care about optimistic naming. Its route table determines whether it is public.

---

# 8. Choosing a VPC CIDR block

When creating a VPC, an IPv4 CIDR range is assigned.

For example:

```text
VPC: 10.0.0.0/16
```

This provides 65,536 total addresses.

Subnets can then divide this range:

```text
10.0.1.0/24 → Public subnet
10.0.2.0/24 → Private subnet
10.0.3.0/24 → Another subnet
```

Subnet CIDR ranges must not overlap.

Invalid example:

```text
Subnet A: 10.0.1.0/24
Subnet B: 10.0.1.0/25
```

Subnet B exists inside Subnet A’s range, causing overlap.

---

# 9. Reserved addresses in each subnet

AWS reserves five addresses in every IPv4 subnet.

For:

```text
10.0.0.0/24
```

the reserved addresses are:

| Address      | Purpose           |
| ------------ | ----------------- |
| `10.0.0.0`   | Network address   |
| `10.0.0.1`   | VPC router        |
| `10.0.0.2`   | DNS               |
| `10.0.0.3`   | Future use        |
| `10.0.0.255` | Broadcast address |

Therefore:

```text
256 total addresses − 5 reserved = 251 usable addresses
```

This is illustrated in the page 14 diagram.

### Exam trap

A `/24` subnet does not provide 256 usable addresses in AWS.

It provides:

```text
251 usable addresses
```

---

# 10. Private and public IP addresses

An EC2 instance normally receives a **private IP address** from its subnet.

A private address is used for communication inside the VPC.

Example:

```text
10.0.1.15
```

A resource that communicates directly with the internet may also require a public IPv4 address.

## Automatically assigned public IP

AWS may assign a public address when the instance launches, depending on subnet settings.

The address can change after the instance is stopped and started.

## Elastic IP address

An **Elastic IP address** is a public IPv4 address associated with the AWS account.

It can be remapped between resources.

```text
Normal public IP → Temporary
Elastic IP       → Persistent and movable
```

It is useful when a stable public address is required, though unnecessary Elastic IP addresses may incur charges.

---

# 11. Elastic network interfaces

An **Elastic Network Interface**, or ENI, is a virtual network card.

It can contain:

* private IP addresses;
* public IP associations;
* security groups;
* a MAC address.

An ENI can sometimes be detached from one EC2 instance and attached to another.

### Analogy

An EC2 instance is a computer.

The ENI is its network card and network identity.

```text
EC2 instance
└── ENI
    ├── Private IP
    ├── Security groups
    └── MAC address
```

Moving the ENI can move those network attributes to another instance.

---

# 12. Route tables: deciding where traffic goes

A route table contains rules that direct traffic.

Each route has:

```text
Destination → Target
```

Example:

| Destination   | Target           |
| ------------- | ---------------- |
| `10.0.0.0/16` | local            |
| `0.0.0.0/0`   | internet gateway |

The first route means:

> Traffic for the VPC’s internal network stays within the VPC.

The second means:

> All other IPv4 traffic should go to the internet gateway.

`0.0.0.0/0` represents all IPv4 destinations.

### Road-sign analogy

```text
Destination: City centre → Local road
Destination: Anywhere else → Highway exit
```

Every subnet must be associated with a route table. One subnet uses one route table at a time, although one route table can serve several subnets.

---

# 13. The built-in local route

Every VPC route table contains a local route.

Example:

```text
10.0.0.0/16 → local
```

This enables communication between subnets inside the VPC.

It cannot be deleted.

So resources in:

```text
10.0.1.0/24
```

can potentially communicate with resources in:

```text
10.0.2.0/24
```

subject to security groups, network ACLs and other controls.

A route provides a path. It does not automatically grant permission.

---

# 14. Internet gateway

An **internet gateway**, or IGW, connects a VPC to the internet.

The diagram on page 20 shows a public subnet route table containing:

```text
10.0.0.0/16 → local
0.0.0.0/0   → internet gateway
```

For an EC2 instance to communicate directly with the internet, it normally needs:

1. A public IP address.
2. A route to an internet gateway.
3. Security rules allowing the traffic.

```text
Public IP
+ Internet gateway route
+ Security group permission
= Internet connectivity
```

Missing any one of these may break connectivity.

An attached internet gateway alone does not magically make every resource public. Thankfully, AWS networking is not quite that reckless.

---

# 15. NAT gateway

A **Network Address Translation gateway**, or NAT gateway, allows resources in a private subnet to initiate outbound internet connections without accepting unsolicited inbound internet connections.

Example:

A private database server must download software updates.

It needs internet access, but it should not be publicly reachable.

The traffic path is:

```text
Private EC2
    ↓
NAT gateway in public subnet
    ↓
Internet gateway
    ↓
Internet
```

The page 21 diagram shows:

**Private subnet route table:**

```text
0.0.0.0/0 → NAT gateway
```

**Public subnet route table:**

```text
0.0.0.0/0 → Internet gateway
```

### Intuitive difference

```text
Internet gateway → Direct two-way internet path for public resources
NAT gateway      → Outbound path for private resources
```

A NAT gateway belongs in a **public subnet**, because it must reach the internet gateway.

---

# 16. Public versus private architecture

A typical application architecture looks like:

```text
Internet users
      ↓
Internet gateway
      ↓
Public subnet
└── Web server or load balancer
      ↓
Private subnet
└── Database
      ↓
NAT gateway for updates
```

The website must be reachable publicly, while the database should only accept traffic from the application tier.

Putting the database in a private subnet is useful, but it is not sufficient by itself. Security groups must also restrict access.

---

# 17. VPC peering

**VPC peering** connects two VPCs privately.

It can connect VPCs:

* within the same account;
* across accounts;
* across Regions.

Each VPC must add routes for the other VPC’s CIDR range.

Example:

```text
VPC A: 10.0.0.0/16
VPC B: 10.3.0.0/16
```

Routes:

```text
VPC A route table:
10.3.0.0/16 → Peering connection

VPC B route table:
10.0.0.0/16 → Peering connection
```

## Restrictions

The CIDR ranges cannot overlap.

VPC peering is also **not transitive**.

Suppose:

```text
VPC A ↔ VPC B ↔ VPC C
```

A cannot automatically communicate with C merely because both connect to B.

```text
A ↔ B and B ↔ C
does not mean
A ↔ C
```

A separate connection is required.

---

# 18. VPC sharing

VPC sharing lets one AWS account own the VPC while other accounts deploy resources into shared subnets.

The page 22 diagram shows multiple participant accounts placing resources such as EC2 and RDS inside a VPC owned by Account A.

### Analogy

One organisation centrally manages the roads, subnets and gateways, while different departments own the buildings placed inside them.

This improves central network governance without requiring every account to build a separate VPC.

---

# 19. Site-to-Site VPN

An **AWS Site-to-Site VPN** creates an encrypted connection between an on-premises network and an AWS VPC over the public internet.

It commonly involves:

* a **customer gateway** on the company side;
* a **virtual private gateway** on the AWS side;
* an encrypted VPN tunnel between them.

The page 24 diagram shows:

```text
Corporate data centre
        ↓
Customer gateway
        ↓
Encrypted VPN over internet
        ↓
Virtual private gateway
        ↓
AWS VPC
```

### Strengths

* relatively quick to establish;
* encrypted;
* uses existing internet connectivity.

### Limitation

Its performance depends partly on the public internet, which is not exactly famous for signing legally binding promises about latency.

---

# 20. AWS Direct Connect

**AWS Direct Connect** provides a dedicated network connection between an organisation and AWS.

Instead of sending traffic over the ordinary internet, the organisation establishes a private connection through a Direct Connect location.

```text
Corporate network
       ↓
Dedicated connection
       ↓
AWS
```

Compared with Site-to-Site VPN, Direct Connect can provide:

* more consistent performance;
* more predictable bandwidth;
* lower network variability;
* private connectivity.

However, it generally takes more time and cost to establish.

## VPN versus Direct Connect

| Feature         | Site-to-Site VPN        | Direct Connect                            |
| --------------- | ----------------------- | ----------------------------------------- |
| Connection path | Public internet         | Dedicated connection                      |
| Encryption      | Built in                | Not inherently the same as VPN encryption |
| Setup           | Faster                  | More involved                             |
| Performance     | More variable           | More consistent                           |
| Typical use     | Quick secure connection | Long-term enterprise connectivity         |

A VPN can also be used over Direct Connect when both dedicated connectivity and encryption are needed.

---

# 21. VPC endpoints

A **VPC endpoint** allows resources inside a VPC to privately access supported AWS services without using:

* an internet gateway;
* a NAT gateway;
* a public IP address;
* a VPN connection.

Example:

```text
Private EC2
    ↓
VPC endpoint
    ↓
Amazon S3
```

Traffic stays on the AWS network.

The page 26 diagram presents two endpoint types:

## Gateway endpoints

Used for:

* Amazon S3;
* Amazon DynamoDB.

They are represented in route tables.

## Interface endpoints

Powered by AWS PrivateLink.

They create elastic network interfaces with private IP addresses inside the VPC.

### Use case

A private EC2 instance must access an S3 bucket.

Without an endpoint:

```text
EC2 → NAT gateway → Internet gateway → S3 public endpoint
```

With an endpoint:

```text
EC2 → VPC endpoint → S3
```

The second route is more private and can avoid NAT gateway traffic costs.

---

# 22. AWS Transit Gateway

When only two VPCs need to connect, peering is manageable.

When 50 VPCs must communicate, a full mesh of peering connections becomes architectural spaghetti.

The page 27 diagram contrasts:

```text
Many separate peering and VPN connections
```

with:

```text
VPCs
VPN
Direct Connect
   \ | /
Transit Gateway
```

**AWS Transit Gateway** acts as a central networking hub.

### Analogy

Instead of building a direct road between every pair of cities, connect every city to one central highway interchange.

It simplifies connectivity between:

* multiple VPCs;
* VPNs;
* Direct Connect gateways;
* on-premises networks.

---

# 23. Security groups

A **security group** is a virtual firewall that operates at the instance or network-interface level.

The page 32 diagram shows a separate security-group boundary surrounding each EC2 instance.

Security groups control:

* inbound traffic;
* outbound traffic;
* protocols;
* ports;
* source or destination.

Example:

| Direction | Protocol | Port | Purpose    |
| --------- | -------- | ---: | ---------- |
| Inbound   | TCP      |   80 | HTTP       |
| Inbound   | TCP      |  443 | HTTPS      |
| Inbound   | TCP      |   22 | SSH        |
| Outbound  | TCP      | 1433 | SQL Server |

---

# 24. Security-group defaults

A default security group generally:

* denies unsolicited inbound traffic except traffic allowed by its rules;
* allows outbound traffic;
* allows communication from resources associated with the same default security group.

For exam purposes, remember:

```text
Security group rules contain ALLOW rules only.
```

There are no explicit deny rules in security groups.

Traffic not allowed by a rule is denied implicitly.

---

# 25. Security groups are stateful

A security group is **stateful**.

This means return traffic is automatically allowed.

Example:

An inbound rule permits a customer to access a web server on port 443.

```text
Customer → Web server: Allowed by inbound rule
Web server → Customer: Automatically allowed as return traffic
```

A separate outbound rule for that return response is not required.

### Analogy

A stateful guard remembers that a visitor was allowed into the building and lets the same visitor leave without requiring another full inspection.

---

# 26. Network ACLs

A **network access control list**, or network ACL, acts at the subnet level.

The page 35 diagram shows the ACL positioned around the subnet boundary rather than around individual EC2 instances.

```text
Security group → Instance level
Network ACL    → Subnet level
```

A network ACL controls traffic entering and leaving the entire subnet.

---

# 27. Network ACL rules

Unlike security groups, network ACLs support:

* allow rules;
* deny rules.

Rules are numbered and evaluated from the lowest number upward.

Example:

| Rule | Traffic                      | Decision |
| ---: | ---------------------------- | -------- |
|  100 | HTTPS from anywhere          | Allow    |
|  110 | Traffic from malicious range | Deny     |
|  120 | SSH from company network     | Allow    |
|  `*` | Everything else              | Deny     |

The first matching rule wins.

So rule order matters.

```text
100 evaluated before 110
110 evaluated before 120
```

A beautifully written rule at number 500 is useless if rule 100 already matched the traffic.

---

# 28. Network ACLs are stateless

Network ACLs are **stateless**.

Return traffic must be explicitly allowed.

Example:

```text
Inbound rule allows user request
```

This does not automatically allow the response.

An outbound rule must also allow the return traffic.

### Analogy

A stateless guard remembers absolutely nothing. Every time someone passes through the gate, the guard checks the rules again.

---

# 29. Security group versus network ACL

The table on page 38 is one of the most exam-relevant parts of the chapter.

| Feature         | Security group        | Network ACL                   |
| --------------- | --------------------- | ----------------------------- |
| Level           | Instance/ENI          | Subnet                        |
| Rules           | Allow only            | Allow and deny                |
| State           | Stateful              | Stateless                     |
| Rule evaluation | All rules considered  | Lowest-numbered matching rule |
| Return traffic  | Automatically allowed | Must be explicitly allowed    |

## Memory trick

```text
Security Group = Smart guard
- Remembers connections
- Protects individual instance
- Allow rules only

Network ACL = Subnet checkpoint
- Forgets connections
- Protects subnet
- Allow and deny rules
```

---

# 30. Designing a secure VPC

The design activity on page 39 asks for:

* a public website;
* a private database;
* internet access for database updates;
* high availability;
* custom firewall protection.

A sensible design would be:

```text
VPC: 10.0.0.0/16

Availability Zone A
├── Public subnet A:  10.0.1.0/24
│   └── Web server or load balancer
└── Private subnet A: 10.0.2.0/24
    └── Database

Availability Zone B
├── Public subnet B:  10.0.3.0/24
│   └── Web server or load balancer
└── Private subnet B: 10.0.4.0/24
    └── Standby database
```

Connections:

```text
Internet gateway → Public subnets
NAT gateways     → Private subnet outbound access
Security groups  → Restrict web and database traffic
Network ACLs     → Optional subnet-level protection
```

Database security group:

```text
Allow database port
Source: Web-server security group
```

Not:

```text
Allow database port
Source: 0.0.0.0/0
```

Putting the database in a private subnet and then allowing the entire planet to access its port would rather defeat the point.

---

# 31. Amazon Route 53

Humans prefer names such as:

```text
www.example.com
```

Computers communicate using IP addresses such as:

```text
192.0.2.10
```

The **Domain Name System**, or DNS, translates names into addresses.

**Amazon Route 53** is AWS’s highly available DNS service.

It can:

* register domain names;
* translate names into IP addresses;
* route users to resources;
* perform health checks;
* support failover;
* route to AWS and non-AWS infrastructure.

### Phonebook analogy

```text
Person’s name → Phone number
Domain name   → IP address
```

Route 53 is essentially the internet’s address directory, except much less likely to be used as a booster seat.

---

# 32. DNS resolution process

The page 43 flow can be understood like this:

1. The user enters `www.example.com`.
2. The user’s DNS resolver asks Route 53 for the destination.
3. Route 53 returns the corresponding IP address.
4. The browser connects to that address.

```text
www.example.com
      ↓
Route 53 lookup
      ↓
192.0.2.10
      ↓
Application
```

Route 53 directs users to destinations. It does not itself host the web application.

---

# 33. Route 53 routing policies

Route 53 supports several routing policies.

## Simple routing

Use one or more records without special routing logic.

Suitable for a basic single-resource environment.

## Weighted routing

Send different proportions of traffic to different resources.

Example:

```text
Version A → 90%
Version B → 10%
```

Useful for:

* gradual deployments;
* testing;
* traffic distribution.

## Latency-based routing

Send users to the Region providing the lowest network latency.

Useful for global applications.

## Geolocation routing

Route based on the user’s geographic location.

Example:

```text
Malaysian users → Asia application
European users  → Europe application
```

## Geoproximity routing

Route based on the location of resources and optionally shift traffic between them.

## Failover routing

Use a primary resource while healthy, then send traffic to a secondary resource if the primary fails.

## Multivalue answer routing

Return multiple healthy records, up to a limited set, to distribute traffic.

---

# 34. Route 53 health checks and failover

Route 53 can monitor the health of a resource.

Example:

```text
Primary application → Healthy
Route 53 directs traffic to primary
```

If the primary becomes unhealthy:

```text
Primary application → Unhealthy
Route 53 directs traffic to backup
```

The page 47 diagram shows a primary multi-tier application with a secondary S3 static website.

```text
Normal condition:
User → Primary application

Failure condition:
User → Secondary S3 website
```

The secondary site may provide reduced functionality, but a basic maintenance page is usually preferable to users staring at a browser error and questioning every decision that led them there.

---

# 35. Multi-Region deployment

A global application may run in several AWS Regions.

Example:

```text
US users      → US Region
Asian users   → Asia-Pacific Region
European users → European Region
```

Route 53 can select a destination based on:

* latency;
* geography;
* health;
* traffic weights.

Benefits include:

* lower latency;
* improved availability;
* regional disaster recovery;
* better global performance.

Multi-Region design is more complex and costly, so it is not automatically the correct answer for every tiny application.

---

# 36. Network latency

**Latency** is the delay between sending a request and receiving a response.

When a user is far from the server, data may pass through many routers or **hops**.

```text
User
 ↓ hop
Router
 ↓ hop
Router
 ↓ hop
Origin server
```

More physical distance and more network hops can increase latency.

This is why a website hosted far away may feel slower even when the server itself is powerful.

A fast server located on the other side of the world cannot negotiate with the speed of light.

---

# 37. Content delivery networks

A **Content Delivery Network**, or CDN, stores cached copies of content in locations around the world.

Instead of every user retrieving a file from the original server, users may retrieve it from a nearby cache.

Without CDN:

```text
Malaysian user → Server in United States
```

With CDN:

```text
Malaysian user → Nearby edge cache
```

A CDN commonly caches static content such as:

* images;
* videos;
* JavaScript files;
* CSS;
* downloads.

It can also accelerate dynamic content through optimised network paths.

---

# 38. Amazon CloudFront

**Amazon CloudFront** is AWS’s CDN service.

It uses:

* edge locations;
* Regional edge caches;
* AWS’s global network.

The original source of the content is called the **origin**.

Possible origins include:

* Amazon S3;
* EC2;
* Elastic Load Balancing;
* an external web server.

---

# 39. How CloudFront caching works

Suppose a user requests an image.

## Cache hit

The image already exists at the nearby edge location.

```text
User → Edge location → Cached image returned
```

This is fast.

## Cache miss

The edge location does not have the image.

```text
User
 ↓
Edge location
 ↓
Regional edge cache
 ↓
Origin server
```

The image is retrieved and cached for future requests.

Later users can receive it from the edge rather than repeatedly contacting the origin.

---

# 40. Edge locations and Regional edge caches

The page 53 world map illustrates CloudFront’s distributed infrastructure.

## Edge location

A site close to users that stores popular content.

## Regional edge cache

A larger cache positioned between edge locations and the origin.

It can retain content that is not popular enough to remain at every individual edge location.

```text
User
 ↓
Edge location
 ↓
Regional edge cache
 ↓
Origin
```

This reduces the number of requests sent back to the origin.

---

# 41. CloudFront benefits

CloudFront offers several main benefits.

## Lower latency

Content is delivered from locations closer to users.

## Reduced origin load

Cached content does not have to be repeatedly retrieved from the original server.

## Global scalability

Many edge locations can serve large numbers of users.

## Security

CloudFront integrates with AWS security services and can help absorb or filter traffic at the edge.

## AWS integration

It works closely with:

* S3;
* Elastic Load Balancing;
* AWS Shield;
* AWS WAF;
* Route 53;
* Certificate Manager.

---

# 42. Route 53 versus CloudFront

These services are often confused.

| Service    | Main job                                   |
| ---------- | ------------------------------------------ |
| Route 53   | Finds where users should go                |
| CloudFront | Delivers content from locations near users |

### Restaurant analogy

```text
Route 53  → Directory telling you which branch to visit
CloudFront → Nearby branch already holding the food
```

Route 53 translates and routes.

CloudFront caches and delivers.

They often work together:

```text
User enters domain
      ↓
Route 53 resolves destination
      ↓
CloudFront edge location serves content
```

---

# 43. Important networking service comparisons

## Internet gateway versus NAT gateway

| Internet gateway                           | NAT gateway                                     |
| ------------------------------------------ | ----------------------------------------------- |
| Direct internet connection                 | Outbound internet for private resources         |
| Used by public subnets                     | Used on behalf of private subnets               |
| Supports inbound and outbound connectivity | Does not permit unsolicited inbound connections |
| Attached to VPC                            | Deployed in public subnet                       |

## VPN versus Direct Connect

| VPN                   | Direct Connect              |
| --------------------- | --------------------------- |
| Uses public internet  | Dedicated connection        |
| Encrypted tunnel      | More consistent performance |
| Faster to establish   | More involved to establish  |
| More variable latency | More predictable            |

## Peering versus Transit Gateway

| VPC peering                     | Transit Gateway                |
| ------------------------------- | ------------------------------ |
| Direct connection between VPCs  | Central hub                    |
| Good for a small number of VPCs | Better for many networks       |
| Non-transitive                  | Supports hub-and-spoke routing |
| Can become difficult at scale   | Centralises management         |

## Route 53 versus CloudFront

| Route 53              | CloudFront                      |
| --------------------- | ------------------------------- |
| DNS                   | CDN                             |
| Resolves domain names | Caches content                  |
| Selects destination   | Accelerates delivery            |
| Can perform failover  | Reduces latency and origin load |

---

# 44. Common exam traps

## Trap 1: “A VPC spans several Regions.”

Incorrect.

A VPC belongs to one Region.

It may span multiple Availability Zones within that Region.

---

## Trap 2: “A subnet spans several Availability Zones.”

Incorrect.

A subnet belongs to exactly one Availability Zone.

---

## Trap 3: “A subnet is public because it has a public name.”

Incorrect.

A public subnet requires a route to an internet gateway.

---

## Trap 4: “An internet gateway alone gives EC2 internet access.”

Incomplete.

The instance also needs suitable routing, a public address and security permission.

---

## Trap 5: “A NAT gateway lets internet users connect to private EC2 instances.”

Incorrect.

It permits private resources to initiate outbound connections.

---

## Trap 6: “VPC peering is transitive.”

Incorrect.

```text
A ↔ B and B ↔ C
does not provide A ↔ C
```

---

## Trap 7: “Security groups support deny rules.”

Incorrect.

Security groups contain allow rules only.

---

## Trap 8: “Network ACLs are stateful.”

Incorrect.

Network ACLs are stateless.

Return traffic must be explicitly allowed.

---

## Trap 9: “Security groups protect the subnet.”

Incorrect.

Security groups operate at the instance or ENI level.

Network ACLs operate at the subnet level.

---

## Trap 10: “Route 53 delivers cached website content.”

Incorrect.

Route 53 handles DNS and routing.

CloudFront caches and delivers content.

---

# 45. Final memory sheet

```text
NETWORK BASICS
IP address → Identifies a device
CIDR       → Defines an address range
Router     → Directs traffic
Subnet     → Divides a network

AWS NETWORK STRUCTURE
VPC    → Regional virtual network
Subnet → One Availability Zone
Route table → Chooses traffic path
ENI    → Virtual network card

INTERNET CONNECTIVITY
Internet gateway → Public internet access
NAT gateway      → Outbound internet for private resources
VPC endpoint     → Private access to AWS services

NETWORK CONNECTIONS
VPC peering      → Connect two VPCs
VPC sharing      → Multiple accounts use shared subnets
Site-to-Site VPN → Encrypted connection over internet
Direct Connect   → Dedicated private connection
Transit Gateway  → Central networking hub

SECURITY
Security group:
- Instance level
- Stateful
- Allow rules only

Network ACL:
- Subnet level
- Stateless
- Allow and deny rules
- Lowest-numbered matching rule wins

ROUTE 53
- DNS
- Domain name to IP address
- Routing policies
- Health checks
- Failover

CLOUDFRONT
- CDN
- Edge locations
- Caching
- Lower latency
- Reduced origin load
```

# Chapter in one paragraph

Amazon VPC lets customers create isolated virtual networks within an AWS Region. A VPC is divided into subnets that belong to individual Availability Zones, while route tables determine where traffic is sent. Public resources can connect through an internet gateway, whereas private resources can initiate outbound internet access through a NAT gateway or privately access AWS services using VPC endpoints. VPCs and on-premises networks can be connected using peering, VPN, Direct Connect or Transit Gateway. Security groups protect individual resources using stateful allow rules, while network ACLs protect subnets using stateless allow and deny rules. Route 53 translates domain names and routes users based on policies and health, while CloudFront caches content at global edge locations to reduce latency and improve delivery performance.

---



</details>

<details>
<summary><strong>Module 6: Compute — Intuitive and Narrative Explanation</strong></summary>

# Module 6: Compute — Intuitive and Narrative Explanation

This module answers one central question:

> **Where should an application run in AWS, and how much control should AWS manage for you?**

AWS provides several compute choices because not every workload should be forced onto a traditional server. Sometimes full server control is necessary. Sometimes only a container is needed. Sometimes only a small piece of code needs to run for three seconds. Renting an entire virtual machine for that would be rather like renting a whole shopping mall to sell one cup of coffee.

The module mainly covers:

```text
Amazon EC2          → Rent and manage virtual machines
Containers          → Package and run applications consistently
AWS Lambda          → Run code only when triggered
Elastic Beanstalk   → Upload a web application and let AWS deploy it
```

These services differ mainly in the amount of **control** and **management responsibility** given to the customer. 

---

# 1. The big idea: compute in AWS

**Compute** refers to the processing power used to run applications.

Traditionally, an organisation buys a physical server:

```text
Buy server
↓
Install operating system
↓
Configure networking
↓
Install application
↓
Maintain hardware
↓
Replace it when outdated
```

AWS changes this model. Instead of buying a physical machine, compute resources can be requested whenever needed.

```text
Need server → Launch EC2
Need containers → Use ECS or EKS
Need short event-driven code → Use Lambda
Need to deploy a web app quickly → Use Elastic Beanstalk
```

The difficult part is not merely knowing the service names. The real question is:

> **How much infrastructure does the organisation want to manage?**

---

# 2. The compute-management spectrum

The table on page 6 categorises the main compute services.

| Service           | Model                       | Customer mainly manages                     |
| ----------------- | --------------------------- | ------------------------------------------- |
| Amazon EC2        | Infrastructure as a Service | OS, software, configuration and application |
| Amazon ECS/EKS    | Container computing         | Containers and application                  |
| AWS Fargate       | Serverless containers       | Containers, without managing servers        |
| AWS Lambda        | Serverless functions        | Function code                               |
| Elastic Beanstalk | Platform as a Service       | Application code                            |

This can be viewed as a management ladder:

```text
More control                                     Less infrastructure work

Amazon EC2 → Containers on EC2 → Fargate → Elastic Beanstalk → Lambda
```

More management is not automatically better. It merely means more things are available to misconfigure at 2 a.m.

---

# 3. Amazon EC2: renting a virtual computer

**Amazon Elastic Compute Cloud**, or **Amazon EC2**, provides virtual machines called **EC2 instances**.

An EC2 instance can act as:

* a web server;
* an application server;
* a database server;
* a file server;
* a game server;
* a mail server;
* a computing server.

The main advantage is control. The customer can choose:

* Windows or Linux;
* CPU and memory;
* storage;
* networking;
* installed software;
* security configuration.

### Apartment analogy

Imagine AWS owns a large apartment building.

An EC2 instance is an apartment rented inside it.

AWS maintains:

* the building;
* electricity;
* physical security;
* structural maintenance.

The customer controls:

* the furniture;
* the occupants;
* what is installed;
* how the apartment is used.

The physical building is AWS infrastructure, while the guest operating system and software inside the instance remain the customer’s responsibility.

---

# 4. The nine EC2 launch decisions

The module explains nine decisions made when launching an EC2 instance:

```text
1. AMI
2. Instance type
3. Network settings
4. IAM role
5. User data
6. Storage
7. Tags
8. Security group
9. Key pair
```

These choices answer nine practical questions:

```text
What software should the machine begin with?
How powerful should it be?
Where should it run?
What AWS services may it access?
What setup should happen automatically?
Where should its data be stored?
How should it be identified?
What traffic may reach it?
How will administrators log in securely?
```

---

# 5. Amazon Machine Image: the starting template

An **Amazon Machine Image**, or **AMI**, is a template used to create an EC2 instance.

An AMI can contain:

* an operating system;
* installed software;
* configuration;
* storage information.

### House-plan analogy

An AMI is a house blueprint.

The blueprint is not the house itself. It describes how new houses should be created.

```text
AMI → Launch → EC2 instance
Blueprint → Construction → House
```

Possible AMI sources include:

| Source          | Meaning                                        |
| --------------- | ---------------------------------------------- |
| Quick Start     | Standard AWS-provided Windows and Linux images |
| My AMIs         | Images created by the customer                 |
| AWS Marketplace | Preconfigured third-party images               |
| Community AMIs  | Publicly shared images                         |

Community AMIs should be treated cautiously. “Uploaded by a stranger on the internet” is not normally considered a strong security certification.

---

# 6. Creating a custom AMI

The diagram on page 13 shows the process:

```text
Existing AMI
    ↓
Launch EC2 instance
    ↓
Install or configure software
    ↓
Capture the modified instance
    ↓
New custom AMI
```

For example, an organisation may:

1. Launch a Linux instance.
2. Install a web server.
3. Install company monitoring software.
4. Apply security configurations.
5. Save the configured instance as a new AMI.
6. Launch identical instances from that AMI.

This makes deployments repeatable.

A custom AMI can also be copied to another AWS Region.

---

# 7. Choosing an instance type

The **instance type** determines the resources available to the EC2 instance:

* virtual CPU;
* memory;
* storage options;
* network performance.

The instance type should match the workload.

AWS instance families include:

| Category              | Best suited for                    |
| --------------------- | ---------------------------------- |
| General purpose       | Balanced workloads                 |
| Compute optimised     | CPU-intensive processing           |
| Memory optimised      | Applications requiring large RAM   |
| Accelerated computing | GPU, machine learning and graphics |
| Storage optimised     | High local storage performance     |

### Employee analogy

Choosing an instance type is like hiring an employee.

A graphic designer may need powerful graphics hardware. An accountant may need memory and reliable storage. Hiring an expensive specialist for a simple filing job wastes money.

Likewise, a machine-learning workload may need accelerated computing, while a small website may only need a general-purpose instance.

---

# 8. Reading an instance name

The slide on page 15 uses:

```text
t3.large
```

It can be divided into:

```text
t → Instance family
3 → Generation
large → Size
```

The family describes the type of workload.

The generation indicates the version of that family.

The size indicates the amount of resources.

For example:

```text
t3.micro
t3.small
t3.medium
t3.large
t3.xlarge
```

Larger sizes generally provide more CPU and memory.

A larger instance is not automatically “better.” It is merely more expensive when the workload does not need it.

---

# 9. Network settings

When launching an EC2 instance, the customer selects:

* the VPC;
* the subnet;
* whether to assign a public IP address.

The network decision determines where the instance exists and how it can communicate.

```text
VPC
├── Public subnet
│   └── Public web server
└── Private subnet
    └── Internal application or database
```

A public-facing web server may require:

* a public subnet;
* a public IP address;
* a route to an internet gateway;
* a security-group rule permitting web traffic.

A database normally belongs in a private subnet because random internet users have no convincing reason to communicate directly with it.

---

# 10. IAM role for EC2

An EC2 instance may need to access another AWS service.

For example:

```text
EC2 application → Read file from Amazon S3
```

The recommended approach is to attach an **IAM role** to the instance.

The role provides temporary permissions.

```text
EC2 instance
    ↓ Uses IAM role
Amazon S3
```

Without a role, developers may be tempted to store long-term access keys inside the instance or application code. That is convenient right up until the keys are accidentally uploaded somewhere public.

### Key distinction

* **Security groups** control network traffic.
* **IAM roles** control AWS API permissions.

A security group does not grant permission to read an S3 object.

An IAM role does not open port 443 to the internet.

---

# 11. User data

**User data** is a script that can run when an EC2 instance is first launched.

Example:

```bash
#!/bin/bash
yum update -y
yum install -y httpd
```

The script might:

* install software;
* download application files;
* apply settings;
* start services;
* register the instance with another system.

### Hotel analogy

The AMI is the standard hotel room design.

User data is a guest request submitted before arrival:

```text
Place an extra bed
Set the air conditioning
Prepare conference equipment
```

Instead of building a separate AMI for every small difference, user data can customise instances during launch.

---

# 12. EC2 storage choices

An EC2 instance normally needs a **root volume**, which contains the operating system.

Additional volumes can be attached for application data.

The main storage options discussed are:

```text
Amazon EBS
EC2 Instance Store
Amazon EFS
Amazon S3
```

The most important comparison is between **Amazon EBS** and **Instance Store**.

---

# 13. Amazon EBS

**Amazon Elastic Block Store**, or **Amazon EBS**, provides persistent block storage.

The data remains when the EC2 instance is stopped and started again.

```text
EC2 stopped
↓
EBS data remains
↓
EC2 started
↓
Data is still available
```

EBS is comparable to a detachable hard drive.

It exists separately from the physical host running the EC2 instance.

Typical uses include:

* operating-system volumes;
* application files;
* databases;
* persistent data.

---

# 14. EC2 Instance Store

**Instance Store** provides temporary storage physically attached to the host computer.

It offers high local performance, but the data is ephemeral.

If the instance is stopped, terminated or moved away from the host, the data may be lost.

```text
Instance Store = Fast temporary workspace
EBS            = Persistent storage
```

### Desk analogy

EBS is a filing cabinet that remains after the employee leaves the room.

Instance Store is the paper spread across the employee’s desk. Once the desk is cleared, the papers are gone.

Instance Store is suitable for:

* caches;
* temporary files;
* replicated data;
* data that can be recreated.

It should not be the only location for important data.

---

# 15. Tags

A **tag** is metadata assigned to an AWS resource.

A tag normally contains:

```text
Key = Value
```

Examples:

```text
Name = WebServer1
Environment = Production
Department = Finance
Owner = DevelopmentTeam
```

Tags support:

* searching and filtering;
* automation;
* access control;
* cost allocation;
* resource organisation.

Without tags, an AWS account can eventually become a digital warehouse containing hundreds of resources called things like `test-final-2-real-final`.

---

# 16. Security groups

A **security group** acts as a virtual firewall for an EC2 instance.

It controls allowed traffic according to:

* protocol;
* port;
* source or destination.

Example:

| Purpose            | Protocol | Port | Source          |
| ------------------ | -------- | ---: | --------------- |
| Website            | TCP      |   80 | Anywhere        |
| Secure website     | TCP      |  443 | Anywhere        |
| SSH administration | TCP      |   22 | Company IP only |

Security groups exist outside the guest operating system.

The operating system may also have its own firewall, but that is separate.

### Important principle

Only open the ports that are required.

Opening every port to every IP address certainly makes connectivity easier. So does leaving every door in a building unlocked.

---

# 17. Key pairs

A key pair contains:

* a public key stored by AWS;
* a private key stored by the customer.

For Linux instances, the private key is commonly used for SSH access.

For Windows instances, it can be used to retrieve the administrator password.

```text
AWS stores public key
Customer stores private key
```

The private key must be protected.

If it is lost, AWS cannot casually reconstruct it. That would rather undermine the point of private-key security.

---

# 18. EC2 lifecycle

The lifecycle diagram on page 29 shows the main EC2 states:

```text
AMI
 ↓
Pending
 ↓
Running
```

From running, the instance may be:

```text
Rebooted
Stopped
Hibernated
Terminated
```

## Reboot

Equivalent to restarting a computer.

```text
Running → Rebooting → Running
```

The instance stays on the same host, and its IP addresses normally remain unchanged.

## Stop

The instance is shut down but can be started later.

```text
Running → Stopping → Stopped
```

Only EBS-backed instances can be stopped.

## Terminate

The instance is permanently deleted.

```text
Running → Shutting down → Terminated
```

Termination is not an unusually dramatic form of stopping. The instance cannot simply be started again.

---

# 19. Stop versus terminate

| Action    | Instance can restart? | EBS data                     | Compute charges        |
| --------- | --------------------- | ---------------------------- | ---------------------- |
| Reboot    | Yes                   | Remains                      | Continue               |
| Stop      | Yes                   | Remains                      | Instance compute stops |
| Terminate | No                    | Depends on deletion settings | Stops permanently      |

An attached EBS volume may continue generating storage charges even when the EC2 instance is stopped.

Stopping the server does not make every related cost disappear. AWS billing would be tragically less interesting if it did.

---

# 20. Public IP behaviour

When an EC2 instance is rebooted:

```text
Public IP → Does not normally change
Private IP → Does not change
```

When it is stopped and started:

```text
Automatically assigned public IP → May change
Private IP → Remains
```

When a persistent public address is required, use an **Elastic IP address**.

An Elastic IP remains allocated to the AWS account until it is released.

---

# 21. EC2 instance metadata

Instance metadata provides information about the running EC2 instance.

Examples include:

* instance ID;
* private IP;
* public IP;
* Availability Zone;
* Region;
* security groups;
* hostname.

Applications can use metadata to configure themselves dynamically.

For example:

```text
Application starts
↓
Reads Availability Zone from metadata
↓
Adjusts configuration
```

Metadata is available from a special local address accessible from the instance.

The broader lesson is that a program does not always need hard-coded infrastructure information.

---

# 22. Monitoring EC2 with CloudWatch

**Amazon CloudWatch** collects metrics from EC2 instances.

Examples include:

* CPU utilisation;
* network traffic;
* disk operations;
* status checks.

The slide on page 32 distinguishes:

| Monitoring          | Metric interval |
| ------------------- | --------------: |
| Basic monitoring    |       5 minutes |
| Detailed monitoring |        1 minute |

Basic monitoring is enabled by default.

Detailed monitoring provides more frequent data but may involve additional charges.

### Doctor analogy

CloudWatch is the health monitor attached to the server.

It does not automatically cure every problem, but it reveals symptoms:

```text
CPU constantly at 95%
Network traffic suddenly drops
Status check fails
```

The information can then be used for alarms, scaling or troubleshooting.

---

# 23. EC2 versus a managed service

The activity compares running Microsoft SQL Server on:

```text
Amazon EC2
versus
Amazon RDS
```

## SQL Server on EC2

The customer manages more:

* operating system;
* database installation;
* patches;
* backups;
* high availability;
* configuration.

Benefit:

* greater control;
* custom database settings;
* access to the operating system;
* support for unusual configurations.

## SQL Server on Amazon RDS

AWS manages more:

* database provisioning;
* backups;
* patching;
* monitoring;
* high-availability features.

Benefit:

* lower administrative effort;
* easier deployment;
* managed failover options.

### Restaurant analogy

EC2 is renting a kitchen and cooking everything personally.

RDS is ordering from a managed catering service.

The rented kitchen gives more control, but someone must clean it.

---

# 24. EC2 pricing models

The module introduces several EC2 pricing models:

```text
On-Demand Instances
Reserved Instances
Spot Instances
Dedicated Instances
Dedicated Hosts
Scheduled Reserved Instances
```

The correct option depends on workload behaviour.

---

# 25. On-Demand Instances

With On-Demand pricing:

* no long-term commitment is required;
* payment is based on usage;
* capacity can be launched when required.

Best suited for:

* short-term workloads;
* unpredictable workloads;
* development and testing;
* applications with uncertain demand.

### Hotel analogy

On-Demand is booking a hotel room one night at a time.

It is flexible, but the price per night is generally higher than a long-term arrangement.

---

# 26. Reserved Instances

Reserved Instances involve a one-year or three-year commitment in exchange for lower pricing.

Best suited for:

* steady workloads;
* predictable usage;
* systems expected to run continuously;
* applications requiring long-term capacity planning.

### Rental analogy

A Reserved Instance is similar to signing a long-term rental contract.

The lower price is attractive only when the resource will actually be used. Reserving the wrong instance is simply a discounted way to waste money.

---

# 27. Spot Instances

Spot Instances use unused AWS capacity at a lower price.

However, AWS may interrupt the instance, with a short interruption notification.

Best suited for:

* batch processing;
* rendering;
* fault-tolerant workloads;
* flexible jobs;
* workloads that can resume after interruption.

Not suitable for:

* a single critical database;
* an irreplaceable stateful workload;
* systems unable to tolerate interruption.

### Airline analogy

A Spot Instance is like receiving a very cheap standby airline seat.

The price is attractive, but the arrangement is not designed around certainty.

---

# 28. Dedicated Instances and Dedicated Hosts

## Dedicated Instance

Runs on hardware dedicated to one customer.

The customer does not necessarily control the specific physical host.

## Dedicated Host

Provides an entire physical server dedicated to the customer.

It may help with:

* compliance requirements;
* regulatory requirements;
* server-bound software licences;
* bring-your-own-licence arrangements;
* physical host visibility.

Dedicated Hosts are not selected because an ordinary web server feels lonely.

---

# 29. Matching pricing to workload

The use-case table on page 41 can be simplified as:

| Workload pattern                  | Suitable pricing |
| --------------------------------- | ---------------- |
| Unpredictable or temporary        | On-Demand        |
| Flexible and interruptible        | Spot             |
| Stable and predictable            | Reserved         |
| Licensing or compliance-sensitive | Dedicated Host   |

Memory trick:

```text
Uncertain → On-Demand
Interruptible → Spot
Predictable → Reserved
Regulated → Dedicated
```

---

# 30. The four pillars of EC2 cost optimisation

The diagram on page 42 presents four pillars:

```text
1. Right-size
2. Increase elasticity
3. Select the optimal pricing model
4. Optimise storage choices
```

Cost optimisation is not merely searching for the cheapest instance.

A cheap service used incorrectly can still produce an impressively expensive bill.

---

# 31. Pillar 1: Right-size

Right-sizing means matching resources to actual requirements.

Consider:

* CPU;
* RAM;
* storage;
* networking.

CloudWatch metrics can reveal whether an instance is underused.

Example:

```text
Instance has 16 vCPUs
Average usage is 4%
```

Possible response:

```text
Move to a smaller instance
```

Best-practice order:

```text
Measure
↓
Right-size
↓
Then consider reservation
```

Do not reserve an oversized instance first merely because the discount looks attractive.

---

# 32. Pillar 2: Increase elasticity

Elasticity means using resources only when required.

Examples:

* stop development servers at night;
* stop test environments on weekends;
* automatically add servers during demand;
* remove servers when demand falls.

```text
Low demand → Fewer instances
High demand → More instances
```

A server that is running but performing no useful work is not “ready for the future.” It is billing the present.

---

# 33. Pillar 3: Use the correct pricing model

Different parts of an application may use different pricing models.

Example:

```text
Baseline demand → Reserved Instances
Unexpected demand → On-Demand Instances
Interruptible batch jobs → Spot Instances
```

There is no requirement to choose only one model for the whole architecture.

Combining models often produces a better balance of cost and reliability.

---

# 34. Pillar 4: Optimise storage

Storage optimisation includes:

* selecting the correct EBS volume type;
* reducing oversized volumes;
* deleting unnecessary snapshots;
* moving suitable data to Amazon S3;
* using lifecycle policies;
* removing unattached volumes.

The cheapest storage is not necessarily appropriate, but the most expensive storage is not automatically necessary.

The proper question is:

> What performance and durability does the application actually require?

---

# 35. Containers

A **container** packages an application together with what it needs to run.

This may include:

* code;
* runtime;
* libraries;
* dependencies;
* configuration.

The key benefit is consistency:

```text
Developer laptop
Test environment
Production environment
```

The same container should behave consistently across all three.

This reduces the famous technical explanation:

> “It worked on my computer.”

An explanation that is emotionally honest but operationally useless.

---

# 36. Containers versus virtual machines

A virtual machine includes a complete guest operating system.

A container shares the host operating system while isolating the application.

```text
Virtual machine:
Application
Libraries
Guest operating system

Container:
Application
Libraries
Shared host operating system
```

Therefore, containers are generally:

* smaller;
* quicker to start;
* quicker to stop;
* more resource-efficient.

The diagram on page 52 shows three containers running on one EC2 instance, while three virtual machines require separate guest operating systems.

---

# 37. Docker

**Docker** is a platform used to build, package and run containers.

The basic flow is:

```text
Dockerfile
↓
Container image
↓
Running container
```

## Image

A container image is a template containing the packaged application.

## Container

A container is a running instance of that image.

This resembles the AMI and EC2 relationship:

```text
AMI → EC2 instance
Container image → Container
```

A blueprint is not the building. An image is not the running container.

---

# 38. Container orchestration

Running one container manually is manageable.

Running hundreds across many servers requires orchestration.

Container orchestration handles:

* scheduling;
* deployment;
* replacement;
* networking;
* load distribution;
* scaling.

Suppose five copies of an application are required:

```text
Container A × 3
Container B × 2
```

An orchestration platform determines:

* which server should run each container;
* whether enough resources exist;
* how failed containers are replaced;
* how traffic is distributed.

---

# 39. Amazon ECS

**Amazon Elastic Container Service**, or **Amazon ECS**, is AWS’s container orchestration service.

It helps:

* run Docker containers;
* organise containers into clusters;
* scale containers;
* replace failed tasks;
* integrate with load balancers, IAM and security groups.

The page 54 diagram shows ECS receiving requests for several containers and distributing them across EC2 instances.

### Hotel-manager analogy

Containers are hotel guests.

EC2 instances are rooms.

ECS is the manager deciding:

* which room each guest receives;
* when another room is needed;
* what happens if a room becomes unavailable.

---

# 40. ECS with EC2 versus ECS with Fargate

ECS containers can run using two broad approaches.

## ECS backed by EC2

The customer manages:

* EC2 instances;
* operating systems;
* capacity;
* patching;
* scaling of the underlying servers.

Benefit:

* more infrastructure control.

## ECS backed by AWS Fargate

AWS manages the underlying servers.

The customer mainly specifies:

* container image;
* CPU;
* memory;
* networking;
* permissions.

Benefit:

* less operational work.

```text
ECS on EC2 → Manage containers and servers
ECS on Fargate → Manage containers, not servers
```

Fargate is often described as **serverless compute for containers**.

Servers still exist, naturally. They have not transcended into another dimension. AWS simply manages them.

---

# 41. Kubernetes

**Kubernetes** is open-source container orchestration software.

Docker helps run containers.

Kubernetes coordinates containers across multiple machines.

```text
Docker → Runs containers
Kubernetes → Manages container clusters
```

Kubernetes automates:

* container deployment;
* networking;
* scaling;
* load distribution;
* replacement of failed containers.

It can operate both on-premises and in the cloud.

---

# 42. Amazon EKS

**Amazon Elastic Kubernetes Service**, or **Amazon EKS**, allows Kubernetes to run on AWS.

Use EKS when:

* Kubernetes compatibility is required;
* an organisation already uses Kubernetes;
* portability is important;
* existing Kubernetes tools are needed.

The simplest distinction is:

```text
ECS → AWS-native container orchestration
EKS → Managed Kubernetes on AWS
```

EKS is not automatically better because Kubernetes sounds more impressive. It may introduce more complexity than a simple application requires.

---

# 43. Amazon ECR

**Amazon Elastic Container Registry**, or **Amazon ECR**, stores container images.

Think of the relationship as:

```text
ECR → Stores container images
ECS/EKS → Runs and manages containers
Fargate/EC2 → Provides compute
```

### Warehouse analogy

ECR is the warehouse where packaged applications are stored.

ECS or EKS is the logistics manager.

EC2 or Fargate is the transport and physical capacity used to run them.

ECR itself does not execute the application.

---

# 44. AWS Lambda

**AWS Lambda** is a serverless compute service that runs code in response to events or schedules.

The customer provides a function.

AWS manages:

* servers;
* operating systems;
* scaling;
* availability;
* much of the execution environment.

```text
Event occurs
↓
Lambda function runs
↓
Task completes
↓
Execution stops
```

Payment is based mainly on requests and execution duration rather than a continuously running virtual machine.

---

# 45. What serverless means

Serverless does not mean that no servers exist.

It means the customer does not provision or manage them directly.

```text
Traditional server:
Create server → Patch OS → Maintain server → Run code

Lambda:
Upload function → Configure trigger → Code runs
```

AWS handles the underlying server fleet.

This is useful when the task is small, event-driven or unpredictable.

---

# 46. Lambda event sources

A Lambda function can be triggered by services such as:

* Amazon S3;
* Amazon DynamoDB;
* Amazon SNS;
* Amazon SQS;
* Amazon API Gateway;
* Application Load Balancer;
* scheduled events.

Example:

```text
Image uploaded to S3
↓
S3 triggers Lambda
↓
Lambda creates thumbnail
↓
Thumbnail stored in another S3 bucket
```

The diagram on page 66 illustrates this workflow.

---

# 47. Lambda execution role

A Lambda function may need permission to access other AWS resources.

For example:

```text
Read image from source S3 bucket
Write thumbnail to target S3 bucket
```

The Lambda function uses an **execution role**.

The role grants only the permissions required by the function.

```text
Lambda function
↓ assumes
Execution role
↓ permits
S3 read and write
```

Again:

* the event source starts the function;
* the execution role gives it permission.

These are related but not the same thing.

---

# 48. Schedule-based Lambda example

The page 65 diagram shows Lambda starting and stopping EC2 instances according to time.

```text
Scheduled event
↓
Lambda triggered
↓
IAM role gives EC2 permission
↓
EC2 instances stopped
```

Later:

```text
Scheduled event
↓
Lambda triggered
↓
EC2 instances started
```

This can reduce cost for development environments that are unnecessary overnight.

Lambda is therefore not only for web applications. It is also useful for automation.

---

# 49. Benefits of Lambda

The module lists benefits including:

* support for several programming languages;
* automatic administration;
* built-in fault tolerance;
* automatic scaling;
* pay-per-use pricing;
* event-driven execution.

Lambda is suitable for:

* file processing;
* automation;
* API backends;
* scheduled jobs;
* notifications;
* data transformation;
* small independent tasks.

It is less suitable for:

* applications requiring a permanently running server;
* workloads needing full operating-system control;
* very long-running processes;
* applications exceeding Lambda runtime or resource limits.

---

# 50. Lambda quotas from the module

The slides identify several limits, including:

```text
Maximum execution time → 15 minutes
Maximum memory         → 10,240 MB
```

These limits matter in exam scenarios.

A workload expected to run continuously for several hours is not a natural Lambda use case.

A batch job can sometimes be divided into smaller functions, but simply placing an oversized traditional application into Lambda and hoping for enlightenment is not an architecture.

---

# 51. AWS Elastic Beanstalk

**AWS Elastic Beanstalk** is a managed service for deploying web applications.

The developer uploads application code.

Elastic Beanstalk can handle:

* infrastructure provisioning;
* deployment;
* load balancing;
* automatic scaling;
* health monitoring;
* logging;
* application environment setup.

```text
Upload code
↓
Elastic Beanstalk creates environment
↓
Application is deployed
↓
AWS monitors and scales resources
```

It supports platforms such as:

* Java;
* .NET;
* PHP;
* Node.js;
* Python;
* Ruby;
* Go;
* Docker.

---

# 52. Elastic Beanstalk responsibilities

The page 71 diagram can be understood as:

```text
Customer manages:
Application code

AWS manages:
HTTP server
Application server
Language platform
Operating system
Infrastructure
```

Elastic Beanstalk gives developers an easier deployment process while still using underlying AWS resources such as EC2, Auto Scaling and load balancers.

The customer can still access and configure those resources when necessary.

---

# 53. Elastic Beanstalk pricing

There is no separate service charge for Elastic Beanstalk itself.

The customer pays for the resources created underneath it, such as:

* EC2 instances;
* load balancers;
* storage;
* databases;
* data transfer.

This distinction matters:

```text
Elastic Beanstalk service charge → None
Underlying AWS resources → Charged
```

“No additional charge” does not mean “the entire application runs for free.” AWS has not accidentally invented charity-based cloud infrastructure.

---

# 54. Elastic Beanstalk versus EC2

| Amazon EC2                         | Elastic Beanstalk                             |
| ---------------------------------- | --------------------------------------------- |
| Customer configures infrastructure | Service configures much of the infrastructure |
| Greater control                    | Faster deployment                             |
| More administrative work           | Less management complexity                    |
| Suitable for custom environments   | Suitable for standard web applications        |

Use EC2 when:

* full OS control is required;
* custom software must be installed;
* unusual architecture is needed.

Use Elastic Beanstalk when:

* a standard web application must be deployed quickly;
* the team wants to focus on application code;
* automatic scaling and monitoring should be configured more easily.

---

# 55. Lambda versus Elastic Beanstalk

| AWS Lambda               | Elastic Beanstalk                          |
| ------------------------ | ------------------------------------------ |
| Function-based           | Application-based                          |
| Event-driven             | Long-running web application               |
| No server management     | Underlying EC2 resources exist             |
| Runs only when triggered | Application environment remains available  |
| Execution limits apply   | Suitable for conventional web applications |

Example:

```text
Resize an uploaded image → Lambda
Host a Python web application → Elastic Beanstalk
```

---

# 56. EC2 versus containers versus Lambda versus Beanstalk

| Requirement                          | Recommended starting point |
| ------------------------------------ | -------------------------- |
| Full control over OS and server      | EC2                        |
| Package a portable application       | Container                  |
| AWS-native container orchestration   | ECS                        |
| Kubernetes compatibility             | EKS                        |
| Containers without server management | Fargate                    |
| Store container images               | ECR                        |
| Short event-driven code              | Lambda                     |
| Quickly deploy a standard web app    | Elastic Beanstalk          |

This is the heart of the module.

---

# 57. A complete application story

Imagine a photo-sharing website.

## EC2 approach

The company launches EC2 instances and manually installs the application.

```text
Users
↓
Load balancer
↓
EC2 web servers
↓
Database
```

This gives full control but requires more administration.

## Container approach

The application is packaged into containers.

```text
Container images stored in ECR
↓
ECS or EKS deploys containers
↓
EC2 or Fargate provides compute
```

This improves portability and deployment consistency.

## Lambda approach

When a user uploads an image:

```text
S3 upload
↓
Lambda triggered
↓
Thumbnail created
```

No continuously running thumbnail server is required.

## Elastic Beanstalk approach

The development team uploads the web application.

```text
Application code
↓
Elastic Beanstalk
↓
EC2 + Load Balancer + Auto Scaling
```

Elastic Beanstalk configures much of the environment.

A real architecture may use several of these services together rather than selecting only one.

---

# 58. Common exam traps

## Trap 1: “An AMI is a running virtual machine.”

Incorrect.

An AMI is a template used to create an EC2 instance.

---

## Trap 2: “A larger EC2 instance is always better.”

Incorrect.

The correct instance should match the workload. Oversized instances waste money.

---

## Trap 3: “User data runs continuously.”

Incorrect.

User data normally runs during initial instance launch unless additional configuration changes that behaviour.

---

## Trap 4: “IAM roles and security groups perform the same job.”

Incorrect.

```text
IAM role → AWS service permissions
Security group → Network traffic
```

---

## Trap 5: “EBS data disappears when the instance stops.”

Incorrect.

EBS is persistent.

Instance Store is ephemeral.

---

## Trap 6: “Stopping and terminating an EC2 instance are the same.”

Incorrect.

A stopped EBS-backed instance can be started again.

A terminated instance cannot.

---

## Trap 7: “The public IP always remains after stop and start.”

Incorrect.

An automatically assigned public IP may change.

Use an Elastic IP when persistence is required.

---

## Trap 8: “Spot Instances are suitable for every low-cost workload.”

Incorrect.

They may be interrupted and should be used for fault-tolerant or flexible workloads.

---

## Trap 9: “Containers contain a complete guest operating system.”

Generally incorrect.

Containers share the host operating-system kernel and are lighter than virtual machines.

---

## Trap 10: “ECR runs containers.”

Incorrect.

ECR stores container images.

ECS or EKS orchestrates containers.

EC2 or Fargate provides compute.

---

## Trap 11: “Fargate replaces ECS.”

Incorrect.

Fargate is a compute option that can run containers managed by ECS or EKS.

---

## Trap 12: “Serverless means no servers exist.”

Incorrect.

AWS manages the servers so the customer does not have to.

---

## Trap 13: “Lambda is suitable for a function running for several hours.”

Incorrect.

The module states a maximum execution duration of 15 minutes.

---

## Trap 14: “Elastic Beanstalk is completely free.”

Misleading.

There is no separate Elastic Beanstalk fee, but the underlying AWS resources are charged.

---

# 59. Memory sheet

```text
COMPUTE OPTIONS

Amazon EC2
- Virtual machines
- Full OS control
- Customer manages more

AMI
- Template for an EC2 instance
- Contains OS and optional software

Instance type
- Determines CPU, RAM, storage and networking

User data
- Startup script
- Customises instance during launch

IAM role
- Grants AWS service permissions

Security group
- Controls network traffic

Key pair
- Secure administrative login
```

```text
EC2 STORAGE

Amazon EBS
- Persistent block storage
- Data remains after stop/start

Instance Store
- Temporary local storage
- Data may disappear when instance stops or terminates
```

```text
EC2 PRICING

On-Demand
- Flexible
- Unpredictable workloads

Reserved
- Long-term commitment
- Predictable workloads

Spot
- Cheaper
- Can be interrupted

Dedicated Host
- Physical server dedicated to one customer
- Licensing and compliance
```

```text
COST OPTIMISATION

1. Right-size resources
2. Increase elasticity
3. Select optimal pricing
4. Optimise storage
```

```text
CONTAINERS

Docker
- Builds and runs containers

ECR
- Stores container images

ECS
- AWS container orchestration

EKS
- Kubernetes on AWS

Fargate
- Serverless compute for containers
```

```text
AWS LAMBDA

- Serverless functions
- Event-driven
- Automatic scaling
- Pay for usage
- Maximum runtime in module: 15 minutes
```

```text
ELASTIC BEANSTALK

- Managed web-application deployment
- Upload code
- AWS handles provisioning, scaling and monitoring
- No separate service fee
- Pay for underlying resources
```

# Module 6 in one paragraph

AWS provides several compute services for different levels of control and management. Amazon EC2 provides virtual machines that customers configure using an AMI, instance type, network settings, IAM role, user data, storage, tags, security groups and key pairs. EBS provides persistent storage, while Instance Store provides temporary local storage. EC2 costs can be optimised by right-sizing resources, increasing elasticity, selecting the correct pricing model and optimising storage. Containers package applications and their dependencies, while ECS and EKS orchestrate containers, ECR stores their images and Fargate runs them without requiring customers to manage servers. AWS Lambda runs event-driven functions using a serverless model, whereas Elastic Beanstalk simplifies the deployment and management of conventional web applications.



---

</details>

<details>
<summary><strong>Module 7: Storage — Intuitive and Narrative Explanation</strong></summary>

# Module 7: Storage — Intuitive and Narrative Explanation

This module answers one practical question:

> **Where should data be stored in AWS, based on how the application needs to use it?**

AWS offers several storage services because data is not always used in the same way. An operating system needs something resembling a hard drive. Thousands of servers may need a shared folder. Photos and videos need scalable object storage. Old legal records may need to be kept for years but almost never opened.

Trying to solve all of those problems with one storage service would be like using a refrigerator to store clothes, money, food and archived tax documents. Technically, some of it might fit. That does not make it sensible.

Module 7 focuses on four services:

```text
Amazon EBS        → Block storage for EC2
Amazon S3         → Object storage
Amazon EFS        → Shared network file storage
Amazon S3 Glacier → Low-cost archival storage
```

The most important exam skill is not memorising four names. It is identifying the **storage behaviour required by the scenario**. 

---

# 1. The big picture: four storage needs

Imagine a company operating an online video platform.

It may need:

```text
EC2 server operating system     → Amazon EBS
Uploaded videos and images      → Amazon S3
Shared files for many servers   → Amazon EFS
Videos archived for ten years   → Amazon S3 Glacier
```

The services can be remembered through four physical analogies:

| AWS service       | Analogy                               | Main purpose       |
| ----------------- | ------------------------------------- | ------------------ |
| Amazon EBS        | A hard drive attached to one computer | Block storage      |
| Amazon S3         | A warehouse of labelled packages      | Object storage     |
| Amazon EFS        | A shared office network drive         | File storage       |
| Amazon S3 Glacier | A remote archive warehouse            | Long-term archival |

---

# 2. The three fundamental storage types

Before learning the AWS services, understand the three storage models:

```text
Block storage
Object storage
File storage
```

Each organises and accesses data differently.

---

# 3. Block storage

Block storage divides data into small blocks.

An operating system sees it as a disk and can create a file system on top of it.

Suppose there is a 1-GB document, but only one character changes.

With block storage:

```text
1-GB file
↓
Find the block containing the character
↓
Update only that block
```

The diagram on page 7 illustrates this difference: block storage modifies only the affected piece, rather than replacing the whole file.

Block storage is suitable for:

* operating systems;
* databases;
* applications that frequently modify data;
* boot volumes;
* low-latency workloads.

In AWS, the main block-storage service in this module is **Amazon EBS**.

---

# 4. Object storage

Object storage treats each file as a complete object.

An object usually contains:

```text
Data
Metadata
Unique key or name
```

If part of an object changes, the object is generally replaced as a whole.

```text
Object uploaded
↓
Object stored as one unit
↓
Application retrieves the object using its key
```

Object storage is suitable for:

* photos;
* videos;
* backups;
* documents;
* website assets;
* log files;
* datasets.

In AWS, **Amazon S3** provides object storage.

---

# 5. File storage

File storage organises data through familiar directories and file names:

```text
/projects
    /group-assignment
        report.docx
        dataset.csv
```

Applications access the files through a file-system protocol.

File storage is useful when multiple users or servers need to work with the same directory structure.

In AWS, **Amazon EFS** provides shared file storage for Linux-based systems.

---

# 6. Why the storage type matters

Consider three application requests:

### Request A

> “The EC2 instance needs a boot disk.”

Use **EBS**, because an operating system needs block storage.

### Request B

> “Users upload millions of photos.”

Use **S3**, because photos are complete objects.

### Request C

> “Ten EC2 instances must access the same files.”

Use **EFS**, because a shared network file system is required.

The correct answer depends on how data must behave, not merely how much data exists.

---

# Section 1: Amazon Elastic Block Store

# 7. What is Amazon EBS?

**Amazon Elastic Block Store**, or **Amazon EBS**, provides block-level storage volumes for EC2 instances.

An EBS volume behaves similarly to a virtual hard drive.

```text
EC2 instance
    │
    └── EBS volume
```

The EC2 instance can:

* install an operating system on it;
* create a file system;
* store application data;
* host a database;
* read and write individual blocks.

Amazon EBS volumes are automatically replicated inside their Availability Zone for protection against component failure.

---

# 8. EBS is separate from the EC2 instance

One of the most important ideas is:

> **An EBS volume exists independently from the EC2 instance.**

Consider:

```text
EC2 instance stopped
↓
EBS volume remains
↓
Instance starts again
↓
Stored data remains available
```

This is different from temporary Instance Store storage.

### Computer analogy

The EC2 instance is the computer.

The EBS volume is an external hard drive connected to that computer.

Turning off the computer does not erase the external drive.

---

# 9. EBS and Availability Zones

An EBS volume is created in a specific **Availability Zone**.

Normally, an EBS volume must be attached to an EC2 instance in the same Availability Zone.

```text
Availability Zone A
├── EC2 instance
└── EBS volume
```

A volume created in Availability Zone A cannot simply be attached directly to an instance in Availability Zone B.

To move the data:

```text
EBS volume in AZ A
↓
Create snapshot
↓
Create new volume in AZ B
```

This is an important distinction:

```text
EBS volume → Availability Zone resource
EBS snapshot → Can be used to create another volume
```

---

# 10. Common EBS uses

Amazon EBS is commonly used for:

* EC2 boot volumes;
* databases;
* enterprise applications;
* application data;
* file systems;
* development environments;
* virtual desktops.

A simple rule:

> Use EBS when an EC2 instance needs something that behaves like a disk.

---

# 11. SSD versus HDD

EBS volume types are broadly divided into:

```text
Solid-State Drive volumes
Hard Disk Drive volumes
```

## SSD

Designed for workloads where the number of individual read-and-write operations matters.

Examples:

* boot volumes;
* databases;
* interactive applications;
* virtual desktops.

## HDD

Designed for workloads where large amounts of sequential data must be transferred.

Examples:

* big data;
* log processing;
* data warehouses;
* infrequently accessed data.

---

# 12. IOPS versus throughput

Two performance terms appear repeatedly:

## IOPS

**Input/output operations per second**

IOPS measures how many storage operations can be completed each second.

It matters when an application makes many small, separate requests.

Example:

```text
Database:
Read customer record
Update order
Write transaction
Read inventory
```

A database may perform thousands of small operations, making IOPS important.

## Throughput

Throughput measures how much data can be transferred per second.

It matters when processing large continuous files.

Example:

```text
Read a 100-GB log file sequentially
```

### Traffic analogy

IOPS is the number of vehicles that can pass through a road.

Throughput is the total amount of cargo transported.

A road could handle many motorcycles but little cargo, or fewer large trucks carrying enormous amounts of data.

---

# 13. General Purpose SSD

General Purpose SSD is recommended for most ordinary workloads.

Typical uses include:

* boot volumes;
* virtual desktops;
* development environments;
* test environments;
* low-latency applications;
* general application storage.

Use it when the scenario does not demand unusually high storage performance.

It is effectively the sensible default, which is refreshing because AWS services occasionally provide enough options to make choosing a hard drive feel like choosing a university degree.

---

# 14. Provisioned IOPS SSD

Provisioned IOPS SSD is intended for critical workloads requiring consistently high IOPS.

Typical uses include:

* large databases;
* critical business applications;
* applications requiring sustained storage performance.

The customer provisions the required IOPS level.

```text
Ordinary workload → General Purpose SSD
High-performance database → Provisioned IOPS SSD
```

The key exam phrases are:

* high IOPS;
* sustained performance;
* critical database;
* latency-sensitive;
* business-critical application.

---

# 15. Throughput-Optimised HDD

Throughput-Optimised HDD is intended for frequently accessed, throughput-intensive workloads.

Typical uses include:

* big-data processing;
* data warehouses;
* log processing;
* streaming workloads;
* large sequential reads and writes.

It cannot be used as a boot volume according to the module.

The keyword is **throughput**, not high IOPS.

---

# 16. Cold HDD

Cold HDD is designed for large amounts of infrequently accessed data where low cost is important.

Typical scenario:

```text
Large dataset
↓
Rarely accessed
↓
Sequential throughput more important than IOPS
↓
Cold HDD
```

It also cannot be used as a boot volume.

Be careful not to confuse Cold HDD with S3 Glacier:

* Cold HDD is still an EBS volume attached to EC2.
* Glacier is archival object storage.

---

# 17. EBS volume type summary

| Volume type          | Technology | Best use                             |
| -------------------- | ---------- | ------------------------------------ |
| General Purpose      | SSD        | Most workloads and boot volumes      |
| Provisioned IOPS     | SSD        | High-performance databases           |
| Throughput-Optimised | HDD        | Big data, logs and data warehouses   |
| Cold                 | HDD        | Infrequently accessed, low-cost data |

Memory trick:

```text
Normal workload     → General Purpose
Database performance → Provisioned IOPS
Large streaming data → Throughput-Optimised
Rarely used HDD data → Cold
```

---

# 18. EBS snapshots

An **EBS snapshot** is a point-in-time backup of an EBS volume.

```text
EBS volume
↓
Create snapshot
↓
Snapshot stored by AWS
↓
Create a new volume later
```

Snapshots are useful for:

* backup;
* disaster recovery;
* creating copies;
* moving data between Availability Zones;
* creating volumes in another Region after copying the snapshot.

### Photography analogy

An EBS volume is a room being actively used.

A snapshot is a photograph of the room at one point in time.

The photograph does not continue changing when furniture is later moved.

---

# 19. A snapshot is not a live volume

This distinction is frequently tested:

```text
EBS volume   → Active storage used by EC2
EBS snapshot → Point-in-time backup
```

An EC2 instance does not use the snapshot directly as a normal disk.

Instead:

```text
Snapshot
↓
Create new EBS volume
↓
Attach volume to EC2
```

---

# 20. EBS encryption

EBS volumes can be encrypted.

Encryption can protect:

* data stored on the volume;
* data transferred between EC2 and EBS;
* snapshots created from the volume;
* volumes created from encrypted snapshots.

The module states that EBS encryption does not carry an additional encryption charge.

Encryption does not mean the data becomes impossible to access. It means access depends on the correct permissions and encryption key.

---

# 21. EBS elasticity

EBS is described as elastic because storage can be adjusted.

The customer may:

* increase volume capacity;
* change volume types;
* adjust performance settings.

Example:

```text
Application begins with 100 GB
↓
Data grows
↓
Increase EBS volume to 300 GB
```

After increasing the AWS volume, the operating system may still need its file system expanded. Clicking a button in AWS does not always magically persuade Linux to understand the extra space.

---

# 22. EBS pricing

The module identifies several EBS cost components:

```text
Provisioned storage
Provisioned IOPS
Snapshots
Cross-Region data transfer
```

Important principles:

* Charges are based on the amount provisioned, not merely the amount of data written.
* Snapshots incur storage charges.
* Inbound data transfer is generally free in the context described.
* Cross-Region outbound transfer may incur charges.

Example:

```text
Provision 500 GB
Use only 80 GB
↓
Still pay based on 500 GB provisioned
```

Cloud providers are generally reluctant to reward customers for allocating storage they do not use.

---

# 23. EBS lab logic

The lab shown on pages 17–18 follows this sequence:

```text
Create EBS volume
↓
Attach it to an EC2 instance
↓
Configure the operating system to use it
↓
Create a snapshot
↓
Restore a volume from the snapshot
```

This demonstrates the complete EBS lifecycle:

```text
Volume → Attach → Format/Mount → Snapshot → Restore
```

---

# Section 2: Amazon Simple Storage Service

# 24. What is Amazon S3?

**Amazon Simple Storage Service**, or **Amazon S3**, is a fully managed object-storage service.

Data is stored as objects inside buckets.

```text
Bucket
├── photo.jpg
├── report.pdf
├── video.mp4
└── data.csv
```

A bucket is the container.

An object is the stored file plus its metadata and key.

---

# 25. Bucket and object analogy

Imagine a warehouse.

```text
Bucket → Warehouse
Object → Package
Object key → Package label
Metadata → Description attached to package
```

A package can be retrieved using its label.

Unlike EBS, S3 is not normally attached to EC2 as a traditional hard drive. Applications communicate with it through URLs, APIs, SDKs or the AWS CLI.

---

# 26. S3 scale

The module describes Amazon S3 as providing virtually unlimited storage.

A single object can be up to 5 TB according to the slides.

The practical model is:

```text
Create a bucket
↓
Upload objects
↓
S3 handles underlying storage infrastructure
```

The customer does not provision a 10-TB bucket in advance. The bucket grows as objects are added.

---

# 27. S3 durability

Amazon S3 is designed for **11 nines of durability**:

```text
99.999999999%
```

Durability refers to the probability that stored objects will not be lost.

S3 achieves high durability by redundantly storing data across multiple facilities within the selected Region.

The diagram on page 26 shows one object represented in multiple facilities inside the Region.

### Durability is not availability

These terms are related but different:

```text
Durability   → Will the data survive?
Availability → Can the data be accessed right now?
```

A service could preserve data safely but temporarily be unavailable.

---

# 28. S3 is Regional

When creating an S3 bucket, an AWS Region is selected.

The data is stored redundantly within that Region.

```text
Choose Region
↓
Create bucket
↓
Upload object
↓
AWS stores redundant copies within the Region
```

The bucket is not automatically copied to every AWS Region.

Cross-Region Replication can be configured separately, but it is not automatic merely because S3 has a cheerful global-looking icon.

---

# 29. Accessing S3

S3 can be accessed through:

* AWS Management Console;
* AWS CLI;
* SDKs;
* REST APIs;
* object URLs.

This allows:

```text
User application
EC2 instance
Corporate data centre
Command-line script
```

to interact with the same S3 bucket, assuming the required permissions exist.

---

# 30. S3 use cases

Common uses include:

* backups;
* static website hosting;
* application assets;
* media hosting;
* software distribution;
* big-data staging;
* logs;
* disaster recovery;
* data lakes.

Example:

```text
Website code runs on EC2
↓
Images and videos stored in S3
↓
Users retrieve media objects
```

S3 is ideal for complete files that need highly scalable storage.

---

# 31. Why S3 is not EBS

Suppose a database changes a few bytes in a large database file thousands of times per second.

S3 would be an awkward choice because it treats the file as an object.

EBS allows block-level updates.

```text
Frequently modify parts of a disk → EBS
Store and retrieve complete files → S3
```

S3 is excellent storage, but it is not a universal answer to every question containing the word “data.”

---

# 32. S3 bucket URLs

The module presents two URL styles.

## Path style

```text
https://s3.<region>.amazonaws.com/<bucket-name>
```

## Virtual-hosted style

```text
https://<bucket-name>.s3-<region>.amazonaws.com
```

The important conceptual point is:

```text
Bucket name + Region + Object key
```

identify where an object is accessed.

For most subjective exams, understanding the structure matters more than memorising punctuation in historical endpoint formats.

---

# 33. S3 storage classes

S3 offers storage classes for different access patterns.

The module lists:

* S3 Standard;
* S3 Intelligent-Tiering;
* S3 Standard-Infrequent Access;
* S3 One Zone-Infrequent Access;
* S3 Glacier;
* S3 Glacier Deep Archive.

The basic trade-off is:

```text
More frequent and faster access → Higher storage cost
Less frequent and slower access → Lower storage cost
```

---

# 34. S3 Standard

S3 Standard is intended for frequently accessed data.

Typical uses:

* active application data;
* websites;
* frequently viewed images;
* frequently downloaded files;
* dynamic workloads.

It provides high durability and availability.

Use it when access is regular and unpredictable.

---

# 35. S3 Standard-Infrequent Access

S3 Standard-IA is designed for data that is accessed less frequently but still requires rapid retrieval when needed.

Typical uses:

* backups;
* disaster-recovery copies;
* older project files;
* data retained but not opened regularly.

The storage price is lower than S3 Standard, but retrieval charges may apply.

```text
Rare access
+
Immediate retrieval required
=
S3 Standard-IA
```

“Infrequent” does not mean archival. The data can still be retrieved quickly.

---

# 36. S3 One Zone-Infrequent Access

S3 One Zone-IA stores data in a single Availability Zone rather than across multiple Availability Zones.

It is suitable when:

* low cost is important;
* data is infrequently accessed;
* the data can be recreated;
* multi-AZ resilience is not required.

It is less resilient than storage classes designed across multiple Availability Zones.

Suitable example:

```text
Secondary copy of recreatable data
```

Unsuitable example:

```text
Only existing copy of irreplaceable legal records
```

Unless the organisation's disaster-recovery strategy is based on optimism.

---

# 37. S3 Intelligent-Tiering

S3 Intelligent-Tiering is designed for data where access patterns are uncertain or change over time.

It can move objects between access tiers based on usage.

```text
Frequently accessed
↓ access decreases
Move to lower-cost tier
↓ access increases
Move back to frequent-access tier
```

Use it when the organisation cannot confidently predict whether objects will remain hot or become cold.

---

# 38. S3 Glacier classes

Glacier storage classes are intended for archives.

They provide lower storage cost in exchange for slower or more expensive retrieval.

Typical uses:

* regulatory records;
* historical media;
* long-term backups;
* scientific archives;
* compliance data.

The phrase **“archival”** is the strongest clue.

---

# 39. S3 pricing

The module identifies four main S3 pricing factors:

```text
1. Storage class
2. Amount of storage
3. Requests
4. Data transfer
```

## Storage

Charged based on the amount stored.

## Requests

Different operations may incur charges:

* GET;
* PUT;
* COPY;
* POST;
* LIST.

## Data transfer

The module states:

* transfers into S3 are free;
* transfer out of the Region may incur charges;
* transfer to certain AWS services in the same Region may not incur transfer charges.

The important exam lesson is:

> S3 cost is not only the number of gigabytes stored.

A bucket with millions of requests or heavy outbound transfer can generate costs even when its stored data looks modest.

---

# Section 3: Amazon Elastic File System

# 40. What is Amazon EFS?

**Amazon Elastic File System**, or **Amazon EFS**, provides managed file storage over a network.

It allows multiple Linux EC2 instances to access the same file system.

```text
EC2 instance A ─┐
EC2 instance B ─┼── Amazon EFS
EC2 instance C ─┘
```

All instances can work with shared files and directories.

This is the central reason EFS exists.

---

# 41. Shared-drive analogy

Imagine a university computer lab.

Each computer has its own local disk, but students can also access a shared network drive.

```text
Local hard drive → Similar idea to EBS
Shared network drive → Similar idea to EFS
```

When one computer saves a file to the shared drive, another computer can read it.

---

# 42. EFS features

The module identifies these major features:

* shared file storage;
* automatic growth and reduction;
* petabyte-scale capacity;
* low-latency access;
* support for NFS 4.0 and 4.1;
* compatibility with Linux-based EC2 instances;
* managed storage infrastructure.

EFS is useful for:

* content-management systems;
* web serving;
* media processing;
* big-data analysis;
* shared home directories;
* shared application files.

---

# 43. What is NFS?

**Network File System**, or **NFS**, is a protocol that allows a computer to access files over a network as though they belong to a mounted file system.

```text
Remote EFS file system
↓ NFS
Appears as a directory on Linux EC2
```

For example:

```text
/mnt/shared
```

may point to an EFS file system.

Applications can work with files using ordinary file-system operations rather than object-storage API calls.

---

# 44. EFS architecture

The diagram on page 39 shows one EFS file system being accessed through **mount targets** in multiple Availability Zones.

```text
Availability Zone A → Mount target
Availability Zone B → Mount target
Availability Zone C → Mount target
                           ↓
                      One EFS file system
```

A mount target provides a network endpoint through which resources in an Availability Zone access EFS.

For high availability, mount targets are generally created in the Availability Zones where EC2 instances run.

---

# 45. EFS mount targets

An EFS mount target:

* is created in a subnet;
* has a network interface;
* uses security groups;
* connects EC2 instances to the EFS file system;
* belongs to the same VPC;
* is normally created once per Availability Zone.

The mount target is not another copy of the file system.

It is an access point to the same shared EFS storage.

```text
Mount target ≠ Separate file system
Mount target = Network entrance to EFS
```

---

# 46. EFS implementation sequence

The module gives this implementation flow:

```text
1. Create the EC2 resources
2. Create the EFS file system
3. Create mount targets in appropriate subnets
4. Connect EC2 instances to the mount targets
5. Verify security and configuration
```

Security groups must permit the required NFS traffic.

Without appropriate network access, the file system can exist perfectly well while every instance fails to mount it. AWS will have fulfilled its part; the architecture will merely be decorative.

---

# 47. EFS elasticity and pricing

EFS automatically scales as files are added or removed.

```text
Add files
↓
Capacity increases

Delete files
↓
Capacity decreases
```

The customer does not usually provision a fixed volume size in advance.

The module describes EFS as pay-for-what-you-use storage.

This contrasts with an EBS volume, where provisioned capacity matters.

---

# 48. EFS versus EBS

| Amazon EBS                          | Amazon EFS                           |
| ----------------------------------- | ------------------------------------ |
| Block storage                       | File storage                         |
| Behaves like a disk                 | Behaves like a network file system   |
| Usually attached to an EC2 instance | Shared by multiple EC2 instances     |
| Availability Zone-based             | Designed for multi-AZ access         |
| Capacity is provisioned             | Capacity scales automatically        |
| Boot volumes supported              | Not used as a normal EC2 boot volume |

Scenario:

> “Several EC2 web servers need the same uploaded files.”

Use **EFS**, not separate EBS volumes.

Separate disks do not magically synchronise because they share a logo.

---

# 49. EFS versus S3

| Amazon EFS                              | Amazon S3                          |
| --------------------------------------- | ---------------------------------- |
| File storage                            | Object storage                     |
| Uses files and directories              | Uses buckets and objects           |
| Mounted through NFS                     | Accessed through APIs and URLs     |
| Shared Linux file system                | Massive object repository          |
| Application uses normal file operations | Application uses object operations |

Use EFS when an application expects a traditional shared directory.

Use S3 when applications can store and retrieve complete objects.

---

# Section 4: Amazon S3 Glacier

# 50. What is Amazon S3 Glacier?

Amazon S3 Glacier is designed for:

* long-term archives;
* very low storage cost;
* high durability;
* data that is rarely retrieved.

Examples include:

* medical archives;
* compliance records;
* scientific data;
* historical media;
* long-term backups;
* digital preservation.

The trade-off is straightforward:

```text
Lower storage cost
↓
Slower retrieval
```

Cheap storage is possible partly because AWS does not promise that every forgotten file will leap back into the application immediately.

---

# 51. Archive analogy

S3 Standard is like keeping a document on the desk.

S3 Standard-IA is like keeping it in a filing cabinet.

S3 Glacier is like moving it to a secure archive building outside the city.

```text
Desk            → Immediate, frequently used
Filing cabinet  → Less frequent, still accessible
Archive facility → Rare access, retrieval takes longer
```

The archive is cheaper, but retrieving a folder may require a formal request and waiting time.

---

# 52. Glacier durability and security

The module states that S3 Glacier is designed for 11 nines of durability.

Security features include:

* encryption in transit using SSL or TLS;
* encryption at rest;
* IAM access control;
* AES-256 encryption;
* managed encryption keys;
* Vault Lock for compliance policies.

Vault Lock is useful when records must be protected from modification or deletion under regulatory rules.

---

# 53. Glacier retrieval options

The module gives three retrieval choices:

| Retrieval type | Approximate time in module | Best use                    |
| -------------- | -------------------------: | --------------------------- |
| Expedited      |                1–5 minutes | Urgent small retrieval      |
| Standard       |                  3–5 hours | Normal archive retrieval    |
| Bulk           |                 5–12 hours | Large, non-urgent retrieval |

The pattern is:

```text
Faster retrieval → Higher retrieval cost
Slower retrieval → Lower retrieval cost
```

So the question is not merely “How cheap is the storage?”

It is also:

> “How quickly might the archived data be needed?”

---

# 54. S3 versus Glacier

| Amazon S3 Standard       | S3 Glacier                      |
| ------------------------ | ------------------------------- |
| Active object storage    | Archival object storage         |
| Millisecond access       | Minutes or hours                |
| Higher storage price     | Lower storage price             |
| Frequently accessed data | Rarely accessed data            |
| Normal request pricing   | Retrieval charges can be higher |

Use S3 Standard for an image displayed on a website.

Use Glacier for the original image archive retained for compliance.

---

# 55. Lifecycle policies

An **S3 lifecycle policy** automatically moves or deletes objects based on age.

The diagram on page 50 gives this example:

```text
S3 Standard
↓ after 30 days
S3 Standard-IA
↓ after another period
S3 Glacier
↓ after 365 days
Delete
```

The exact rules are configured by the customer.

### Library analogy

A lifecycle policy behaves like a librarian following rules:

```text
New book → Main shelf
Not borrowed for months → Storage room
Not borrowed for years → Archive
Retention period expires → Dispose
```

No employee needs to manually inspect every object.

---

# 56. Why lifecycle policies matter

Lifecycle policies help:

* reduce storage cost;
* automate data retention;
* archive old files;
* remove expired objects;
* enforce data-management rules.

Example:

```text
Security-camera footage
0–30 days     → S3 Standard
31–365 days   → Lower-cost class
After 1 year  → Glacier
After 7 years → Delete
```

This creates a storage strategy rather than merely dumping everything permanently into the most expensive class.

---

# 57. Choosing among all four services

| Requirement                        | Best starting choice |
| ---------------------------------- | -------------------- |
| EC2 boot disk                      | EBS                  |
| Database volume                    | EBS                  |
| High-performance database disk     | Provisioned IOPS EBS |
| Photos and videos                  | S3                   |
| Static website assets              | S3                   |
| Backup objects                     | S3                   |
| Shared folder across EC2 instances | EFS                  |
| Linux home directories             | EFS                  |
| Long-term compliance archive       | S3 Glacier           |
| Rarely accessed archive            | S3 Glacier           |

---

# 58. The four-service decision story

Imagine a media-production company.

## Editing server

The editing software runs on EC2 and needs a fast disk.

```text
EC2 editing server
↓
EBS SSD volume
```

## Finished videos

Completed videos must be stored and distributed.

```text
Video objects
↓
Amazon S3
```

## Shared project directory

Several editing servers need the same files.

```text
EC2 A
EC2 B
EC2 C
  ↓
Amazon EFS
```

## Old footage

Projects older than three years are rarely accessed but must be retained.

```text
S3
↓ Lifecycle policy
S3 Glacier
```

This illustrates that the services complement each other. AWS exams often present them like competing answers, but real systems frequently use several together.

---

# 59. Storage case studies from the module

## Case 1: Billions of customer events

The company receives billions of analytics events through services such as Kinesis, Firehose and Lambda.

Best storage choice:

```text
Amazon S3
```

Why:

* massive scale;
* object storage;
* suitable for analytics datasets;
* integrates with streaming data ingestion;
* virtually unlimited capacity.

---

## Case 2: Collaboration platform with petabytes of shared data

Multiple EC2 instances process customer email and need shared access to files.

Best storage choice:

```text
Amazon EFS
```

Why:

* shared file storage;
* multiple EC2 instances can mount it;
* scales automatically;
* suitable for large shared file systems.

---

## Case 3: Data protection and compliance

The company stores large volumes of customer data for compliance and long-term retention.

Best storage choice:

```text
Amazon S3 Glacier
```

Why:

* low-cost archival;
* long-term retention;
* compliance controls;
* high durability.

---

# 60. Common exam traps

## Trap 1: “S3 is a file system.”

Incorrect.

S3 is object storage. It uses buckets, objects and keys rather than a traditional mounted file system.

---

## Trap 2: “EBS is object storage.”

Incorrect.

EBS provides block storage.

---

## Trap 3: “EFS is a block device.”

Incorrect.

EFS is a shared network file system.

---

## Trap 4: “Glacier is best for frequently accessed data.”

Incorrect.

Glacier is designed for archival data that is rarely accessed.

---

## Trap 5: “An EBS snapshot is the active disk.”

Incorrect.

A snapshot is a point-in-time backup used to create another EBS volume.

---

## Trap 6: “EBS data disappears when EC2 stops.”

Incorrect.

EBS storage persists independently from the EC2 instance.

---

## Trap 7: “Any EBS volume can attach across Availability Zones.”

Incorrect.

The EC2 instance and EBS volume must normally be in the same Availability Zone.

---

## Trap 8: “HDD is always better because it stores large amounts.”

Incorrect.

SSD is better for high IOPS and low-latency workloads. HDD is better for sequential throughput-oriented workloads.

---

## Trap 9: “Throughput and IOPS mean the same thing.”

Incorrect.

```text
IOPS       → Number of operations
Throughput → Amount of data transferred
```

---

## Trap 10: “S3 Standard-IA is the same as Glacier.”

Incorrect.

S3 Standard-IA offers rapid access to infrequently used data.

Glacier is archival and retrieval may take minutes or hours.

---

## Trap 11: “S3 automatically stores every bucket in every Region.”

Incorrect.

A bucket belongs to a selected Region. Data is redundantly stored within that Region unless replication is configured separately.

---

## Trap 12: “EFS is designed mainly for Windows.”

Incorrect based on the module.

EFS uses NFS and is compatible with Linux-based EC2 instances.

---

## Trap 13: “EFS requires the customer to predict its maximum size.”

Incorrect.

EFS grows and shrinks automatically as files are added and removed.

---

## Trap 14: “Glacier retrieval is always immediate.”

Incorrect.

Retrieval time depends on the chosen retrieval option.

---

## Trap 15: “The cheapest storage class is always the cheapest overall.”

Incorrect.

Retrieval fees, request costs, minimum storage periods and access patterns matter. Choosing archival storage for frequently accessed files can turn a clever saving into a billing experiment.

---

# 61. Exam keyword guide

When the question contains these words, think of the corresponding service.

| Question keyword               | Likely answer        |
| ------------------------------ | -------------------- |
| Boot volume                    | EBS                  |
| Block storage                  | EBS                  |
| Database disk                  | EBS                  |
| High IOPS                      | Provisioned IOPS EBS |
| Shared Linux files             | EFS                  |
| Multiple EC2 instances         | EFS                  |
| NFS                            | EFS                  |
| Object storage                 | S3                   |
| Bucket                         | S3                   |
| Static website                 | S3                   |
| Virtually unlimited            | S3                   |
| Archival                       | S3 Glacier           |
| Compliance retention           | S3 Glacier           |
| Rarely accessed and cheapest   | S3 Glacier           |
| Automatically move old objects | Lifecycle policy     |
| Point-in-time backup           | EBS snapshot         |

---

# 62. Subjective exam answer templates

## Explain Amazon EBS

> Amazon EBS is a block-storage service that provides persistent virtual storage volumes for Amazon EC2 instances. An EBS volume behaves similarly to a hard disk and can be used for boot volumes, databases and application storage. It exists independently from the EC2 instance, is replicated within its Availability Zone and can be backed up using snapshots.

## Explain Amazon S3

> Amazon S3 is a fully managed object-storage service that stores objects inside buckets. It provides virtually unlimited storage, high durability and access through URLs, APIs, the AWS CLI and SDKs. It is commonly used for backups, application assets, media hosting, static websites and big-data storage.

## Explain Amazon EFS

> Amazon EFS is a managed network file-storage service that enables multiple Linux-based EC2 instances to access the same files through NFS. It automatically scales as files are added or removed and is suitable for shared content, web serving, analytics, media processing and home directories.

## Explain Amazon S3 Glacier

> Amazon S3 Glacier is a low-cost archival storage service designed for data that is rarely accessed but must be retained for long periods. It provides high durability, encryption and compliance features, although retrieval may take from several minutes to several hours depending on the retrieval option.

---

# 63. Quick comparison answer

> Amazon EBS provides persistent block storage for EC2 and is suitable for boot volumes and databases. Amazon S3 provides scalable object storage for files such as images, backups and application assets. Amazon EFS provides shared file storage that can be mounted by multiple Linux EC2 instances. Amazon S3 Glacier provides low-cost archival storage for rarely accessed, long-term data.

---

# 64. Memory sheet

```text
AMAZON EBS

- Block storage
- Used with EC2
- Similar to a hard drive
- Persistent after instance stops
- Availability Zone-based
- Supports SSD and HDD
- Backed up using snapshots
```

```text
EBS VOLUME TYPES

General Purpose SSD
- Most workloads
- Boot volumes

Provisioned IOPS SSD
- High-performance databases
- Sustained IOPS

Throughput-Optimised HDD
- Big data
- Logs
- Data warehouses

Cold HDD
- Rarely accessed
- Lowest HDD cost
```

```text
AMAZON S3

- Object storage
- Objects stored in buckets
- Virtually unlimited storage
- Up to 5 TB per object in module
- Designed for 11 nines durability
- Accessed through URLs, APIs, CLI and SDKs
```

```text
AMAZON EFS

- Shared file storage
- Uses NFS
- Multiple Linux EC2 instances
- Mount targets in VPC subnets
- Automatically scales
- Pay for used capacity
```

```text
AMAZON S3 GLACIER

- Long-term archive
- Rarely accessed data
- Extremely low storage cost
- Retrieval takes minutes or hours
- Supports compliance and encryption
- Can receive objects through lifecycle policies
```

```text
STORAGE SELECTION

Need a disk?             → EBS
Need to store objects?   → S3
Need a shared folder?    → EFS
Need a long-term archive? → Glacier
```

# Module 7 in one paragraph

AWS provides different storage services based on how data must be accessed. Amazon EBS offers persistent block storage for EC2 instances and supports SSD and HDD volume types, encryption, elasticity and point-in-time snapshots. Amazon S3 stores objects in buckets and provides virtually unlimited, highly durable storage for backups, media, application assets and analytics data. Amazon EFS provides automatically scaling shared file storage that multiple Linux EC2 instances can access through NFS and mount targets. Amazon S3 Glacier provides secure, durable and low-cost archival storage for rarely accessed data, while S3 lifecycle policies can automatically move older objects into cheaper storage classes or delete them after a retention period.


---

</details>

<details>
<summary><strong>Module 8: Databases — Intuitive and Narrative Explanation</strong></summary>

# Module 8: Databases — Intuitive and Narrative Explanation

This module is really about one question:

> **What kind of database should an application use, based on how the data will be stored, accessed and analysed?**

AWS does not provide only one database service because databases perform very different jobs.

An online store might need:

| Requirement                                                     | Suitable AWS service |
| --------------------------------------------------------------- | -------------------- |
| Store customers, orders and payments with clear relationships   | Amazon RDS           |
| Store millions of shopping-cart or session records very quickly | Amazon DynamoDB      |
| Analyse several years of sales data                             | Amazon Redshift      |
| Run a high-performance enterprise relational database           | Amazon Aurora        |

The trick is not memorising four service names. It is recognising the **type of workload** behind the scenario. 

---

# 1. The module as one company story

Imagine that a company operates an online shopping platform called **CloudCart**.

CloudCart has four database problems.

## Problem 1: Transactions

Customers place orders, make payments and receive invoices.

These records have clear relationships:

```text
Customer
   ↓ places
Order
   ↓ contains
Order Items
   ↓ refers to
Product
```

This needs a **relational database**.

CloudCart could use:

```text
Amazon RDS
or
Amazon Aurora
```

## Problem 2: Shopping carts and user sessions

Millions of users browse products. Their carts change constantly, and the application must respond within milliseconds.

The data does not require complicated joins. It mainly needs fast operations such as:

```text
GET cart for User123
PUT new item into User123's cart
```

This suits:

```text
Amazon DynamoDB
```

## Problem 3: Business analysis

Management wants to analyse:

* five years of sales;
* best-selling products;
* customer trends;
* sales by country;
* seasonal performance.

These queries may scan billions of records.

That suits:

```text
Amazon Redshift
```

## Problem 4: Enterprise relational performance

CloudCart wants a relational database compatible with MySQL but with stronger cloud-native performance, availability and scalability.

That suits:

```text
Amazon Aurora
```

This is the whole module in miniature.

---

# 2. Database versus storage

Before going further, separate a **database** from ordinary storage.

Amazon S3, EBS and EFS store data, but they do not automatically organise it into customers, transactions, relationships and queries.

A database adds structure and control.

For example:

```text
Storage:
customer_data.csv

Database:
Find all customers who:
- purchased in July
- spent more than RM1,000
- live in Malaysia
```

Storage keeps data.

A database helps applications **organise, retrieve, modify and analyse** that data.

---

# 3. Relational databases

A relational database stores data in tables made of rows and columns.

Example:

## Customers table

| CustomerID | Name     | Country   |
| ---------- | -------- | --------- |
| C001       | Amir     | Malaysia  |
| C002       | Mei Ling | Singapore |

## Orders table

| OrderID | CustomerID | Amount |
| ------- | ---------- | -----: |
| O101    | C001       |  RM250 |
| O102    | C001       |  RM400 |

The `CustomerID` connects the two tables.

```text
Customers.CustomerID
        ↓
Orders.CustomerID
```

This creates a relationship between customers and their orders.

Relational databases are useful when:

* the data has a clear structure;
* relationships matter;
* transactions must remain accurate;
* complex queries and joins are required;
* SQL is used.

---

# 4. Non-relational databases

A non-relational database, often called **NoSQL**, does not require every record to follow the same rigid table structure.

One item might look like:

```json
{
  "UserID": "U001",
  "Name": "Aiman",
  "Country": "Malaysia"
}
```

Another item in the same collection might contain:

```json
{
  "UserID": "U002",
  "Name": "Sarah",
  "PreferredLanguage": "English",
  "Subscription": "Premium"
}
```

The second item has attributes that the first one does not.

That flexibility is useful when the data changes frequently or when enormous scale matters more than complicated relationships.

The comparison shown on page 25 summarises the main difference:

| Relational                      | Non-relational                          |
| ------------------------------- | --------------------------------------- |
| Rows and columns                | Key-value, document or graph structures |
| Usually fixed schema            | Flexible or dynamic schema              |
| Uses SQL                        | Usually accessed through keys and APIs  |
| Traditionally scales vertically | Designed to scale horizontally          |

Do not reduce this to “SQL good, NoSQL modern.” That is the sort of slogan people use shortly before choosing the wrong database.

---

# Section 1: Amazon RDS

# 5. What is Amazon RDS?

**Amazon Relational Database Service**, or **Amazon RDS**, is a managed service for setting up, operating and scaling relational databases in AWS.

RDS supports database engines such as:

* MySQL;
* PostgreSQL;
* MariaDB;
* Oracle;
* Microsoft SQL Server;
* Amazon Aurora.

The customer chooses the engine, instance size and storage. AWS handles much of the underlying administration.

```text
Application
    ↓
Amazon RDS
    ↓
Relational database
```

---

# 6. Managed versus unmanaged databases

Suppose CloudCart installs MySQL directly on an EC2 instance.

The company must manage:

* the operating system;
* database installation;
* database patches;
* backups;
* availability;
* storage;
* server failures;
* scaling.

This is essentially an **unmanaged database approach**.

With Amazon RDS, AWS manages much of that work.

The comparison on pages 6–10 shows the shift in responsibility:

| Database on EC2                          | Amazon RDS                      |
| ---------------------------------------- | ------------------------------- |
| Customer manages the OS                  | AWS manages the OS              |
| Customer installs database software      | AWS handles installation        |
| Customer applies patches                 | AWS manages patching            |
| Customer designs backups                 | Automated backups are available |
| Customer builds failover                 | Multi-AZ can provide failover   |
| Customer handles physical infrastructure | AWS handles infrastructure      |

The customer still manages:

* database design;
* users and permissions;
* application queries;
* indexes;
* performance optimisation;
* the data itself.

AWS manages the service, not the customer's bad SQL query that joins twelve tables for no apparent reason.

---

# 7. Why relational databases are difficult to manage

Page 7 identifies several traditional database challenges:

* server maintenance;
* operating system installation and patching;
* database software installation and patching;
* backups;
* high availability;
* scalability;
* data security;
* power and physical infrastructure.

RDS reduces this operational burden.

The main idea is:

> **RDS allows the organisation to focus more on using the database and less on maintaining the server underneath it.**

---

# 8. RDS DB instance

An RDS database runs on a **DB instance**.

A DB instance combines three major choices.

## Database engine

Examples:

```text
MySQL
PostgreSQL
MariaDB
Oracle
Microsoft SQL Server
Amazon Aurora
```

## DB instance class

This determines resources such as:

* CPU;
* memory;
* network performance.

## Storage

The module lists:

* magnetic storage;
* General Purpose SSD;
* Provisioned IOPS SSD.

So an RDS instance can be understood as:

```text
DB engine
+
Compute and memory
+
Database storage
=
RDS DB instance
```

---

# 9. RDS inside a VPC

An RDS database usually runs inside a Virtual Private Cloud.

The architecture diagram on page 12 places:

* the EC2 application server in a public subnet;
* the RDS database in a private subnet.

```text
Internet users
      ↓
Public EC2 application
      ↓
Private RDS database
```

This design is sensible because users normally should not connect directly to the database.

Instead:

1. the user connects to the application;
2. the application validates the request;
3. the application communicates with RDS.

The database remains protected inside a private network.

Putting a production database directly on the internet merely saves attackers the inconvenience of looking for it.

---

# 10. RDS security idea

A typical secure architecture uses security groups so that:

```text
Internet
   ↓ allowed
Application server
   ↓ allowed on database port
RDS database
```

The database security group permits connections from the application server, not from every address on the internet.

For example:

```text
Web traffic: Internet → EC2
Database traffic: EC2 → RDS
Direct database traffic: Internet ✕
```

---

# 11. RDS Multi-AZ deployment

A **Multi-AZ deployment** improves availability.

The diagrams on pages 13–14 show:

```text
Availability Zone 1
Primary RDS instance
        ↓ synchronous replication
Availability Zone 2
Standby RDS instance
```

The primary database handles the application's traffic.

The standby database receives synchronised copies of the data.

If the primary instance or Availability Zone fails, AWS can fail over to the standby.

---

# 12. Synchronous replication

Multi-AZ uses **synchronous replication** in the module.

This means a database change is copied to the standby as part of the write process.

Conceptually:

```text
Application writes order
        ↓
Primary database records order
        ↓
Standby database also receives order
        ↓
Write is confirmed
```

This reduces the chance that a recent transaction is lost during failover.

---

# 13. What Multi-AZ is for

Multi-AZ is primarily for:

```text
High availability
Fault tolerance
Automatic failover
```

It is not mainly intended to improve read performance.

The standby normally exists to take over if the primary fails.

This distinction is extremely important:

```text
Multi-AZ → Availability
Read replica → Read scalability
```

AWS exams enjoy testing this because apparently one backup-looking database is not confusing enough.

---

# 14. RDS read replicas

A **read replica** is a copy of a database used to handle read queries.

The diagram on page 15 shows:

```text
Primary RDS instance
        ↓ asynchronous replication
Read replica
```

The application sends:

* write operations to the primary;
* some read operations to the replica.

Example:

```text
Create new order → Primary
Update payment   → Primary
View product list → Read replica
Generate report   → Read replica
```

This reduces the read workload on the primary database.

---

# 15. Asynchronous replication

Read replicas use **asynchronous replication** in the module.

That means the primary can finish a write before the change has fully reached the replica.

```text
Primary receives update
        ↓
Primary confirms update
        ↓
Replica catches up shortly afterward
```

Therefore, the replica might briefly contain slightly older data.

This delay is known as **replication lag**.

---

# 16. Read replicas versus Multi-AZ

| Multi-AZ standby                               | Read replica                         |
| ---------------------------------------------- | ------------------------------------ |
| Designed for high availability                 | Designed for read performance        |
| Synchronous replication                        | Asynchronous replication             |
| Automatic failover                             | Usually accessed separately          |
| Standby normally does not serve ordinary reads | Replica serves read queries          |
| Protects against failure                       | Reduces read load                    |
| Secondary can replace failed primary           | Replica can be promoted if necessary |

Memory trick:

```text
Multi-AZ keeps the database alive.
Read replicas make reading lighter.
```

---

# 17. Example: ecommerce database

CloudCart's database receives:

* 1,000 order writes per minute;
* 50,000 product-page reads per minute.

The writes must go to the primary.

However, product catalogue queries can be sent to read replicas.

```text
Checkout and payments
        ↓
Primary RDS instance

Product browsing and reports
        ↓
Read replicas
```

If the requirement instead says:

> “The database must continue operating when an Availability Zone fails.”

The answer is Multi-AZ, not merely a read replica.

---

# 18. When to use RDS

According to page 17, RDS is suitable when an application requires:

* complex transactions;
* complex SQL queries;
* relational data;
* high durability;
* moderate-to-high query and write rates;
* structured data with relationships.

Examples:

* banking transactions;
* order management;
* inventory systems;
* accounting systems;
* customer relationship management;
* ecommerce checkouts.

A strong clue is the word **transaction**.

For example:

```text
Deduct inventory
Create order
Record payment
Generate invoice
```

These actions must remain consistent. A relational database is usually appropriate.

---

# 19. When RDS may not be suitable

The module suggests avoiding RDS when the workload needs:

* extremely massive read or write rates;
* horizontal sharding at enormous scale;
* simple GET and PUT access;
* flexible NoSQL data;
* deep operating-system or database-engine customisation.

In those cases:

```text
Massive simple key-based workload → DynamoDB
Full OS control required → Database on EC2
Analytics over huge historical data → Redshift
```

---

# 20. RDS pricing factors

The module describes several RDS cost components.

## Running time

RDS instances incur charges while running.

## Database characteristics

Cost depends on:

* database engine;
* DB instance class;
* memory and compute capacity;
* storage type and size.

## Purchase option

The module describes:

* On-Demand DB instances;
* Reserved DB instances with one-year or three-year terms.

## Number of instances

A primary, standby and several read replicas are separate database resources.

## Storage and backup

Charges may include:

* provisioned database storage;
* additional backup storage;
* backups retained after the database is terminated.

## I/O requests

Some configurations charge based on database input/output operations.

## Deployment

Multi-AZ generally costs more than Single-AZ because additional infrastructure exists.

## Data transfer

Inbound transfer is described as free in the module, while outbound transfer may be charged.

The sensible exam statement is:

> Amazon RDS cost depends on the instance class, database engine, storage, deployment type, running duration, backups, I/O and data transfer.

---

# Section 2: Amazon DynamoDB

# 21. What is Amazon DynamoDB?

**Amazon DynamoDB** is a fully managed NoSQL database service designed for fast and predictable performance at very large scale.

It supports:

* key-value data;
* document data;
* flexible attributes;
* low-latency queries;
* scalable read and write throughput;
* virtually unlimited storage in the context of the module.

```text
Application
    ↓ key
DynamoDB table
    ↓
Matching item
```

DynamoDB is useful when an application usually knows exactly which item it wants.

---

# 22. Library analogy

Imagine a library where every book has a unique identification number.

If the librarian knows the number:

```text
Book ID: B1029
        ↓
Find exact shelf
        ↓
Retrieve book quickly
```

That resembles a DynamoDB query using a key.

If the librarian is told:

> “Find every book containing a blue car somewhere in the story.”

The librarian might need to inspect a huge part of the collection.

That resembles a scan.

DynamoDB is extremely fast when the table and keys are designed properly. It is less impressed when an application ignores the keys and scans everything.

---

# 23. DynamoDB core components

DynamoDB has three main components:

```text
Table
Item
Attribute
```

## Table

A table is a collection of related data.

Example:

```text
Users table
```

## Item

An item is one record inside the table.

Example:

```text
One user
```

## Attribute

An attribute is one piece of information about the item.

Example:

```text
UserID
Name
Country
Subscription
```

Relational comparison:

| Relational database | DynamoDB  |
| ------------------- | --------- |
| Table               | Table     |
| Row                 | Item      |
| Column              | Attribute |

The names are different, but the analogy helps.

---

# 24. Flexible attributes

In DynamoDB, items in the same table can contain different attributes.

Example:

```json
{
  "UserID": "U001",
  "Name": "Ali",
  "Country": "Malaysia"
}
```

Another item:

```json
{
  "UserID": "U002",
  "Name": "Hannah",
  "Country": "Singapore",
  "Subscription": "Premium",
  "PreferredDevice": "Mobile"
}
```

Both items can exist in the same table.

This is useful when the data structure changes or varies between records.

---

# 25. Primary keys

Every DynamoDB item must have a key.

The diagram on page 29 shows two designs.

## Simple primary key

A simple primary key contains only a **partition key**.

Example:

```text
UserID = U001
```

Each partition-key value must uniquely identify one item.

## Composite primary key

A composite primary key contains:

```text
Partition key
+
Sort key
```

Example:

```text
UserID = U001
Timestamp = 2026-07-22T10:00
```

Several items can share the same partition key as long as their sort keys differ.

---

# 26. Partition-key example

Suppose CloudCart stores orders.

```text
Partition key: CustomerID
Sort key: OrderDate
```

The table might contain:

| CustomerID | OrderDate  | Amount |
| ---------- | ---------- | -----: |
| C001       | 2026-07-01 |  RM200 |
| C001       | 2026-07-15 |  RM450 |
| C002       | 2026-07-20 |  RM100 |

The complete key for the first item is:

```text
C001 + 2026-07-01
```

The same customer can therefore have many orders.

The sort key also allows the orders to be organised and queried by date.

---

# 27. What partitioning means

As a DynamoDB table grows, AWS divides the data into **partitions**.

The partition key helps determine where an item is stored.

Conceptually:

```text
Partition key
      ↓
Hash calculation
      ↓
Select storage partition
```

This allows DynamoDB to spread data and workload across multiple resources.

That is how horizontal scaling works.

Instead of endlessly upgrading one gigantic machine, the data is distributed across many partitions.

---

# 28. Good partition keys

A useful partition key distributes requests across many different values.

Good example:

```text
UserID
OrderID
DeviceID
```

Potentially poor example:

```text
Country
```

Suppose 90% of users are from Malaysia. Most traffic might be directed toward one partition-key value.

This creates a **hot partition**.

The key should ideally have:

* many possible values;
* balanced access;
* no single value receiving most requests.

DynamoDB scales impressively, but it cannot repeal the consequences of a terrible key design.

---

# 29. Query versus scan

The partitioning diagram on page 28 distinguishes between **Query** and **Scan**.

## Query

A Query uses a key to locate items efficiently.

Example:

```text
Find all orders where CustomerID = C001
```

DynamoDB knows which partition to inspect.

## Scan

A Scan checks every item or a large part of the table.

Example:

```text
Find all customers whose favourite colour is blue
```

If `FavouriteColour` is not part of an appropriate key or index, DynamoDB may need to scan the table.

| Query           | Scan                               |
| --------------- | ---------------------------------- |
| Uses keys       | Checks many or all items           |
| Efficient       | Less efficient                     |
| Usually cheaper | Can consume more capacity          |
| Preferred       | Avoid for frequent large workloads |

Exam rule:

> Use Query when the key is known. Scan is broader and usually less efficient.

---

# 30. DynamoDB latency

The module describes DynamoDB as providing consistent, single-digit millisecond latency at any scale.

The practical meaning is that a well-designed key-based request can remain fast even when the table becomes extremely large.

Typical operations include:

```text
Get item
Put item
Update item
Delete item
Query items by key
```

This makes DynamoDB suitable for applications where users expect immediate responses.

---

# 31. DynamoDB use cases

The module identifies use cases such as:

* mobile applications;
* web applications;
* gaming;
* advertising technology;
* Internet of Things;
* applications with unpredictable traffic.

Examples include:

```text
User sessions
Shopping carts
Game player states
Device telemetry
Product lookups
User preferences
Leaderboards
```

These workloads often require:

* simple access patterns;
* low latency;
* rapid scaling;
* flexible schemas.

---

# 32. Example: online game

An online game stores:

```json
{
  "PlayerID": "P001",
  "Level": 47,
  "Score": 92300,
  "CurrentMap": "Volcano"
}
```

The game repeatedly performs:

```text
GET PlayerID P001
UPDATE PlayerID P001 score
```

This is exactly the kind of key-based workload DynamoDB handles well.

A relational database could store it, but complicated relational features may be unnecessary.

---

# 33. DynamoDB replication

The module states that DynamoDB can replicate tables across selected AWS Regions.

This relates to **global tables**.

Conceptually:

```text
DynamoDB table in Region A
          ↕
DynamoDB table in Region B
```

This supports applications with users in several geographical regions and provides resilience across Regions when configured.

It should not be interpreted as every DynamoDB table being copied to every Region by default. AWS tends not to create global infrastructure merely because someone clicked “Create table.”

---

# 34. DynamoDB versus RDS

| Amazon RDS                                     | Amazon DynamoDB                               |
| ---------------------------------------------- | --------------------------------------------- |
| Relational                                     | Non-relational                                |
| Rows and columns                               | Items and attributes                          |
| Fixed or strongly defined schema               | Flexible schema                               |
| SQL and joins                                  | Key-based API operations                      |
| Complex transactions and queries               | Fast simple access patterns                   |
| Mostly vertical instance scaling plus replicas | Horizontal partitioning                       |
| Best for related structured data               | Best for massive key-value/document workloads |

Use RDS when:

```text
Customer → Order → Product → Payment
```

and relationships matter.

Use DynamoDB when:

```text
Key → Item
```

and speed and scale matter most.

---

# Section 3: Amazon Redshift

# 35. What is Amazon Redshift?

**Amazon Redshift** is a fully managed cloud data warehouse.

It is designed for analysing large amounts of data using SQL.

```text
Operational systems
    ↓
Data collected
    ↓
Amazon Redshift
    ↓
Analysts and BI dashboards
```

Redshift is not mainly intended to process one customer's checkout transaction.

It is designed to answer questions such as:

* What were total sales by Region over five years?
* Which products are growing fastest?
* What customer segments are most profitable?
* How did marketing affect sales?

---

# 36. Operational database versus data warehouse

An operational database handles daily business activity.

Example:

```text
Create one order
Update one customer's address
Record one payment
```

A data warehouse handles large analytical questions.

Example:

```text
Analyse 500 million orders
Group by country
Compare by month
Calculate five-year trends
```

| Operational database         | Data warehouse                 |
| ---------------------------- | ------------------------------ |
| Many short transactions      | Fewer large analytical queries |
| Current application data     | Historical combined data       |
| Insert and update frequently | Mostly read and analyse        |
| RDS or DynamoDB              | Redshift                       |

Using Redshift as an ordinary checkout database would be like using a stadium to conduct a private tutoring session. Technically, people can sit there. The architecture remains ridiculous.

---

# 37. Redshift architecture

The architecture on page 36 shows:

```text
SQL clients and BI tools
          ↓
Leader node
          ↓
Multiple compute nodes
```

Redshift can also work with data from sources such as:

* Amazon S3;
* Amazon DynamoDB;
* other databases and data systems.

---

# 38. Leader node

The **leader node** receives SQL queries from clients.

It then:

1. analyses the query;
2. creates an execution plan;
3. distributes work to compute nodes;
4. combines the results;
5. returns the final answer.

Conceptually:

```text
Analyst asks one large question
          ↓
Leader divides it into smaller tasks
          ↓
Compute nodes work in parallel
          ↓
Leader combines the answers
```

---

# 39. Compute nodes

Compute nodes store and process portions of the data.

Instead of one machine processing an enormous table alone:

```text
One machine
↓
Process all data sequentially
```

Redshift can divide the work:

```text
Node 1 → Part A
Node 2 → Part B
Node 3 → Part C
Node 4 → Part D
```

The nodes work at the same time.

This is called **massively parallel processing**, or MPP.

---

# 40. Parallel-processing analogy

Imagine counting all the books in a large library.

## Sequential processing

One person counts every shelf.

## Parallel processing

Ten people each count a separate section.

The results are added together.

Redshift follows the second approach.

This is why it performs well for large analytical workloads.

---

# 41. Columnar storage

Traditional transactional databases often store data by row.

Example:

```text
Order1: Date, Customer, Product, Quantity, Price
Order2: Date, Customer, Product, Quantity, Price
```

Redshift uses **columnar storage**, which stores values from the same column together.

Conceptually:

```text
Dates:      Date1, Date2, Date3...
Customers:  C001, C002, C003...
Prices:     50, 70, 100...
```

Suppose an analyst only wants:

```sql
SELECT SUM(Price)
FROM Sales;
```

Redshift mainly needs the `Price` column.

It does not need to read every customer name, address and product description.

This reduces the amount of data processed.

---

# 42. Why columnar storage helps analytics

Analytical queries often use a small number of columns from a very large number of rows.

Example:

```text
Calculate average sale value
for every month
over five years
```

The query might only need:

```text
Date
SaleAmount
```

Columnar storage allows Redshift to focus on those columns.

It also improves compression because similar values are stored together.

---

# 43. Redshift compatibility

Page 38 shows Redshift connecting to:

* SQL clients;
* business-intelligence tools.

This allows tools to create:

* dashboards;
* reports;
* visualisations;
* analytical models.

Examples of users include:

```text
Business analysts
Data analysts
Management
Reporting systems
BI applications
```

The users submit SQL queries without needing to understand how every compute node processes the query.

---

# 44. Redshift use cases

The module lists several major use cases.

## Enterprise data warehouse

Organisations can migrate existing analytical workloads without purchasing large physical data-warehouse systems.

## Big-data analytics

Redshift can analyse large historical datasets.

## Software as a Service

A SaaS provider can include analytical features for customers.

## Business intelligence

Redshift can support dashboards and reports.

## Cost reduction

The organisation avoids purchasing and maintaining dedicated data-warehouse hardware.

---

# 45. Redshift features

The section summary on page 41 identifies:

* fully managed data warehousing;
* scalability;
* columnar storage;
* parallel processing;
* continuous monitoring;
* built-in encryption.

The essential exam phrase is:

> Amazon Redshift is a fully managed data warehouse that uses columnar storage and massively parallel processing for large-scale analytics.

---

# 46. Redshift versus RDS

| Amazon RDS                             | Amazon Redshift                           |
| -------------------------------------- | ----------------------------------------- |
| Operational relational database        | Analytical data warehouse                 |
| Handles daily transactions             | Handles large analytical queries          |
| Frequently inserts and updates records | Mainly reads and aggregates data          |
| Good for individual orders             | Good for trends across millions of orders |
| Row-oriented relational workloads      | Columnar analytical workloads             |

Scenario:

> “Record one customer's payment.”

Use RDS or Aurora.

Scenario:

> “Analyse payments from all customers over ten years.”

Use Redshift.

---

# Section 4: Amazon Aurora

# 47. What is Amazon Aurora?

**Amazon Aurora** is an enterprise-class relational database engine developed by AWS.

It is compatible with:

* MySQL;
* PostgreSQL.

Aurora is managed through Amazon RDS.

This relationship is important:

```text
Amazon RDS
    ├── MySQL
    ├── PostgreSQL
    ├── MariaDB
    ├── Oracle
    ├── SQL Server
    └── Amazon Aurora
```

Aurora is not an unrelated alternative floating outside RDS. It is one of the database engines available through the RDS managed-service environment.

---

# 48. Why Aurora exists

Traditional MySQL and PostgreSQL are widely used, but organisations may want:

* higher performance;
* automatic scaling;
* high availability;
* cloud-native storage;
* automatic recovery;
* easier management.

Aurora keeps compatibility with familiar MySQL or PostgreSQL applications while redesigning the underlying database for AWS infrastructure.

---

# 49. Aurora compatibility

Because Aurora is compatible with MySQL or PostgreSQL, many existing tools and applications can connect using familiar:

* SQL syntax;
* drivers;
* libraries;
* administration tools.

This makes migration easier than rewriting the entire application for a completely different database model.

Compatibility does not mean Aurora is internally identical to ordinary MySQL. It means the application-facing behaviour is designed to work with the chosen compatible engine.

---

# 50. Managed Aurora tasks

Page 43 lists tasks Aurora automates:

* provisioning;
* patching;
* backup;
* recovery;
* failure detection;
* repair.

This means the customer focuses mainly on:

* schema design;
* queries;
* users;
* application logic;
* performance strategy.

AWS handles much of the infrastructure and database maintenance.

---

# 51. Aurora availability architecture

The diagram on page 45 shows Aurora storage distributed across three Availability Zones.

It illustrates:

```text
Availability Zone 1 → Two copies
Availability Zone 2 → Two copies
Availability Zone 3 → Two copies
```

This gives six storage copies across three Availability Zones in the architecture shown.

It also shows backups associated with Amazon S3.

The design reduces dependence on one disk, server or Availability Zone.

---

# 52. Aurora high-availability story

Suppose one storage copy fails.

Aurora still has other copies.

Suppose an Availability Zone becomes unavailable.

Copies remain in the other Availability Zones.

Conceptually:

```text
One copy fails
↓
Other copies continue serving data
↓
Aurora repairs or replaces the damaged copy
```

This supports high availability and durability.

---

# 53. Redo logs and recovery

The resilient-design diagram on page 46 shows **redo log files** helping restore a database.

A redo log records database changes.

Example:

```text
Create Order O101
Update inventory from 12 to 11
Record payment RM250
```

If a failure occurs, the database can use the log to reconstruct recent changes.

Instead of copying an entire database repeatedly for every small change, the system can preserve and replay the sequence of updates.

---

# 54. Aurora benefits

The module summarises Aurora as:

* high performance;
* scalable;
* highly available;
* durable;
* secure;
* MySQL-compatible;
* PostgreSQL-compatible;
* fully managed;
* pay-as-you-go.

Use Aurora when the requirement is:

> “A high-performance enterprise relational database compatible with MySQL or PostgreSQL.”

---

# 55. Aurora versus ordinary RDS engines

| Standard RDS engine                      | Amazon Aurora                                          |
| ---------------------------------------- | ------------------------------------------------------ |
| Runs engines such as MySQL or PostgreSQL | AWS-designed relational engine                         |
| Traditional engine architecture          | Cloud-native distributed storage                       |
| Managed by RDS                           | Also managed through RDS                               |
| Good general relational workloads        | Stronger enterprise performance and availability focus |
| Supports several engine choices          | Only MySQL- or PostgreSQL-compatible editions          |

RDS is the broader managed service.

Aurora is a specialised relational engine within it.

---

# 56. Aurora versus DynamoDB

| Aurora                               | DynamoDB                              |
| ------------------------------------ | ------------------------------------- |
| Relational                           | NoSQL                                 |
| Uses SQL                             | Key-value/document access             |
| Structured schemas and relationships | Flexible attributes                   |
| Supports joins and transactions      | Designed for simple high-scale access |
| MySQL/PostgreSQL compatibility       | AWS-native API model                  |

Use Aurora for:

```text
Customers, orders, invoices and payments
```

Use DynamoDB for:

```text
Sessions, carts, game state and device data
```

---

# 57. Choosing the right database

The table on page 48 presents the central decision.

| Requirement                                                      | Suitable service                   |
| ---------------------------------------------------------------- | ---------------------------------- |
| Managed enterprise relational database                           | Amazon RDS                         |
| High-performance MySQL/PostgreSQL-compatible relational database | Amazon Aurora                      |
| Fast and flexible NoSQL at large scale                           | Amazon DynamoDB                    |
| Large-scale analytical data warehouse                            | Amazon Redshift                    |
| Full operating-system or database customisation                  | Database on Amazon EC2             |
| Specialised database requirement                                 | AWS purpose-built database service |

---

# 58. Database on EC2

Sometimes an organisation needs full control over:

* the operating system;
* database software;
* extensions;
* configuration;
* patch timing;
* unsupported features.

In that case, it can install a database directly on EC2.

```text
EC2 instance
    ↓
Customer installs database
    ↓
Customer manages everything
```

This gives control but increases responsibility.

| Database on EC2                    | Amazon RDS                       |
| ---------------------------------- | -------------------------------- |
| Full OS access                     | No normal OS access              |
| Full customisation                 | Managed configuration            |
| Customer patches everything        | AWS manages much of the patching |
| Customer manages backups           | Automated backup features        |
| Customer designs high availability | Multi-AZ options available       |
| More control                       | Less operational work            |

Control is useful when genuinely required. It is not automatically a virtue. Manually patching database servers at 3 a.m. is not a personality trait worth cultivating.

---

# 59. The four-service decision tree

Ask the following questions.

## Is the workload analytical?

```text
Yes → Amazon Redshift
```

Example:

> Analyse ten years of customer purchases.

## Does the application require relationships, SQL and transactions?

```text
Yes → Amazon RDS or Aurora
```

Example:

> Store payments, invoices and orders.

## Does it specifically require high-performance MySQL or PostgreSQL compatibility?

```text
Yes → Amazon Aurora
```

## Does it mainly use keys, simple GET/PUT operations and huge scale?

```text
Yes → Amazon DynamoDB
```

## Does it require operating-system access or unsupported database features?

```text
Yes → Database on EC2
```

---

# 60. Complete comparison

| Feature        | RDS                      | DynamoDB                          | Redshift                    | Aurora                              |
| -------------- | ------------------------ | --------------------------------- | --------------------------- | ----------------------------------- |
| Database model | Relational               | NoSQL                             | Relational analytics        | Relational                          |
| Main purpose   | Application transactions | Fast key-value/document workloads | Data warehousing            | Enterprise relational workloads     |
| Query style    | SQL                      | Key-based APIs                    | Complex analytical SQL      | SQL                                 |
| Schema         | Structured               | Flexible                          | Structured analytical model | Structured                          |
| Scaling focus  | Instance and replicas    | Horizontal partitioning           | Cluster processing          | Cloud-native relational scaling     |
| Typical data   | Orders and payments      | Sessions and carts                | Historical business data    | High-performance transactional data |
| Main keyword   | Managed relational       | NoSQL                             | Data warehouse              | MySQL/PostgreSQL compatible         |

---

# 61. Case study 1: data protection company

The company needs:

1. a relational database for configuration data;
2. a non-relational store for unstructured metadata;
3. S3 for accessible stored data;
4. Glacier for long-term archive.

Best starting choices:

```text
Configuration data → Amazon RDS or Aurora
Unstructured metadata → Amazon DynamoDB
Processed objects → Amazon S3
Long-term archive → Amazon S3 Glacier
```

Why?

Configuration data normally has clear relationships and structure.

Metadata used for high-scale deduplication may be accessed through simple keys and may not share a fixed schema.

---

# 62. Case study 2: shipping company

The company:

* currently uses Oracle;
* is moving toward serverless applications;
* is decomposing relational data into semistructured data;
* uses Lambda and AppSync.

A suitable future database for the semistructured serverless workload is:

```text
Amazon DynamoDB
```

The existing Oracle system can continue operating during migration, while newly decomposed services store flexible data in DynamoDB.

This is a common modernisation pattern:

```text
Large relational legacy system
        ↓ gradually decomposed
Smaller serverless services
        ↓
DynamoDB tables
```

---

# 63. Case study 3: payment-processing company

The company processes over one million transactions daily and experiences sudden traffic spikes during flash sales.

The data remains transactional and relational, but it needs high throughput and read scaling.

A strong fit is:

```text
Amazon Aurora
with read replicas
```

Why?

* payments require relational integrity;
* Aurora supports enterprise relational workloads;
* read replicas can offload read traffic;
* AWS-managed scaling and availability reduce operational burden.

DynamoDB may handle extremely high throughput, but the presence of complex financial transactions and read replicas points toward a relational RDS-family design in the module's context.

---

# 64. Common exam traps

## Trap 1: Multi-AZ improves read performance

Not primarily.

```text
Multi-AZ → High availability
Read replica → Read scaling
```

---

## Trap 2: A read replica is always fully current

Not necessarily.

Read replicas use asynchronous replication, so temporary replication lag may occur.

---

## Trap 3: The Multi-AZ standby normally handles application reads

No.

Its main job is failover and availability.

---

## Trap 4: DynamoDB is relational

No.

DynamoDB is a NoSQL key-value and document database.

---

## Trap 5: DynamoDB items must all have identical attributes

No.

Items can contain different attributes, although every item must satisfy the table's key requirements.

---

## Trap 6: Scan is more efficient than Query

Usually the opposite.

A Query uses keys.

A Scan examines many or all items.

---

## Trap 7: Redshift is designed for everyday checkout transactions

No.

Redshift is a data warehouse for analytics.

---

## Trap 8: RDS and Aurora are completely separate categories

Not quite.

RDS is the managed relational database service. Aurora is one of the relational engines available through RDS.

---

## Trap 9: Aurora supports every RDS engine

No.

Aurora is compatible with MySQL and PostgreSQL.

---

## Trap 10: Managed means the customer has no responsibilities

No.

The customer still manages:

* the data;
* schema;
* queries;
* users;
* access permissions;
* application optimisation.

---

## Trap 11: DynamoDB automatically makes every data model fast

No.

A poor partition key or excessive Scan operations can still produce inefficient performance.

---

## Trap 12: Redshift and RDS are interchangeable because both use SQL

No.

```text
RDS → Transactions
Redshift → Analytics
```

SQL is a language, not a guarantee that two services perform the same job.

---

# 65. Exam keyword guide

| Keyword in question                                | Likely answer    |
| -------------------------------------------------- | ---------------- |
| Managed relational database                        | Amazon RDS       |
| MySQL or PostgreSQL compatible enterprise database | Amazon Aurora    |
| NoSQL                                              | Amazon DynamoDB  |
| Key-value                                          | Amazon DynamoDB  |
| Document database                                  | Amazon DynamoDB  |
| Single-digit millisecond latency                   | Amazon DynamoDB  |
| Flexible schema                                    | Amazon DynamoDB  |
| Data warehouse                                     | Amazon Redshift  |
| Business intelligence                              | Amazon Redshift  |
| Columnar storage                                   | Amazon Redshift  |
| Parallel processing                                | Amazon Redshift  |
| High availability across AZs                       | RDS Multi-AZ     |
| Read-heavy workload                                | RDS read replica |
| Synchronous replication                            | Multi-AZ         |
| Asynchronous replication                           | Read replica     |
| Full operating-system access                       | Database on EC2  |

---

# 66. Subjective exam answer: Amazon RDS

> Amazon RDS is a managed relational database service that allows organisations to set up, operate and scale relational databases in AWS. It supports engines such as MySQL, PostgreSQL, MariaDB, Oracle, Microsoft SQL Server and Amazon Aurora. AWS manages tasks such as operating-system maintenance, database installation, patching, backups and high availability, while the customer manages the data, schema, queries and application optimisation. RDS also supports Multi-AZ deployment for high availability and read replicas for read scalability.

---

# 67. Subjective exam answer: Multi-AZ versus read replicas

> An RDS Multi-AZ deployment improves availability by synchronously replicating data from the primary database to a standby instance in another Availability Zone. If the primary fails, AWS can fail over to the standby. A read replica is different because it uses asynchronous replication and is intended to serve read queries and reduce the workload on the primary database. Therefore, Multi-AZ supports availability, while read replicas support read scalability.

---

# 68. Subjective exam answer: DynamoDB

> Amazon DynamoDB is a fully managed NoSQL database service that supports key-value and document data models. It stores data using tables, items and attributes, and every item must have a primary key. DynamoDB automatically partitions data to support horizontal scaling and provides low-latency read and write performance. It is suitable for mobile, web, gaming and Internet of Things applications that require fast, flexible and highly scalable access.

---

# 69. Subjective exam answer: Redshift

> Amazon Redshift is a fully managed cloud data-warehouse service designed for analysing large datasets. It uses columnar storage to reduce the amount of data read during analytical queries and massively parallel processing to distribute work across multiple compute nodes. Redshift integrates with SQL and business-intelligence tools and is suitable for enterprise reporting, historical analysis and big-data analytics.

---

# 70. Subjective exam answer: Aurora

> Amazon Aurora is an enterprise-class relational database engine managed through Amazon RDS. It is compatible with MySQL and PostgreSQL and provides high performance, scalability, availability and durability. Aurora automates tasks such as provisioning, patching, backup, recovery and failure repair. Its distributed storage architecture keeps multiple copies of data across several Availability Zones.

---

# 71. Quick scenario practice

## Scenario A

> A bank needs a structured database for accounts, customers and transfers.

**Answer:** Amazon RDS or Aurora.

Reason: relationships and transactions matter.

---

## Scenario B

> A game stores the current state of millions of players and retrieves each record using PlayerID.

**Answer:** DynamoDB.

Reason: key-based access, low latency and large scale.

---

## Scenario C

> Management wants to analyse seven years of sales using dashboards.

**Answer:** Redshift.

Reason: large-scale historical analytics.

---

## Scenario D

> The database must survive an Availability Zone failure.

**Answer:** RDS Multi-AZ.

Reason: synchronous standby and failover.

---

## Scenario E

> The application performs far more reads than writes.

**Answer:** RDS read replicas.

Reason: offload read queries.

---

## Scenario F

> The company requires direct access to the operating system and custom database extensions.

**Answer:** Database on EC2.

Reason: RDS does not provide normal operating-system control.

---

## Scenario G

> The company wants a high-performance database compatible with its existing MySQL application.

**Answer:** Amazon Aurora MySQL-compatible edition.

---

# 72. Memory sheet

```text
AMAZON RDS

- Managed relational database service
- Supports several database engines
- SQL, transactions and relationships
- Multi-AZ for availability
- Read replicas for read scaling
- AWS manages patching, backups and infrastructure
```

```text
RDS MULTI-AZ

- Primary + standby
- Different Availability Zones
- Synchronous replication
- Automatic failover
- High availability
- Not mainly for read scaling
```

```text
RDS READ REPLICA

- Copy of primary database
- Asynchronous replication
- Handles read queries
- Reduces primary workload
- Can be promoted when needed
```

```text
AMAZON DYNAMODB

- Fully managed NoSQL
- Tables, items and attributes
- Key-value and document models
- Partition key
- Optional sort key
- Flexible schema
- Low latency
- Horizontal scaling
```

```text
AMAZON REDSHIFT

- Fully managed data warehouse
- Historical analytics
- SQL and BI tools
- Columnar storage
- Parallel processing
- Leader node and compute nodes
```

```text
AMAZON AURORA

- Relational database engine
- Managed through RDS
- MySQL or PostgreSQL compatible
- High performance
- Multi-AZ distributed storage
- Automated backup and recovery
```

```text
FAST DECISION

Transactions and SQL?       → RDS
Enterprise MySQL/PostgreSQL? → Aurora
Key-value at massive scale?  → DynamoDB
Historical analytics?       → Redshift
Full OS control?             → Database on EC2
```

# Module 8 in one paragraph

AWS provides several database services because transactional, NoSQL and analytical workloads require different designs. Amazon RDS is a managed relational database service that supports complex queries and transactions while automating maintenance, backups and availability. RDS Multi-AZ uses synchronous replication for high availability, whereas read replicas use asynchronous replication to scale read workloads. Amazon DynamoDB is a fully managed NoSQL service that stores flexible items using partition and sort keys and provides low-latency performance at large scale. Amazon Redshift is a managed data warehouse that uses columnar storage and parallel processing for business intelligence and large analytical queries. Amazon Aurora is an AWS-designed relational engine managed through RDS, compatible with MySQL and PostgreSQL, and built for strong performance, scalability and resilience.


---

</details>



<details>
<summary><strong>Module 1: Cloud Concepts Overview — Subjective Exam Preparation</strong></summary>

For a **subjective exam**, you do not need to memorise every sentence in the slides. You need to be able to **define the concept, explain why it matters, and apply it to a scenario**.

Chapter 1 mainly tests four areas:

1. Cloud computing concepts and models
2. Six advantages of cloud computing
3. AWS services and ways to interact with AWS
4. AWS Cloud Adoption Framework (AWS CAF) 

---

# 1. What is cloud computing?

The safest exam definition is:

> **Cloud computing is the on-demand delivery of compute power, databases, storage, applications, and other IT resources through the internet using pay-as-you-go pricing.**

The three keywords are:

```text
On-demand
Via the internet
Pay-as-you-go
```

### What this means

Instead of a company purchasing and maintaining physical infrastructure first, it can request resources when required.

For example:

```text
Traditional:
Need server
→ Purchase
→ Wait
→ Install
→ Configure

Cloud:
Need server
→ Provision it on demand
```

### Good subjective answer

> Cloud computing enables organisations to access IT resources such as compute, storage and databases on demand through the internet. Customers normally pay according to their usage instead of purchasing all infrastructure upfront. This makes the environment more flexible because resources can be provisioned and adjusted according to changing requirements.

---

# 2. Infrastructure as hardware vs infrastructure as software

This is one of the conceptual points from Chapter 1.

## Traditional model

Infrastructure is treated as **hardware**.

A company must:

* purchase servers;
* provide physical space;
* provide physical security;
* employ staff;
* install equipment;
* maintain equipment;
* estimate future capacity.

## Cloud model

Infrastructure can be treated more like **software**.

Resources can be:

* created;
* changed;
* removed;
* automated;
* provisioned through commands or APIs.

### Exam explanation

> In traditional computing, infrastructure is mainly physical hardware that must be purchased and maintained. Cloud computing allows infrastructure to be treated more like software because resources can be created and modified programmatically. This makes cloud infrastructure more flexible and faster to change.

A useful phrase from the module is that cloud helps reduce **undifferentiated heavy lifting**—routine infrastructure work that is necessary but does not directly differentiate the business. 

---

# 3. Cloud service models: IaaS, PaaS and SaaS

This is highly likely to appear in theory or scenario form.

The important idea is:

> **The difference is how much of the IT environment the customer manages.**

## IaaS — Infrastructure as a Service

The customer gets infrastructure and retains the most control.

Think:

```text
Provider supplies infrastructure.
Customer manages more of the system.
```

Example from later AWS modules:

* Amazon EC2

### Use IaaS when:

* operating-system control is required;
* custom software must be installed;
* the customer wants greater infrastructure control.

### Subjective answer

> Infrastructure as a Service provides basic computing infrastructure such as virtual machines, networking and storage. The customer retains greater control over the operating system, software and configuration, while the cloud provider manages the physical infrastructure.

---

## PaaS — Platform as a Service

The provider manages more of the underlying environment.

The customer focuses mainly on:

* application code;
* application data.

Example later in the course:

* AWS Elastic Beanstalk

### Subjective answer

> Platform as a Service provides a managed platform for developing and deploying applications. The provider manages more of the underlying infrastructure and operating environment, allowing developers to focus mainly on their application and data.

---

## SaaS — Software as a Service

The customer simply uses the finished software.

The provider manages almost everything underneath.

### Subjective answer

> Software as a Service provides a complete application that users access without managing the underlying infrastructure or platform. The provider manages the hardware, operating system, application and supporting environment.

---

# 4. IaaS vs PaaS vs SaaS

Remember this direction:

```text
MORE CUSTOMER CONTROL

IaaS
 ↓
PaaS
 ↓
SaaS

LESS CUSTOMER CONTROL
```

The reverse is also true:

```text
MORE PROVIDER MANAGEMENT

SaaS
 ↓
PaaS
 ↓
IaaS
```

### Scenario example

> A company wants full control over the operating system of its virtual servers.

**Answer: IaaS**

Because the customer wants greater infrastructure control.

---

> Developers only want to upload application code and do not want to manage the underlying environment.

**Answer: PaaS**

---

> Employees simply need to use a finished application through the internet.

**Answer: SaaS**

---

# 5. Cloud deployment models

Do not confuse **service model** with **deployment model**.

```text
IaaS / PaaS / SaaS
= How the service is managed

Cloud / Hybrid / On-premises
= Where the infrastructure is deployed
```

The module teaches three deployment models. 

---

## Cloud

The application is deployed in a cloud environment.

```text
Organisation
    ↓
Cloud provider
```

The organisation does not need to own all of the underlying infrastructure.

---

## On-premises / private cloud

Infrastructure remains within the organisation's own environment.

The organisation handles more of:

* hardware;
* networking;
* physical security;
* maintenance.

---

## Hybrid

Hybrid combines:

```text
On-premises
+
Cloud
```

### Example

A bank keeps some existing systems in its own data centre while deploying new web applications on AWS.

### Good answer

> A hybrid deployment combines cloud infrastructure with an organisation's existing on-premises infrastructure. It is useful when some workloads must remain on-premises while other workloads benefit from cloud scalability and flexibility.

---

# 6. The six advantages of cloud computing

This is probably the **single most important memorisation area** in Chapter 1.

You need to know all six and be able to explain them.

The module lists: 

1. Trade capital expense for variable expense
2. Benefit from massive economies of scale
3. Stop guessing capacity
4. Increase speed and agility
5. Stop spending money running and maintaining data centers
6. Go global in minutes

---

# 7. Advantage 1 — Trade capital expense for variable expense

## Traditional

A company purchases infrastructure before using it.

Example:

```text
Buy servers
Buy storage
Buy networking
Build data centre
```

This requires **capital expenditure**.

## Cloud

The organisation uses resources and pays based on consumption.

This is closer to **variable expense**.

### Good exam answer

> Cloud computing allows organisations to replace large upfront capital investments in data centres and hardware with variable expenses. Instead of purchasing infrastructure based on forecasts, customers can consume cloud resources and pay according to actual usage.

### Scenario clue

If the question says:

> “The company does not want to purchase expensive servers upfront.”

Think:

**Trade capital expense for variable expense.**

---

# 8. Advantage 2 — Massive economies of scale

AWS combines demand from many customers.

Because AWS operates at enormous scale, it can achieve lower per-unit operating costs.

### Good answer

> AWS benefits from economies of scale because it operates infrastructure for a large number of customers. The combined scale allows AWS to achieve cost efficiencies that an individual organisation may not achieve on its own, and some of these savings can be passed to customers.

### Scenario clue

> “Why can a large cloud provider potentially offer lower unit costs than a small company running its own data centre?”

**Massive economies of scale.**

---

# 9. Advantage 3 — Stop guessing capacity

Traditional organisations have to estimate future peak demand.

There are two bad possibilities.

## Overestimate

```text
Capacity purchased > actual demand
```

Result:

* idle infrastructure;
* wasted money.

## Underestimate

```text
Capacity purchased < actual demand
```

Result:

* poor performance;
* insufficient capacity.

Cloud allows resources to scale more closely with actual demand.

### Good answer

> Cloud computing reduces the need to predict maximum infrastructure capacity far in advance. Organisations can increase resources when demand rises and reduce them when demand falls. This reduces both overprovisioning and underprovisioning.

### Scenario clue

> “Traffic changes significantly during the year.”

Think:

**Stop guessing capacity.**

This is also exactly the idea behind the module's sample exam question: EC2 is economical for varying workloads because instances can be launched on demand. 

---

# 10. Advantage 4 — Increase speed and agility

Traditional:

```text
Request hardware
↓
Approve purchase
↓
Order
↓
Deliver
↓
Install

Potentially weeks
```

Cloud:

```text
Request resource
↓
Launch

Potentially minutes
```

### Good answer

> Cloud computing increases speed and agility because resources can be provisioned much more quickly than physical infrastructure. This allows organisations to test ideas, develop applications and respond to business changes faster.

### Scenario clue

> “The development team currently waits several weeks for new servers.”

Think:

**Increase speed and agility.**

---

# 11. Advantage 5 — Stop spending money running and maintaining data centers

Physical data centres require:

* power;
* cooling;
* physical security;
* staff;
* maintenance;
* building space;
* hardware replacement.

AWS manages the underlying cloud infrastructure.

### Good answer

> Cloud computing reduces the need for organisations to operate and maintain their own physical data centres. This allows staff and financial resources to be focused more on the organisation's business and customers rather than routine infrastructure maintenance.

### Scenario clue

> “The company wants IT staff to focus on customers instead of server maintenance.”

Think:

**Stop spending money running and maintaining data centers.**

---

# 12. Advantage 6 — Go global in minutes

AWS has infrastructure in multiple geographic locations.

A company can deploy resources closer to users in different parts of the world without constructing its own international data centres.

### Good answer

> AWS enables organisations to deploy applications in multiple geographic locations relatively quickly. This allows businesses to reach users around the world and place resources closer to customers without building their own global infrastructure.

### Scenario clue

> “A company wants to expand its application from Malaysia to Europe and the United States quickly.”

Think:

**Go global in minutes.**

---

# 13. Six advantages — rapid memory method

Learn this:

```text
MONEY
SCALE
CAPACITY
SPEED
DATA CENTER
GLOBAL
```

Then expand:

| Keyword     | Advantage                    |
| ----------- | ---------------------------- |
| Money       | CapEx → variable expense     |
| Scale       | Economies of scale           |
| Capacity    | Stop guessing capacity       |
| Speed       | Speed and agility            |
| Data center | Stop maintaining it yourself |
| Global      | Go global in minutes         |

---

# 14. What is AWS?

The module describes AWS as a secure cloud platform offering a broad set of global cloud-based products called **services**. 

AWS provides on-demand access to things such as:

* compute;
* storage;
* databases;
* networking;
* security;
* management tools.

The important idea:

> **AWS services work together like building blocks.**

---

# 15. AWS service categories

For Chapter 1, don't waste time trying to memorise every icon on page 25.

Know the major categories that appear throughout the course:

| Category        | Examples                  |
| --------------- | ------------------------- |
| Compute         | EC2, Lambda               |
| Storage         | S3, EBS, EFS              |
| Database        | RDS, DynamoDB             |
| Networking      | VPC, Route 53, CloudFront |
| Security        | IAM, KMS, Shield          |
| Management      | CloudWatch, CloudTrail    |
| Cost Management | Budgets, Cost Explorer    |

Chapter 1's point is simply:

> AWS offers many services, and the correct service depends on the organisation's **business goals and technology requirements**.

---

# 16. Simple AWS solution architecture

The module provides an example using:

```text
Users
 ↓
Amazon VPC
 ↓
Amazon EC2
 ├── Amazon DynamoDB
 └── Amazon S3
```

Interpret it like this:

```text
VPC      → Networking
EC2      → Compute
DynamoDB → Database
S3       → Storage
```

A subjective question might ask you to explain why AWS uses several services together.

Good answer:

> AWS services are designed as building blocks. An application can combine networking, compute, database and storage services according to its requirements rather than relying on one service to perform every task.

---

# 17. Three ways to interact with AWS

You must know these three:

```text
Management Console
AWS CLI
AWS SDK
```

---

## AWS Management Console

A graphical browser interface.

Think:

> **Click**

### Answer

> The AWS Management Console provides a graphical user interface that enables users to access and manage AWS services through a web browser.

---

## AWS CLI

Command Line Interface.

Think:

> **Commands and scripts**

### Answer

> The AWS CLI enables users to interact with AWS services using commands and scripts, making it useful for automation and repeatable administrative tasks.

---

## AWS SDK

Software Development Kit.

Think:

> **Application code**

### Answer

> AWS SDKs allow developers to access AWS services directly from programming languages such as Python or Java. They are useful when an application needs to interact programmatically with AWS resources.

---

# 18. Console vs CLI vs SDK

```text
Console → Click
CLI     → Command
SDK     → Code
```

Possible subjective scenario:

> “A company needs to automatically create AWS resources through a shell script.”

**CLI**

> “A Python application must upload files automatically to S3.”

**SDK**

> “A beginner wants to configure AWS using a graphical interface.”

**Management Console**

---

# 19. AWS Cloud Adoption Framework

This section tends to look worse than it actually is.

The important question is:

> **What does an organisation need to think about before and during cloud adoption?**

AWS CAF provides guidance and best practices to help organisations develop a structured approach to cloud adoption. 

The module uses six perspectives:

```text
Business
People
Governance
Platform
Security
Operations
```

---

# 20. Two groups of AWS CAF perspectives

The module groups them like this:

## Business capabilities

```text
Business
People
Governance
```

## Technical capabilities

```text
Platform
Security
Operations
```

This division is worth remembering.

---

# 21. Business perspective

Main question:

> **Why are we moving to the cloud, and does it create business value?**

Focuses on:

* IT finance;
* IT strategy;
* benefits realization;
* business risk management.

Stakeholders include:

* business managers;
* finance managers;
* budget owners;
* strategy stakeholders.

### Scenario

> “Management wants to ensure AWS investment produces measurable business benefits.”

**Business perspective**

### Good answer

> The Business perspective ensures that IT strategy and cloud investments align with business needs and produce measurable business outcomes. It focuses on areas such as IT finance, strategy, benefits realization and business risk.

---

# 22. People perspective

Main question:

> **Do our employees have the skills and organisational support to adopt cloud?**

Focuses on:

* staffing;
* training;
* career management;
* incentives;
* organisational change.

Stakeholders include:

* HR;
* staffing managers;
* people managers.

### Scenario

> “Employees require cloud training and new roles before migration.”

**People perspective**

### Good answer

> The People perspective focuses on organisational skills, staffing, training and change management. Its purpose is to prepare employees and organisational structures for successful cloud adoption.

---

# 23. Governance perspective

Main question:

> **How do we control, measure and align the cloud programme with organisational goals?**

Focuses on:

* portfolio management;
* project and programme management;
* business performance measurement;
* licence management.

Stakeholders include:

* CIO;
* programme managers;
* enterprise architects;
* business analysts;
* portfolio managers.

### Scenario

> “Management wants cloud projects to follow company strategy and be properly measured.”

**Governance**

### Good answer

> The Governance perspective ensures that cloud initiatives, IT strategy and business goals remain aligned. It includes programme management, portfolio management, performance measurement and licence management to maximise business value and reduce business risk.

---

# 24. Platform perspective

Main question:

> **What technical architecture should we build?**

Focuses on:

* compute;
* networking;
* storage;
* databases;
* architecture;
* application development.

Stakeholders:

* CTO;
* IT managers;
* solutions architects.

### Scenario

> “The organisation is deciding how EC2, networking, databases and storage should be designed.”

**Platform perspective**

### Good answer

> The Platform perspective focuses on designing and implementing the target cloud architecture. It includes compute, network, storage and database provisioning as well as systems architecture and application development.

---

# 25. Security perspective

Main question:

> **How will we protect the cloud environment?**

Focuses on:

* identity and access management;
* detective controls;
* infrastructure security;
* data protection;
* incident response.

Stakeholders:

* CISO;
* security managers;
* security analysts.

### Scenario

> “The company needs access controls and an incident-response process.”

**Security perspective**

### Good answer

> The Security perspective ensures that the organisation meets its security objectives. It focuses on identity and access management, infrastructure security, data protection, detection and incident response.

---

# 26. Operations perspective

Main question:

> **How will we run the cloud environment every day?**

Focuses on:

* service monitoring;
* application performance;
* inventory;
* release/change management;
* reporting;
* business continuity;
* disaster recovery;
* service catalogue.

Stakeholders:

* IT operations managers;
* support managers.

### Scenario

> “The organisation needs monitoring, change management and disaster recovery.”

**Operations perspective**

### Good answer

> The Operations perspective focuses on the ongoing operation and support of cloud workloads. It includes monitoring, change management, resource management, reporting, business continuity and disaster recovery.

---

# 27. The easiest AWS CAF memory method

Do not try to memorise the long capability lists first.

Remember these six questions:

```text
BUSINESS
Why are we doing it?

PEOPLE
Who needs skills and change?

GOVERNANCE
What rules and oversight are needed?

PLATFORM
What will we build?

SECURITY
How will we protect it?

OPERATIONS
How will we run it?
```

Then add detail if the question requires it.

---

# 28. CAF scenario table

| Scenario                                        | CAF perspective |
| ----------------------------------------------- | --------------- |
| Cost, value and business strategy               | Business        |
| Training and staffing                           | People          |
| Policies, projects and organisational oversight | Governance      |
| Compute/network/storage/database design         | Platform        |
| Access control and data protection              | Security        |
| Monitoring and disaster recovery                | Operations      |

---

# 29. Likely subjective question: “Explain the benefits of cloud computing.”

A strong answer:

> Cloud computing provides several advantages over traditional computing. First, organisations can trade large capital expenditure for variable expense by paying for resources according to usage. Second, cloud providers can achieve economies of scale. Third, organisations do not need to predict maximum capacity far in advance because resources can scale according to demand. Fourth, resources can be provisioned quickly, improving speed and agility. Fifth, organisations can reduce the burden of operating and maintaining physical data centres. Finally, cloud infrastructure enables organisations to deploy resources globally more quickly.

That is enough for a good full-mark theoretical answer if supported by relevant scenario examples.

---

# 30. Likely subjective question: “Differentiate IaaS, PaaS and SaaS.”

Answer in comparison form:

> IaaS provides fundamental infrastructure such as virtual machines and gives customers the greatest control over the operating system and configuration. PaaS provides a managed application platform so developers can focus more on application code while the provider manages more of the infrastructure. SaaS provides a complete software application that users consume without managing the underlying platform or infrastructure. Therefore, customer control generally decreases from IaaS to PaaS to SaaS.

---

# 31. Likely subjective question: “Explain hybrid cloud.”

> A hybrid deployment combines cloud infrastructure with an organisation's on-premises environment. Some applications or data remain on-premises while other workloads use cloud services. This approach can be useful when an organisation must retain certain existing or sensitive systems locally while benefiting from cloud scalability, flexibility and other cloud services.

---

# 32. Likely subjective question: “Explain AWS CAF.”

A concise full answer:

> The AWS Cloud Adoption Framework provides guidance and best practices that help organisations prepare for successful cloud adoption. It recognises that cloud adoption affects the whole organisation rather than only the IT department. In the module, AWS CAF consists of six perspectives: Business, People, Governance, Platform, Security and Operations. Business, People and Governance focus mainly on business capabilities, while Platform, Security and Operations focus mainly on technical capabilities.

Then explain each perspective briefly if more marks are available.

---

# 33. How to answer a scenario question

Do not just define the concept.

Use this structure:

**1. Identify the concept.**
**2. Explain what it means.**
**3. Connect it directly to the scenario.**

Example:

> A retailer experiences very high traffic only during holiday sales. Explain one advantage of cloud computing.

Weak answer:

> Cloud computing has elasticity.

Better answer:

> One relevant advantage is that the organisation can stop guessing capacity. In a traditional environment, the retailer might purchase enough servers for peak holiday traffic even though those servers would remain underused during the rest of the year. With cloud computing, resources can be increased when holiday demand rises and reduced afterward, which helps reduce overprovisioning and unnecessary cost.

That **last sentence connecting to the scenario** is what often separates a decent subjective answer from somebody vomiting a definition onto the page and hoping the examiner is feeling charitable.

---

# 34. Common mistakes to avoid

**Cloud ≠ free.** It is generally based on consumption.

**Hybrid ≠ two cloud services.** It means cloud + on-premises.

**IaaS/PaaS/SaaS ≠ deployment models.**

**“Stop guessing capacity” ≠ no capacity planning whatsoever.** It means capacity can adjust more dynamically.

**AWS CAF ≠ only technical architecture.** Half of its perspectives in this module are business-focused.

**Platform ≠ Operations.**

```text
Platform → design/build
Operations → run/manage
```

**Business ≠ Governance.**

```text
Business → value and strategy
Governance → oversight and alignment
```

---

# 35. What I would prioritise before the exam

If you are short on time, know these extremely well:

```text
1. Cloud definition:
   On-demand + internet + pay-as-you-go

2. IaaS vs PaaS vs SaaS

3. Cloud vs Hybrid vs On-premises

4. Six cloud advantages

5. Console vs CLI vs SDK

6. AWS CAF:
   Business
   People
   Governance
   Platform
   Security
   Operations
```

Those six areas cover most of the meaningful theoretical content in Chapter 1. 

---

# Final 2-minute revision

```text
CLOUD COMPUTING
On-demand IT resources
+ Internet
+ Pay-as-you-go
```

```text
SERVICE MODELS
IaaS → Infrastructure / most control
PaaS → Platform / focus on application
SaaS → Finished software / least control
```

```text
DEPLOYMENT
Cloud
Hybrid = Cloud + On-premises
On-premises/private
```

```text
6 ADVANTAGES
1. CapEx → Variable expense
2. Economies of scale
3. Stop guessing capacity
4. Speed and agility
5. Stop maintaining data centers
6. Go global in minutes
```

```text
AWS ACCESS
Console → Click
CLI → Command
SDK → Code
```

```text
CAF
Business   → Value
People     → Skills
Governance → Rules
Platform   → Build
Security   → Protect
Operations → Run
```

For a subjective paper, the most important skill is **not memorising longer definitions**. It is being able to see a scenario and recognise which of those concepts explains it, then give a two- or three-sentence justification.


</details>



<details>
<summary><strong>Module 2: Cloud Economics and Billing — Subjective Exam Preparation</strong></summary>

For a **subjective exam**, Module 2 is less about calculating random AWS prices and more about explaining **how AWS pricing works, how companies compare AWS with on-premises infrastructure, and which AWS tools solve different cost-management problems**.

The module itself expects you to understand five areas: **fundamentals of pricing, Total Cost of Ownership, AWS Organizations, AWS Billing and Cost Management, and AWS Technical Support.** 

The easiest way to think about the entire chapter is:

```text
How does AWS charge me?
        ↓
Would AWS actually be cheaper than owning infrastructure?
        ↓
What might my AWS architecture cost?
        ↓
How do I manage costs across many AWS accounts?
        ↓
How do I monitor the bill?
        ↓
What support do I get if something goes wrong?
```

---

# 1. AWS pricing philosophy

The first thing you should understand is that AWS does **not** have one universal price.

Its pricing depends on the resources you actually consume.

The module gives three fundamental AWS cost drivers:

```text
Compute
Storage
Data transfer
```

For compute, cost generally depends on things such as how long the resource runs and the type of compute resource. Storage is typically charged according to the amount stored, while data transfer commonly becomes chargeable when data is transferred outbound. The module states that inbound data transfer generally has no charge, with exceptions. 

### Intuitive example

Imagine you operate an online shop.

Your AWS bill might consist of:

```text
EC2 servers running
       ↓
COMPUTE COST

Images and files stored
       ↓
STORAGE COST

Customers downloading content
       ↓
DATA TRANSFER COST
```

So if the examiner asks:

> “What are the fundamental drivers of AWS cost?”

Your answer should be:

> The three fundamental cost drivers are compute, storage and data transfer. Compute cost depends on the computing resources and duration used, storage is normally based on the amount of data stored, and outbound data transfer may incur charges depending on the service and destination.

---

# 2. The three AWS pricing ideas

The module presents three basic ways customers can reduce or control cost:

```text
Pay for what you use
Pay less when you reserve
Pay less when you use more
```



These are important because they explain the **AWS pricing philosophy**, rather than just one particular service.

---

# 3. Pay for what you use

The idea is simple:

> You pay for services that you consume instead of purchasing a large amount of infrastructure upfront.

### Traditional model

A company predicts that it might need 20 servers.

So it buys:

```text
20 physical servers
↓
Pay now
↓
Use them later
```

Even if only 8 are normally needed, the company already owns all 20.

### AWS model

The company can consume resources according to actual requirements.

```text
Need more → use more
Need less → use less
```

The module describes this as paying only for services consumed without large upfront expenses. 

### Good subjective answer

> AWS follows a consumption-based pricing approach where customers pay for the resources they use rather than making large upfront infrastructure purchases. This helps organisations align expenditure more closely with actual workload requirements and reduce the cost of unused capacity.

---

# 4. Pay less when you reserve

The second idea is:

> If the customer can commit to predictable usage, AWS may provide discounted pricing.

The module explains this using **Reserved Instances** and gives three payment approaches:

| Payment option in the module      | General idea     |
| --------------------------------- | ---------------- |
| No Upfront Reserved Instance      | Smaller discount |
| Partial Upfront Reserved Instance | Larger discount  |
| All Upfront Reserved Instance     | Largest discount |

The slide states that Reserved Instances could provide savings of up to 75% in the pricing material used for this course. 

The intuitive reason is commitment.

```text
No commitment
→ Greater flexibility
→ Usually higher unit price

Longer commitment
→ More predictable usage
→ Potential discount
```

### Scenario

> A company knows that a server will be required continuously for several years.

A reservation can make more sense than repeatedly paying flexible On-Demand pricing.

### Good subjective answer

> AWS customers can reduce costs when they commit to predictable resource usage. Reserved pricing provides lower rates in exchange for a longer commitment, and the module shows that a greater upfront payment generally provides a larger discount.

Do **not** write:

> “Reserved is always cheaper therefore always use Reserved.”

If the workload disappears after two months, congratulations, you obtained a discount on something you no longer need.

---

# 5. Pay less by using more

AWS can also provide **volume-based or tiered pricing**.

The module gives S3, EBS and EFS as examples where increasing usage can reduce the cost **per GB** under relevant tiered pricing structures. 

Important distinction:

```text
Use more
→ Price PER UNIT may decrease

Does NOT mean
→ Total bill must decrease
```

If you store 100 TB instead of 1 GB, your bill will not magically collapse out of gratitude.

### Good answer

> Some AWS services use tiered pricing, where the unit cost may decrease as the customer's usage increases. This creates volume-based savings while allowing customers to choose services and storage options appropriate to their requirements.

---

# 6. Economies of scale

The module also explains that AWS's enormous combined customer usage allows it to achieve **economies of scale**.

Meaning:

```text
AWS operates at enormous scale
↓
AWS can lower its own unit operating costs
↓
Some savings can be passed to customers
```

The slide contains historical examples of AWS price reductions, but for a subjective answer, the concept is much more important than memorising an old count of price changes. 

### Good answer

> AWS benefits from economies of scale because it operates infrastructure for many customers at very large scale. This enables AWS to achieve efficiencies that individual organisations may not achieve independently and potentially pass some of those savings to customers.

---

# 7. Free AWS service does not mean a free architecture

The module gives examples of services that have no separate charge in the teaching material, including IAM, Amazon VPC, Auto Scaling, CloudFormation and Elastic Beanstalk. However, it explicitly warns that **other AWS services used with them can still incur charges**. 

For example:

```text
Elastic Beanstalk
→ No separate Beanstalk service charge in the module

But it may provision:
EC2
Load balancer
Storage
etc.

Those resources
→ Can still cost money
```

This is a classic exam trap.

### Subjective answer

> Some AWS services do not have a separate service charge, but resources that those services create or use may still incur charges. Therefore, the absence of a direct service fee does not mean the complete architecture is free.

---

# 8. AWS Free Tier

The 2022 module describes AWS Free Tier as allowing new customers to gain hands-on experience with eligible AWS services under limited free usage. 

For the exam, understand the **concept**:

```text
Free Tier
≠
Every AWS service is unlimited and free
```

It only applies within eligible conditions and limits defined by the course material.

---

# 9. What is Total Cost of Ownership?

This is probably the biggest theoretical idea in Module 2 after pricing.

**Total Cost of Ownership, or TCO, is a financial estimate used to identify both the direct and indirect costs of a system.**

The module says TCO is useful for comparing on-premises infrastructure with AWS and for building the financial business case for moving to the cloud. 

The keyword is:

> **TOTAL**

---

# 10. Why simply comparing server prices is wrong

Imagine:

```text
Physical server = RM20,000
AWS compute = RM15,000
```

Can you immediately conclude AWS is RM5,000 cheaper?

No.

The physical server also requires things like:

```text
Networking
Storage
Software licences
Administrators
Building space
Power
Cooling
Maintenance
```

TCO exists because pretending electricity and IT staff are free makes for wonderfully optimistic accounting.

---

# 11. Four major TCO categories

The module groups TCO considerations into four major categories. 

| Category            | Examples from the module                                                    |
| ------------------- | --------------------------------------------------------------------------- |
| **Server costs**    | Servers, racks, PDUs, switches, OS and virtualisation licences, maintenance |
| **Storage costs**   | Storage disks, SAN/FC equipment, storage administration                     |
| **Network costs**   | LAN switches, load balancers, bandwidth, network administration             |
| **IT labour costs** | Server, storage and network administration                                  |

And across the infrastructure there are also **facility costs** such as:

```text
Space
Power
Cooling
```

So a good mental model is:

```text
TCO
=
Hardware
+ Software
+ Storage
+ Networking
+ Administration
+ Facilities
+ Maintenance
```

---

# 12. Subjective answer — TCO

> Total Cost of Ownership is a financial estimate that considers both the direct and indirect costs of operating an IT system. It can be used to compare an on-premises environment with AWS and to build a business case for cloud migration. A complete TCO analysis should consider server hardware, software licences, storage, networking, IT administration, maintenance, physical space, power and cooling rather than comparing only the purchase price of servers.

That is a strong exam answer.

---

# 13. Hard benefits and soft benefits

The module also distinguishes **hard benefits** from **soft benefits** when considering a move to AWS. 

Hard benefits are easier to quantify financially, such as reduced spending on compute, storage, networking, hardware, software, operations, backup and disaster recovery.

Soft benefits are less directly measured in RM or dollars but may still be valuable, such as:

```text
Higher developer productivity
Improved customer satisfaction
Greater business agility
Faster response to opportunities
Greater global reach
```

### Exam distinction

```text
Hard benefit
→ directly measurable financial saving

Soft benefit
→ operational/business improvement
```

---

# 14. TCO does NOT prove AWS is always cheaper

The module gives an illustrative case where moving to AWS produced very large savings.

Do not turn that into:

> “AWS always saves 96%.”

That would be spectacularly bad reasoning.

TCO is used to **compare the specific alternatives**.

A better answer is:

> TCO helps an organisation identify whether cloud migration is financially attractive by comparing all relevant direct and indirect costs. The result depends on the organisation's workload, infrastructure and operating model.

---

# 15. AWS Pricing Calculator

The next concept is much easier.

The **AWS Pricing Calculator** is used **before deploying an architecture** to estimate its AWS cost.

According to the module, it can be used to estimate monthly costs, model solutions before building them, explore the calculations behind an estimate, compare available instance types or contract terms, and organise services into estimate groups. 

Memory:

```text
Pricing Calculator
=
"What MIGHT this cost?"
```

---

# 16. Pricing Calculator vs TCO

These are related but not interchangeable.

| Tool/concept               | Question it answers                                                              |
| -------------------------- | -------------------------------------------------------------------------------- |
| **AWS Pricing Calculator** | What might this AWS solution cost?                                               |
| **TCO**                    | How does the complete cost of AWS compare with alternatives such as on-premises? |

### Scenario A

> “We have not built the application yet and want to estimate its monthly EC2 and storage cost.”

**AWS Pricing Calculator**

### Scenario B

> “Should we close our physical data centre and move to AWS?”

**TCO analysis**

---

# 17. Pricing Calculator is an estimate, not the invoice

Suppose your estimate says:

```text
Estimated monthly cost = $500
```

But after deployment:

```text
You use more compute
You store more data
You transfer more data
```

Then:

```text
Actual bill ≠ necessarily $500
```

The calculator works from the assumptions you enter.

### Good answer

> The AWS Pricing Calculator provides an estimated cost based on the selected AWS services and expected usage. It is useful for planning before deployment, but actual charges may differ if the real workload or resource usage differs from the assumptions in the estimate.

---

# 18. AWS Organizations

Now imagine a large company has:

```text
Production AWS account
Development AWS account
Finance AWS account
HR AWS account
Security AWS account
```

Managing all of them independently becomes messy.

**AWS Organizations** lets the company centrally organise and manage multiple AWS accounts.

The module highlights four benefits:

```text
Policy-based account management
Group-based account management
APIs for automated account management
Consolidated billing
```



---

# 19. Organization, Root and Organizational Units

The page 32 diagram shows AWS Organizations as a hierarchy:

```text
Organization
     ↓
    Root
     ↓
Organizational Units (OUs)
     ↓
AWS accounts
```

An **OU** is a logical group of accounts.

For example:

```text
Organization
├── Production OU
│   ├── Website account
│   └── Database account
│
└── Development OU
    ├── Dev account
    └── Test account
```

This allows the company to apply organisational controls to groups of accounts instead of manually managing every account separately.

---

# 20. Consolidated billing

This is a major economic benefit of AWS Organizations.

Without consolidated billing:

```text
Account A → Separate bill
Account B → Separate bill
Account C → Separate bill
```

With AWS Organizations:

```text
Account A ┐
Account B ├→ Central billing view
Account C ┘
```

### Good subjective answer

> AWS Organizations enables organisations to centrally manage multiple AWS accounts and provides consolidated billing. This simplifies financial management because charges from member accounts can be viewed centrally while the organisation can still maintain separate accounts for different teams or workloads.

---

# 21. AWS Organizations and SCPs

The module shows **Service Control Policies (SCPs)** as a mechanism used to control access to AWS services for accounts or groups of accounts within OUs. 

The setup shown in the module is:

```text
Create Organization
↓
Create Organizational Units
↓
Create Service Control Policies
↓
Test restrictions
```



For Module 2, the important idea is:

> AWS Organizations can be used not only for consolidated billing, but also for central account governance.

---

# 22. AWS Organizations vs IAM

A simple distinction:

```text
AWS Organizations
→ Manage multiple AWS accounts

IAM
→ Manage users, groups, roles and permissions
```

Do not write that Organizations replaces IAM.

It doesn't.

---

# 23. AWS Billing and Cost Management

Once an application is actually running, the question changes from:

> “What might this cost?”

to:

> “What are we actually spending?”

This section introduces the **Billing Dashboard, Bills, Cost Explorer, AWS Budgets, and Cost and Usage Report**. 

The easiest memory model is:

| Tool                  | Think                |
| --------------------- | -------------------- |
| Billing Dashboard     | Overview             |
| Bills                 | Charges              |
| Cost Explorer         | Analyse              |
| AWS Budgets           | Track against target |
| Cost and Usage Report | Detailed records     |

---

# 24. Billing Dashboard

The dashboard shown on page 40 includes a **spend summary**, **month-to-date spending by service**, and a **forecast**.

Think:

```text
Billing Dashboard
=
"Give me the financial overview."
```

It helps you quickly understand things such as:

```text
How much have we spent?
Which services are costing money?
What is the expected total?
```

---

# 25. AWS Bills

The monthly Bills page shows the charges contributing to the bill.

Think of your telephone bill.

```text
Total = RM300
```

You then want to know:

> “Where did RM300 come from?”

Bills gives the breakdown.

### Scenario

> “The finance manager wants to inspect the individual AWS service charges for the month.”

Think:

**AWS Bills**

---

# 26. AWS Cost Explorer

The module's Cost Explorer page shows historical monthly costs broken down by service.

Think:

> **Analyse cost patterns.**

For example:

```text
August:    $1,500
September: $2,100
October:   $2,050
```

Then:

> “Why did September cost more?”

Cost Explorer helps investigate that.

### Good answer

> AWS Cost Explorer helps organisations analyse AWS cost and usage patterns. It provides visualisation of spending over time and can break costs down by categories such as AWS service, making it useful for identifying trends and understanding where expenditure is occurring.

---

# 27. AWS Budgets

The page titled **Forecast and track costs** shows budget values together with:

```text
Current spending
Forecasted spending
Budgeted amount
```

So the memory is:

```text
AWS Budgets
=
"Are we within the target?"
```

### Scenario

> “Management wants to monitor a monthly AWS target of $1,000.”

Think:

**AWS Budgets**

A very important trap:

> A budget is not the same thing as a magical wall that makes AWS unable to charge above the number.

Its role in this module is to **track and monitor spending against budgets**.

---

# 28. Cost and Usage Report

The module's reporting page shows very detailed line-item information such as:

```text
Product code
Usage type
Operation
Availability Zone
Usage amount
Currency
Line-item description
```

Think:

```text
Cost and Usage Report
=
"Give me the detailed data."
```

This is suitable for deeper analysis or organisational reporting.

---

# 29. The five billing tools as one story

Suppose management asks five different questions.

| Question                          | Tool                  |
| --------------------------------- | --------------------- |
| “Give me a quick overview.”       | Billing Dashboard     |
| “What did AWS charge us for?”     | Bills                 |
| “Why has cost changed over time?” | Cost Explorer         |
| “Are we approaching our target?”  | AWS Budgets           |
| “Give us detailed usage records.” | Cost and Usage Report |

That table is far more useful than memorising five disconnected definitions.

---

# 30. Pricing Calculator vs Billing tools

Another useful timeline:

```text
BEFORE BUILDING
AWS Pricing Calculator
→ Estimate

AFTER / DURING USAGE
Billing Dashboard
Bills
Cost Explorer
Budgets
Cost and Usage Report
→ Monitor and analyse
```

This distinction is highly exam-worthy.

---

# 31. AWS Technical Support

The final section explains that different customers require different support levels.

Someone experimenting with AWS does not require the same support as a company whose entire payment system is down.

The module teaches four support plans:

| Support plan   | Intended use in the module               |
| -------------- | ---------------------------------------- |
| **Basic**      | General AWS resources                    |
| **Developer**  | Early development                        |
| **Business**   | Production workloads                     |
| **Enterprise** | Business- and mission-critical workloads |



For your exam, learn **this 2022 module's classification**.

---

# 32. Basic Support

The module associates Basic Support with resources such as:

```text
Resource Center
Service Health Dashboard
Product FAQs
Discussion forums
Health-check support
```

Think:

```text
Basic
→ General support resources
```

---

# 33. Developer Support

The module describes Developer Support as:

> **Support for early development on AWS.**

Scenario:

> “A small development team is building its first AWS application.”

Think:

**Developer Support**

---

# 34. Business Support

Business Support is aimed at customers running:

> **Production workloads.**

Scenario:

> “An ecommerce website is live and real customers depend on it.”

Think:

**Business Support**

---

# 35. Enterprise Support

Enterprise Support is aimed at:

> **Business- and mission-critical workloads.**

Scenario:

> “Failure of the AWS workload would significantly disrupt the company's core business.”

Think:

**Enterprise Support**

---

# 36. Support response times in the module

If your lecturer expects the exact table, the 2022 module shows:

| Plan       |        Critical |          Urgent |            High |          Normal |             Low |
| ---------- | --------------: | --------------: | --------------: | --------------: | --------------: |
| Basic      | No case support | No case support | No case support | No case support | No case support |
| Developer  |               — |               — |               — |       ≤12 hours |       ≤24 hours |
| Business   |               — |         ≤1 hour |        ≤4 hours |       ≤12 hours |       ≤24 hours |
| Enterprise |         ≤15 min |         ≤1 hour |        ≤4 hours |       ≤12 hours |       ≤24 hours |

I would treat this as **lower priority than understanding which support plan fits which scenario**, unless your lecturer specifically likes asking exact response-time tables.

---

# 37. TAM, Trusted Advisor and Support Concierge

These three are easy to mix up.

The module defines them as: 

| Feature                             | Main purpose       |
| ----------------------------------- | ------------------ |
| **Technical Account Manager (TAM)** | Proactive guidance |
| **AWS Trusted Advisor**             | Best practices     |
| **AWS Support Concierge**           | Account assistance |

Memory:

```text
TAM
→ Technical guidance

Trusted Advisor
→ Recommendations

Concierge
→ Account assistance
```

---

# 38. Likely subjective question — Explain AWS pricing philosophy

A strong answer:

> AWS uses a consumption-based pricing philosophy where customers generally pay for the resources they use rather than purchasing large amounts of infrastructure upfront. The main cost drivers include compute, storage and data transfer. Customers may reduce unit costs through longer-term reservations, volume-based pricing and AWS economies of scale. This model allows organisations to align infrastructure expenditure more closely with actual usage.

---

# 39. Likely subjective question — Explain TCO

> Total Cost of Ownership is a financial estimate used to identify both the direct and indirect costs of an IT system. It is useful when comparing an on-premises environment with AWS and when building a cloud-migration business case. TCO includes server, storage, network and IT labour costs as well as supporting costs such as software, maintenance, space, power and cooling.

---

# 40. Likely subjective question — Pricing Calculator vs Cost Explorer

> AWS Pricing Calculator is used before deployment to estimate the expected cost of a proposed AWS solution based on assumed usage. AWS Cost Explorer is used after AWS resources are being consumed to analyse actual cost and usage patterns over time. Therefore, the Pricing Calculator supports planning, while Cost Explorer supports cost analysis.

---

# 41. Likely subjective question — Explain AWS Organizations

> AWS Organizations enables central management of multiple AWS accounts. Accounts can be grouped into organizational units, policies can be applied centrally, and consolidated billing provides central visibility of account charges. This simplifies governance and financial management for organisations operating many AWS accounts.

---

# 42. Likely subjective question — Explain AWS cost-management tools

> AWS provides several tools for managing cloud costs. The Billing Dashboard provides a high-level spending overview, while AWS Bills shows the charges contributing to the monthly bill. AWS Cost Explorer visualises and analyses cost trends. AWS Budgets tracks spending against defined targets and forecasts, while the AWS Cost and Usage Report provides detailed cost and usage records for deeper analysis.

---

# 43. Likely subjective question — Explain AWS support options

> The module describes four AWS Support plans. Basic Support provides general support resources, Developer Support is designed for early development, Business Support is intended for production workloads, and Enterprise Support is intended for business- and mission-critical workloads. AWS also provides Technical Account Managers for proactive guidance, Trusted Advisor for best-practice recommendations, and Support Concierge for account assistance.

---

# 44. How to answer scenario questions

Use this structure:

```text
1. Name the concept/tool.
2. Explain what it does.
3. Connect it to the scenario.
```

Example:

> A company has 20 AWS accounts and wants one central billing structure.

Weak answer:

> AWS Organizations.

Better answer:

> The company should use AWS Organizations because it provides central management of multiple AWS accounts and supports consolidated billing. This would allow the company to keep separate accounts for different teams while giving finance central visibility over AWS charges.

That second answer actually earns subjective marks because it proves you understand **why**.

---

# 45. High-priority scenario clues

| If the question says...        | Think...              |
| ------------------------------ | --------------------- |
| Compute + storage + transfer   | AWS cost drivers      |
| Predictable long-term use      | Reserve / commitment  |
| Higher usage, lower unit price | Volume pricing        |
| AWS vs physical data centre    | TCO                   |
| Direct + indirect costs        | TCO                   |
| Before deployment              | Pricing Calculator    |
| Multiple AWS accounts          | AWS Organizations     |
| Consolidated billing           | AWS Organizations     |
| Quick spending overview        | Billing Dashboard     |
| Monthly service charges        | Bills                 |
| Historical cost trend          | Cost Explorer         |
| Budget target / forecast       | AWS Budgets           |
| Detailed usage records         | Cost and Usage Report |
| Early development              | Developer Support     |
| Production                     | Business Support      |
| Mission-critical               | Enterprise Support    |
| Proactive guidance             | TAM                   |
| Best-practice recommendations  | Trusted Advisor       |
| Account assistance             | Support Concierge     |

---

# 46. Common mistakes to avoid

**Pricing Calculator ≠ actual bill.**

```text
Calculator → Estimate
Bill → Actual charges
```

**TCO ≠ server purchase price only.**

```text
TCO → Direct + indirect costs
```

**Cost Explorer ≠ AWS Budgets.**

```text
Cost Explorer → Analyse
Budgets → Track against target
```

**AWS Organizations ≠ IAM.**

```text
Organizations → Accounts
IAM → Identities and permissions
```

**Free service ≠ free architecture.**

The service may use other resources that are chargeable.

**Reserved pricing ≠ automatically the best option.**

It depends on predictable usage.

**Enterprise Support ≠ “the most expensive therefore always best.”**

It is intended for business- and mission-critical use in the module.

---

# 47. What I would prioritise before the subjective exam

If time is short, master these six relationships:

```text
AWS COST
Compute + Storage + Data transfer

TCO
On-premises total cost vs AWS

Pricing Calculator
Estimate BEFORE deployment

Organizations
Multiple accounts + consolidated billing

COST TOOLS
Dashboard → Overview
Bills → Charges
Explorer → Analyse
Budgets → Track target
CUR → Detailed records

SUPPORT
Developer → Development
Business → Production
Enterprise → Mission-critical
```

   

# Final 2-minute revision

```text
PRICING PHILOSOPHY
──────────────────
Pay for what you use
Pay less when you reserve
Pay less per unit with suitable volume

Main cost drivers:
Compute
Storage
Data transfer
```

```text
TCO
───
Direct + indirect costs

Server
Storage
Network
IT labour
Space
Power
Cooling
Maintenance
```

```text
PLANNING
────────
Pricing Calculator
→ "What might this cost?"
```

```text
AWS ORGANIZATIONS
─────────────────
Multiple accounts
OUs
Central policies
Consolidated billing
```

```text
BILLING
───────
Dashboard → Overview
Bills → Charges
Explorer → Analyse
Budgets → Target
Cost & Usage Report → Detail
```

```text
SUPPORT
───────
Basic → General
Developer → Early development
Business → Production
Enterprise → Mission-critical

TAM → Guidance
Trusted Advisor → Best practices
Concierge → Account assistance
```

The central idea of Module 2 is that **cloud economics is not simply “AWS is cheap.”** It is about matching cost to actual consumption, comparing the *total* cost of alternatives, estimating before deployment, monitoring spending after deployment, and selecting the level of governance and support appropriate to the business.

</details>


<details>
<summary><strong>Module 3: AWS Global Infrastructure Overview — Subjective Exam Preparation</strong></summary>

# Module 3: AWS Global Infrastructure Overview — Subjective Exam Preparation

For a **subjective exam**, Module 3 is considerably more focused than Modules 1 and 2. The module has only two formal objectives:

1. Differentiate **AWS Regions, Availability Zones, and edge locations**.
2. Identify **AWS services and their service categories**. 

So I would concentrate most of your effort on understanding the infrastructure hierarchy, why we use multiple Availability Zones, how a Region is selected, and recognising which AWS services belong to which category.

The whole chapter can be pictured as:

```text
AWS Global Infrastructure
│
├── AWS Region
│   ├── Availability Zone
│   │   ├── Data center
│   │   └── Data center
│   │
│   └── Availability Zone
│       └── Data center
│
└── Points of Presence
    ├── Edge locations
    └── Regional edge caches
```

---

# 1. What is AWS Global Infrastructure?

AWS Global Infrastructure is the worldwide physical and networking infrastructure that AWS uses to provide cloud services.

The module describes it as being designed to provide:

* flexibility;
* reliability;
* scalability;
* security;
* high-quality global network performance. 

For the subjective exam, however, the important thing is understanding **how that infrastructure is divided**.

Think of AWS as a worldwide company.

```text
World
↓
Different geographical areas
↓
Different isolated locations
↓
Physical data centers
```

AWS gives names to those levels:

```text
Geographical area
→ Region

Isolated location within Region
→ Availability Zone

Physical building
→ Data center
```

---

# 2. AWS Region

An **AWS Region is a geographical area**.

A Region normally contains multiple Availability Zones. The module also states that communication between Regions uses AWS backbone network infrastructure, while **data replication between Regions is controlled by the customer**. 

Think of a Region as a **city or major geographical area**.

For example:

```text
AWS
└── Region
    ├── Availability Zone A
    ├── Availability Zone B
    └── Availability Zone C
```

The crucial point is:

> **A Region is NOT one data center.**

A Region is the larger geographical area containing multiple Availability Zones.

---

# 3. Why does AWS have multiple Regions?

Different customers have different requirements.

A Malaysian organisation might care about:

* where its data is legally permitted to reside;
* how far its users are from AWS;
* whether the AWS services it needs are available there;
* how much those services cost in that Region.

That leads to one of the most important subjective topics in this module.

---

# 4. How to choose an AWS Region

The module gives **four factors** for selecting a Region:

1. Data governance and legal requirements
2. Proximity to customers / latency
3. Services available in the Region
4. Costs, which can vary by Region 

I would remember these as:

```text
C → Compliance
L → Latency
A → Availability of services
C → Cost
```

Or simply ask:

> **Legal? Distance? Service? Price?**

---

# 5. Factor 1 — Data governance and legal requirements

Suppose a government organisation has a rule:

> Customer data must remain within a particular geographical jurisdiction.

Even if another Region is:

* cheaper;
* faster;
* technically better;

the organisation may still need to choose the legally compliant Region.

### Good subjective answer

> Data governance and legal requirements are important when selecting an AWS Region because regulations may require an organisation to store or process data in a particular geographic location. Therefore, an organisation must ensure that its selected Region satisfies relevant legal and compliance requirements.

### Scenario clue

> “The company is legally required to keep customer data within a particular country.”

Think:

**Data governance / legal requirements**

Not “choose the closest Region because latency is lower.” Breaking the law slightly faster is not much of an optimisation.

---

# 6. Factor 2 — Proximity to customers

Distance can affect **latency**.

Latency means delay.

If most users are very far from the application's Region:

```text
User
↓
Long network distance
↓
Application
```

the response may take longer.

Placing resources closer to customers can reduce latency.

### Good answer

> Customer proximity should be considered when selecting a Region because a Region closer to users can reduce network latency and improve application response time.

### Scenario clue

> “A company wants to reduce response time experienced by customers.”

Think:

**Choose a Region closer to the customers.**

---

# 7. Factor 3 — Service availability

Not every AWS service or feature is necessarily available in every Region.

Therefore:

```text
Need Service X
↓
Check whether Region supports Service X
↓
Then select suitable Region
```

### Good answer

> Organisations must verify that the AWS services required by their application are available in the selected Region. A geographically suitable Region would still be inappropriate if it does not provide a required service.

---

# 8. Factor 4 — Cost

AWS service prices may vary between Regions.

So organisations can consider the cost of running their workload in different Regions.

### Good answer

> AWS pricing may vary between Regions, so organisations should also evaluate the cost of running their required services in each suitable Region after considering requirements such as compliance, latency and service availability.

Notice that cost isn't automatically the first consideration.

If one Region costs $5 less but violates the company's legal requirements, that $5 saving is unlikely to impress the regulator.

---

# 9. Full subjective answer — Selecting a Region

If you get:

> **Explain the factors that should be considered when choosing an AWS Region.**

You can write:

> An organisation should consider four main factors when selecting an AWS Region. First, data governance and legal requirements must be considered because some data may be required to remain within a particular geographical location. Second, proximity to customers affects latency, so resources closer to users may improve response times. Third, the organisation must ensure that all required AWS services are available in the selected Region. Finally, AWS service costs may vary between Regions, so pricing should also be evaluated.

That is a strong full answer directly aligned with the module.

---

# 10. Availability Zone

An **Availability Zone**, usually shortened to **AZ**, is a fully isolated partition of AWS infrastructure within a Region.

The module states that:

* each Region contains multiple AZs;
* AZs consist of discrete data centers;
* they are designed for fault isolation;
* AZs connect to one another through high-speed private networking;
* AWS recommends replicating data and resources across AZs for resiliency. 

Think:

```text
Region
├── AZ A
├── AZ B
└── AZ C
```

Each AZ is separated so that a problem affecting one location does not necessarily affect the others.

---

# 11. Why Availability Zones matter

Imagine an online shop running only in:

```text
Availability Zone A
└── Web server
```

If AZ A has a major failure:

```text
AZ A unavailable
↓
Application unavailable
```

Now imagine:

```text
Region
├── AZ A → Application server
└── AZ B → Application server
```

If one AZ fails:

```text
AZ A ✕
AZ B ✓
```

the second location can continue supporting the workload, depending on how the application has been designed.

So the main idea is:

> **Multiple AZs reduce dependence on one physical location.**

---

# 12. Good subjective answer — Availability Zone

> An Availability Zone is an isolated partition of AWS infrastructure within an AWS Region and consists of one or more discrete data centers. Availability Zones are physically separated for fault isolation but are connected using high-speed private networking. Deploying resources across multiple Availability Zones improves resiliency because an application is less dependent on one physical location.

---

# 13. Multiple servers ≠ automatically Multi-AZ

Suppose:

```text
AZ A
├── Server 1
└── Server 2
```

You have two servers.

Does this protect against **AZ failure**?

No.

Both servers still depend on AZ A.

To protect against an AZ-level failure:

```text
AZ A
└── Server 1

AZ B
└── Server 2
```

This distinction is worth remembering.

---

# 14. Data center

A **data center** is the actual physical facility where:

* data resides;
* data processing occurs.

The module states that each data center has redundant:

* power;
* networking;
* connectivity;

and is housed in a separate facility. 

The hierarchy is therefore:

```text
REGION
  ↓
AVAILABILITY ZONE
  ↓
DATA CENTER
```

Not:

```text
Region = data center
```

That is one of the easiest ways to lose marks unnecessarily.

---

# 15. Region vs AZ vs data center

| Component             | Meaning                                           |
| --------------------- | ------------------------------------------------- |
| **Region**            | Geographical area                                 |
| **Availability Zone** | Isolated infrastructure partition within a Region |
| **Data center**       | Physical facility containing the infrastructure   |

Memory:

```text
Region → Area
AZ → Isolated location
Data center → Physical building
```

---

# 16. Edge locations

The next infrastructure component is very different.

An **edge location** is primarily used to place content closer to users.

It is associated in this module with **Amazon CloudFront**, AWS's Content Delivery Network.

Page 11 explains that AWS Points of Presence include edge locations and Regional edge caches and that CloudFront uses them to deliver content to end users with reduced latency. 

---

# 17. Why edge locations exist

Suppose the original website content is far away from the customer.

Without caching:

```text
Malaysian user
↓
Long network journey
↓
Original server
↓
Image returned
```

If the same image is cached closer to the customer:

```text
Malaysian user
↓
Nearby edge location
↓
Cached image returned
```

The content does not need to travel from the distant origin every time.

The result:

> **Reduced latency.**

---

# 18. Edge location vs Availability Zone

This is a major confusion.

An **Availability Zone** exists primarily to provide isolated infrastructure inside a Region.

An **edge location** exists primarily to deliver cached content closer to users.

```text
Availability Zone
→ Run infrastructure
→ Fault isolation

Edge location
→ Cache/deliver content
→ Lower latency
```

Do not write:

> “An edge location is another Availability Zone closer to users.”

It isn't.

---

# 19. Regional edge cache

The module also introduces **Regional edge caches**.

They are part of AWS Points of Presence and are used for content that is accessed less frequently. 

Conceptually:

```text
User
 ↓
Edge location
 ↓
Regional edge cache
 ↓
Original content
```

Think of the Regional edge cache as a larger intermediate cache between the normal edge location and the origin.

For most subjective questions, however, the more important concept is:

```text
Edge location
→ Content close to user

CloudFront
→ Uses edge locations
```

---

# 20. Points of Presence

AWS **Points of Presence** consist of:

```text
Edge locations
+
Regional edge caches
```

The module explicitly separates these from Regions and Availability Zones. 

So:

```text
AWS GLOBAL INFRASTRUCTURE

Regions
└── Availability Zones
    └── Data centers

Points of Presence
├── Edge locations
└── Regional edge caches
```

---

# 21. Good subjective answer — Edge location

> An edge location is part of AWS's global Points of Presence and is used by services such as Amazon CloudFront to cache and deliver content closer to end users. By serving cached content from a nearby location instead of repeatedly retrieving it from a distant origin, edge locations can reduce latency and improve application performance.

---

# 22. Region vs AZ vs edge location

This is probably **the most important comparison in the entire module**.

| Component             | Main meaning                          | Main reason                |
| --------------------- | ------------------------------------- | -------------------------- |
| **Region**            | Geographical area                     | Choose geographic location |
| **Availability Zone** | Isolated infrastructure within Region | Resilience/fault isolation |
| **Edge location**     | Content-delivery point near users     | Reduce latency             |

Memory:

```text
REGION
→ Where?

AZ
→ Survive failure?

EDGE
→ Faster delivery?
```

If you can answer those three questions, you understand the core of Module 3.

---

# 23. Infrastructure features

The module also introduces four related characteristics:

```text
Elasticity
Scalability
Fault tolerance
High availability
```

These terms sound similar if they are memorised badly, which is presumably why AWS put all four on the same slide.

---

# 24. Elasticity

**Elasticity** means dynamically adapting capacity according to current demand. 

Example:

```text
Morning:
2 servers

Sale starts:
10 servers

Sale ends:
2 servers
```

Capacity goes **up and down**.

### Good answer

> Elasticity is the ability of infrastructure to dynamically adjust capacity according to changes in demand. Resources can be added when demand increases and reduced when demand decreases.

### Scenario clue

> “Automatically increases during peak demand and decreases afterward.”

**Elasticity**

---

# 25. Scalability

**Scalability** means the infrastructure can adapt to accommodate growth. 

Example:

```text
Year 1 → 10,000 customers
Year 3 → 100,000 customers
Year 5 → 1,000,000 customers
```

The architecture can continue growing.

### Good answer

> Scalability is the ability of a system to increase its capacity so that it can accommodate growth in workload or users.

---

# 26. Elasticity vs scalability

This distinction matters.

```text
SCALABILITY
→ Can the system grow?

ELASTICITY
→ Can capacity expand AND contract with changing demand?
```

A scalable application can become larger.

An elastic application dynamically adjusts to demand.

### Example

Company grows permanently from:

```text
10,000 → 1,000,000 users
```

Think **scalability**.

Traffic rises at lunchtime and falls at night:

```text
2 → 10 → 2 servers
```

Think **elasticity**.

---

# 27. Fault tolerance

The module defines **fault tolerance** as the ability to continue operating properly when a failure occurs, supported by built-in redundancy. 

Example:

```text
Server A fails ✕

Server B continues ✓
```

### Good answer

> Fault tolerance is the ability of a system to continue operating properly even when one of its components fails. It usually depends on redundant components so that another component can continue the workload.

---

# 28. High availability

**High availability** aims to maintain a high level of operational performance while minimising downtime. 

Think:

```text
High availability
=
Keep service available
+
Minimise downtime
```

Using resources across multiple Availability Zones is one way of supporting high availability.

### Good answer

> High availability refers to designing a system to maintain a high level of operational performance while minimising downtime. AWS architectures can improve availability by avoiding dependence on a single infrastructure location, for example by deploying resources across multiple Availability Zones.

---

# 29. Fault tolerance vs high availability

A useful subjective distinction:

```text
Fault tolerance
→ Continue despite failure

High availability
→ Minimise downtime
```

They are related, but not identical.

If a system is fault tolerant, the goal is for failure of a component not to stop the service.

With high availability, the goal is to keep downtime as low as possible.

---

# 30. All four infrastructure terms

| Term                  | Think                   |
| --------------------- | ----------------------- |
| **Elasticity**        | Up AND down with demand |
| **Scalability**       | Grow                    |
| **Fault tolerance**   | Survive failure         |
| **High availability** | Minimise downtime       |

Memorise:

```text
Elasticity → Adjust
Scalability → Grow
Fault tolerance → Survive
High availability → Stay available
```

---

# 31. Regional vs global resources

The Management Console activity in Module 3 specifically asks students to distinguish Regional and global services and to identify the scope of VPCs and subnets. 

For the examples used in that activity:

```text
Amazon EC2 → Regional
AWS Lambda → Regional

IAM → Global
Route 53 → Global
```

Also:

```text
VPC → Region level
Subnet → Availability Zone level
```

---

# 32. VPC and subnet scope

You do not need Module 5's networking details yet.

For Module 3, just know:

```text
Region
└── VPC
    ├── Subnet in AZ A
    └── Subnet in AZ B
```

Therefore:

> **A VPC exists at the Region level.**

> **A subnet exists at the Availability Zone level.** 

---

# 33. Section 2 — AWS service categories

The second half of Module 3 is largely a **classification exercise**.

The module is not yet asking you to explain the detailed configuration of every service. Later modules do that.

For Module 3, the important skill is:

> **Recognise what category a service belongs to.**

The categories presented include:

```text
Compute
Storage
Database
Networking and Content Delivery
Security, Identity, and Compliance
AWS Cost Management
Management and Governance
```

  

---

# 34. Compute category

Think:

> **Run applications and processing.**

Important examples shown across the course/module category material include:

```text
Amazon EC2
Amazon EC2 Auto Scaling
Amazon ECS
Amazon EKS
AWS Fargate
AWS Lambda
AWS Elastic Beanstalk
```

For Module 3, don't waste time writing a miniature dissertation on each one.

If a question asks:

> “Which category does AWS Lambda belong to?”

Answer:

**Compute**

---

# 35. Storage category

The Module 3 slide explicitly groups:

```text
Amazon EBS
Amazon EFS
Amazon S3
Amazon S3 Glacier
```

under storage. 

Memory:

```text
EBS
EFS
S3
Glacier
→ STORAGE
```

---

# 36. Database category

The module groups:

```text
Amazon RDS
Amazon Aurora
Amazon DynamoDB
Amazon Redshift
```

under Database. 

Memory:

```text
RDS
Aurora
DynamoDB
Redshift
→ DATABASE
```

---

# 37. Networking and Content Delivery

The module groups these services together:

```text
Amazon VPC
Elastic Load Balancing
AWS Direct Connect
AWS VPN
AWS Transit Gateway
Amazon Route 53
Amazon CloudFront
```



For Module 3:

```text
VPC
Route 53
CloudFront
Direct Connect
etc.
→ NETWORKING AND CONTENT DELIVERY
```

---

# 38. Security, Identity and Compliance

The module groups:

```text
AWS IAM
AWS Organizations
Amazon Cognito
AWS Artifact
AWS KMS
AWS Shield
```

under **Security, Identity, and Compliance**. 

Memory:

```text
IAM
Organizations
Cognito
KMS
Shield
Artifact
→ SECURITY
```

---

# 39. AWS Cost Management

The module groups:

```text
AWS Cost and Usage Report
AWS Budgets
AWS Cost Explorer
```

under **AWS Cost Management**. 

This one should already look familiar from Module 2.

```text
Budgets
Cost Explorer
Cost and Usage Report
→ COST MANAGEMENT
```

---

# 40. Management and Governance

The module groups services/tools such as:

```text
AWS Management Console
AWS Config
Amazon CloudWatch
AWS Auto Scaling
AWS CLI
AWS Trusted Advisor
AWS Well-Architected Tool
AWS CloudTrail
```

under **Management and Governance**. 

The most dangerous category confusions tend to be:

```text
CloudWatch → Management and Governance
CloudTrail → Management and Governance
Trusted Advisor → Management and Governance

Cost Explorer → Cost Management

CloudFront → Networking and Content Delivery

Artifact → Security, Identity and Compliance
```

---

# 41. Service-category table to memorise

| Category                            | High-priority examples                                                                             |
| ----------------------------------- | -------------------------------------------------------------------------------------------------- |
| **Compute**                         | EC2, Lambda, ECS, EKS, Fargate, Elastic Beanstalk                                                  |
| **Storage**                         | S3, S3 Glacier, EBS, EFS                                                                           |
| **Database**                        | RDS, Aurora, DynamoDB, Redshift                                                                    |
| **Networking & Content Delivery**   | VPC, ELB, Direct Connect, VPN, Transit Gateway, Route 53, CloudFront                               |
| **Security, Identity & Compliance** | IAM, Organizations, Cognito, KMS, Shield, Artifact                                                 |
| **Cost Management**                 | Budgets, Cost Explorer, Cost and Usage Report                                                      |
| **Management & Governance**         | Console, CLI, CloudWatch, CloudTrail, Config, Trusted Advisor, Well-Architected Tool, Auto Scaling |

For subjective questions, explain the category's **purpose**, then provide examples.

---

# 42. Likely subjective question — Explain AWS Global Infrastructure

A good answer:

> AWS Global Infrastructure is designed to provide a flexible, reliable, scalable and secure cloud environment. It is organised into geographical AWS Regions, each of which contains multiple isolated Availability Zones consisting of data centers. Availability Zones are physically separated to support fault isolation and resiliency. AWS also operates Points of Presence, including edge locations and Regional edge caches, which are used by services such as Amazon CloudFront to deliver cached content closer to users and reduce latency.

---

# 43. Likely subjective question — Region vs Availability Zone vs edge location

> An AWS Region is a geographical area that normally contains multiple Availability Zones. An Availability Zone is an isolated infrastructure partition within a Region and consists of discrete data centers, making it useful for fault isolation and resiliency. An edge location is different because it is part of AWS Points of Presence and is used to cache and deliver content closer to end users, primarily to reduce latency.

---

# 44. Likely subjective question — Why deploy across multiple AZs?

> Deploying resources across multiple Availability Zones improves resiliency because the application is not dependent on only one isolated infrastructure location. If one Availability Zone becomes unavailable, resources in another Availability Zone can continue supporting the application, provided the workload has been designed appropriately.

---

# 45. Likely subjective question — Explain edge locations

> Edge locations are AWS Points of Presence positioned closer to end users. Amazon CloudFront uses edge locations to cache and deliver content so that users do not always need to retrieve the content from a distant origin. This reduces network latency and improves content-delivery performance.

---

# 46. Likely subjective question — Differentiate elasticity and scalability

> Scalability is the ability of an infrastructure to grow so that it can accommodate increasing demand. Elasticity is the ability to dynamically adjust capacity according to current demand, including both increasing and decreasing resources. Therefore, scalability focuses on the ability to grow, while elasticity focuses on dynamically matching capacity to workload changes.

---

# 47. Likely subjective question — Fault tolerance vs high availability

> Fault tolerance refers to the ability of a system to continue operating properly even when a component fails, usually through redundant components. High availability focuses on maintaining a high level of operational performance while minimising downtime. Both improve reliability, but fault tolerance emphasises continued operation after failure whereas high availability emphasises keeping downtime low.

---

# 48. How to answer a scenario question

As with Modules 1 and 2:

```text
1. Identify the concept.
2. Explain it.
3. Connect it to the scenario.
```

Example:

> An ecommerce company runs its application entirely in one Availability Zone. Management is concerned that failure of the location could make the website unavailable. Recommend an improvement.

Weak:

> Use multiple Availability Zones.

Better:

> The company should distribute its application resources across multiple Availability Zones. Availability Zones are physically isolated infrastructure partitions within a Region, so using more than one AZ reduces dependence on a single location. If one Availability Zone fails, resources in another AZ can continue supporting the workload, improving resiliency and availability.

The second answer tells the examiner that you actually know *why* the answer works.

---

# 49. High-priority scenario clues

| If the question says...                 | Think...                               |
| --------------------------------------- | -------------------------------------- |
| Geographical AWS area                   | Region                                 |
| Multiple AZs                            | Region                                 |
| Isolated infrastructure                 | Availability Zone                      |
| Protect against location/AZ failure     | Multiple AZs                           |
| Physical AWS facility                   | Data center                            |
| Content closer to users                 | Edge location                          |
| CloudFront caching                      | Edge location                          |
| Less frequently accessed cached content | Regional edge cache                    |
| Legal/data residency                    | Region selection: governance           |
| Reduce customer latency                 | Region selection: proximity            |
| Required AWS service not available      | Region selection: service availability |
| Different price by location             | Region selection: cost                 |
| Capacity rises and falls                | Elasticity                             |
| System grows substantially              | Scalability                            |
| Continue after failure                  | Fault tolerance                        |
| Minimise downtime                       | High availability                      |
| VPC scope                               | Region                                 |
| Subnet scope                            | Availability Zone                      |
| IAM / Route 53                          | Global services in module activity     |
| EC2 / Lambda                            | Regional services in module activity   |

---

# 50. Common mistakes to avoid

**Region ≠ Availability Zone.**

```text
Region
contains
Availability Zones
```

**Availability Zone ≠ data center.**

An AZ consists of discrete data centers.

**Edge location ≠ Availability Zone.**

```text
AZ → Infrastructure / resilience
Edge → Content delivery / latency
```

**Two servers in one AZ ≠ Multi-AZ.**

Both still depend on the same AZ.

**Multiple AZs ≠ multiple Regions.**

```text
Multi-AZ
→ Several isolated locations inside one Region

Multi-Region
→ Several geographical Regions
```

**Closest Region ≠ automatically the best Region.**

Compliance, service availability and cost also matter.

**Elasticity ≠ scalability.**

```text
Elasticity → Up and down
Scalability → Grow
```

**CloudFront ≠ an Availability Zone.**

CloudFront uses edge infrastructure to deliver content.

---

# 51. What I would prioritise for the subjective exam

If time is short, master these **five things**:

```text
1. Region vs AZ vs data center vs edge location

2. Region-selection factors
   - Legal/governance
   - Customer proximity
   - Service availability
   - Cost

3. Why multiple AZs improve resilience

4. Elasticity vs scalability
   Fault tolerance vs high availability

5. AWS service categories
```

That covers almost the entire intellectual substance of Module 3 because the module itself only has two formal objectives. 

# Final 2-minute revision

```text
AWS INFRASTRUCTURE
──────────────────
Region
→ Geographical area

Availability Zone
→ Isolated infrastructure inside Region

Data center
→ Physical facility

Edge location
→ Cached content near users

Regional edge cache
→ Intermediate cache for less-frequent content
```

```text
CHOOSE A REGION
───────────────
Compliance / legal
Latency / customer proximity
Available AWS services
Cost
```

```text
RESILIENCE
──────────
Multiple AZs
→ Reduce dependence on one location
```

```text
INFRASTRUCTURE FEATURES
───────────────────────
Elasticity
→ Adjust up/down

Scalability
→ Grow

Fault tolerance
→ Continue after failure

High availability
→ Minimise downtime
```

```text
RESOURCE SCOPE
──────────────
VPC → Region
Subnet → Availability Zone

EC2 / Lambda → Regional
IAM / Route 53 → Global
```

```text
SERVICE CATEGORIES
──────────────────
EC2 / Lambda → Compute
S3 / EBS / EFS → Storage
RDS / DynamoDB → Database
VPC / Route 53 / CloudFront → Networking
IAM / KMS / Shield → Security
Budgets / Cost Explorer → Cost Management
CloudWatch / CloudTrail → Management & Governance
```

The **single most important mental model** for Module 3 is:

```text
REGION
→ Where should my workload be geographically?

AVAILABILITY ZONE
→ How do I reduce dependence on one location?

EDGE LOCATION
→ How do I deliver content closer to users?
```

If those three distinctions are completely clear, the most confusing part of Module 3 is already dealt with. 

</details>


<details>
<summary><strong> Module 4: AWS Cloud Security — Subjective Exam Preparation </strong></summary>

For a **subjective exam**, Module 4 is one of the chapters where simply memorising service names is not enough. You need to understand **who is responsible for security, how AWS permissions work, how accounts are protected, how data is encrypted, and which services support security and compliance**.

The module expects you to recognise eight areas: the shared responsibility model, AWS vs customer responsibilities, IAM users/groups/roles, IAM credentials, securing a new AWS account, IAM users and groups, securing AWS data, and AWS compliance programs. 

The chapter can be remembered as one security story:

```text
WHO protects what?
        ↓
WHO can access AWS?
        ↓
WHAT are they allowed to do?
        ↓
HOW do we protect the account?
        ↓
HOW do we protect data?
        ↓
HOW do we check security and compliance?
```

---

# 1. The most important concept: Shared Responsibility Model

The central security rule is:

```text
AWS      → Security OF the cloud
Customer → Security IN the cloud
```

The diagram on page 5 divides responsibility exactly this way. AWS protects the underlying infrastructure, while the customer protects what they configure and place inside AWS. 

An easy analogy is renting an office.

The building owner is responsible for:

```text
Physical building
Power
Elevators
Building security
Structural maintenance
```

But the tenant is responsible for:

```text
Who receives office keys
What files are stored
Employee access
Computer configuration
Locking the office
```

AWS works similarly.

---

# 2. AWS responsibility: Security **of** the cloud

According to the module, AWS is responsible for areas such as:

* physical security of data centres;
* hardware and software infrastructure;
* network infrastructure;
* virtualisation infrastructure;
* instance isolation;
* storage decommissioning;
* infrastructure access logging and auditing. 

So if something belongs to the **underlying AWS infrastructure**, it is generally AWS's responsibility.

### Good subjective answer

> Under the AWS Shared Responsibility Model, AWS is responsible for security **of the cloud**. This includes protecting the physical data centres, hardware, networking infrastructure, virtualisation layer and the underlying infrastructure that supports AWS services. AWS also provides isolation between customers and manages physical infrastructure security.

---

# 3. Customer responsibility: Security **in** the cloud

The module places responsibility on the customer for things such as:

* customer data;
* applications;
* IAM permissions;
* EC2 operating-system patches;
* passwords;
* security groups;
* host firewalls;
* network configuration;
* account management;
* user login and permission settings. 

So if the question is about something the customer **configures**, that is usually customer responsibility.

### Good answer

> The customer is responsible for security **in the cloud**. This includes protecting customer data, configuring IAM access, securing applications, managing EC2 guest operating systems, applying patches, configuring security groups and managing user permissions.

---

# 4. AWS vs customer — quick decision rule

Ask:

```text
Is it physical or underlying AWS infrastructure?
→ AWS

Is it customer data, configuration, identities or software?
→ Customer
```

Examples:

| Question                        | Responsibility |
| ------------------------------- | -------------- |
| Physical data-centre security   | AWS            |
| Virtualisation infrastructure   | AWS            |
| Isolation between AWS customers | AWS            |
| EC2 guest OS patching           | Customer       |
| EC2 security-group rules        | Customer       |
| S3 bucket permissions           | Customer       |
| IAM users and permissions       | Customer       |
| Application configuration       | Customer       |

---

# 5. Responsibility changes depending on the service

This is important.

The module explains that the amount of security work the customer performs changes according to whether the service behaves more like **IaaS, PaaS or SaaS**. 

Think:

```text
More customer control
→ More customer security responsibility

More AWS management
→ More AWS security responsibility
```

---

# 6. IaaS security responsibility

For Infrastructure as a Service, such as EC2, the customer manages more.

The module gives examples including:

```text
Amazon EC2
Amazon EBS
Amazon VPC
```

The customer may need to manage:

```text
Guest operating system
Patches
Network settings
Firewall/security groups
Applications
Access control
```

### Scenario

> An EC2 instance is running an outdated Linux operating system.

Who is responsible?

**Customer.**

Because the customer manages the EC2 guest operating system.

---

# 7. PaaS security responsibility

The module gives examples such as:

```text
Amazon RDS
AWS Elastic Beanstalk
AWS Lambda
```

AWS manages more of the underlying platform.

For example, with a managed database service, AWS may handle more of:

```text
Operating system
Database patching
Underlying infrastructure
Recovery mechanisms
```

while the customer focuses more on:

```text
Data
Users
Permissions
Application code
```

### Important comparison

If Oracle runs on:

```text
EC2
→ Customer handles Oracle and OS patching
```

If Oracle runs through:

```text
Amazon RDS
→ AWS manages more of the platform and patching
```

The module explicitly uses this kind of distinction in its shared responsibility activity. 

---

# 8. Likely subjective question — Shared responsibility

> Explain the AWS Shared Responsibility Model.

A strong answer:

> The AWS Shared Responsibility Model divides security responsibilities between AWS and the customer. AWS is responsible for security **of the cloud**, which includes the physical data centres, hardware, networking and virtualisation infrastructure. The customer is responsible for security **in the cloud**, including customer data, IAM permissions, applications, operating-system configuration, security groups and network settings. The exact division of responsibility depends on the AWS service being used because customers manage more when using IaaS services such as EC2 and less when using more managed services.

---

# 9. AWS Identity and Access Management

The next huge topic is **IAM**.

IAM is used to control access to AWS resources.

The module describes IAM as providing fine-grained control over:

```text
Who can access a resource
Which resources they can access
What they can do
How they can access them
```

IAM is also described as a no-cost AWS account feature. 

The easiest way to think about IAM is:

> **Who are you, and what are you allowed to do?**

---

# 10. Authentication vs authorisation

These two words are easy to confuse.

## Authentication

Asks:

> **Who are you?**

Examples:

```text
Username + password
Access key
MFA code
```

## Authorisation

Asks:

> **What are you allowed to do?**

Examples:

```text
Can read S3
Can start EC2
Cannot terminate EC2
```

Memory:

```text
Authentication → Identity
Authorisation  → Permission
```

---

# 11. IAM user

An **IAM user** represents a person or application that can authenticate to an AWS account. 

A user may receive:

```text
Console login credentials
or
Programmatic credentials
```

Think of an IAM user as:

> **A named identity.**

Example:

```text
Aisyah
Developer01
FinanceUser
```

---

# 12. IAM group

An **IAM group** is a collection of IAM users that need the same permissions. 

Example:

```text
Developers group
├── Ali
├── Sarah
└── Mei
```

Instead of attaching the same policy separately to all three users:

```text
Policy
↓
Developers group
↓
All users inherit permissions
```

Important:

```text
Groups contain users
Users can belong to multiple groups
Groups do NOT contain other groups
```

---

# 13. IAM policy

An **IAM policy** is the document that defines permissions.

The module explains that policies support fine-grained access and may be:

```text
Identity-based
Resource-based
```



A policy defines things such as:

```text
Effect → Allow or Deny
Action → What may be done
Resource → What resource it applies to
```

Conceptually:

```text
Allow
s3:GetObject
on
ProjectBucket
```

means:

> Allow reading objects from that bucket.

---

# 14. Identity-based vs resource-based policy

## Identity-based policy

Attached to:

```text
IAM user
IAM group
IAM role
```

It answers:

> **What may this identity do?**

## Resource-based policy

Attached directly to a resource.

Example:

```text
S3 bucket policy
```

It answers:

> **Who can access this resource and what may they do?**

The module explicitly distinguishes these two policy types. 

---

# 15. IAM role

An **IAM role** provides a set of permissions for making AWS service requests. 

The key idea is:

> A role is **assumed**, rather than permanently tied to one user.

Roles can be used by:

```text
AWS services
Users
Applications
Other AWS accounts
```

and commonly provide **temporary credentials**.

Example:

```text
EC2
↓ assumes role
IAM role
↓ grants
Permission to read S3
```

This is safer than embedding permanent credentials in the application.

---

# 16. User vs group vs policy vs role

Memorise this:

| IAM component | Think                 |
| ------------- | --------------------- |
| **User**      | Identity              |
| **Group**     | Collection of users   |
| **Policy**    | Permission rules      |
| **Role**      | Assumable permissions |

Or even shorter:

```text
User   → Who
Group  → Team
Policy → Rules
Role   → Temporary job
```

---

# 17. IAM security credentials

The module separates console access from programmatic access.

## Console access

Authentication can use:

```text
12-digit AWS Account ID or alias
IAM username
Password
MFA code if enabled
```

## Programmatic access

The module shows credentials including:

```text
Access key ID
Secret access key
```

used for AWS CLI and SDK access. 

---

# 18. Multi-factor authentication

**MFA** adds another authentication factor.

Instead of only:

```text
Username
+
Password
```

it requires:

```text
Username
+
Password
+
Authentication code
```

The module states that MFA increases security because a password alone is no longer enough. 

### Good answer

> Multi-factor authentication improves account security by requiring an additional authentication code in addition to the username and password. Therefore, possession of a password alone is insufficient to access the account.

---

# 19. IAM permission evaluation

This is one of the most important exam rules in Module 4.

By default:

> **All permissions are implicitly denied.**

If a policy explicitly allows something, it may become allowed.

If a policy explicitly denies something:

> **The explicit deny wins.**

The module's IAM policy example makes this rule very clear. 

Memory:

```text
Explicit Deny
>
Explicit Allow
>
Implicit Deny
```

---

# 20. Example of permission evaluation

Suppose:

```text
Policy A:
Allow S3 access
```

and another policy says:

```text
Policy B:
Deny s3:DeleteObject
```

The user may be able to read S3 objects, but cannot delete them.

Why?

Because:

```text
Explicit Deny wins
```

---

# 21. Principle of least privilege

The module identifies **least privilege** as an IAM best practice. 

It means:

> Give a user only the permissions necessary to perform their job.

Example:

A developer only needs to view EC2 instances.

Bad approach:

```text
AdministratorAccess
```

Better approach:

```text
Only required EC2 read permissions
```

### Good answer

> The principle of least privilege means granting users or roles only the minimum permissions required to complete their tasks. This reduces the potential impact of mistakes, compromised credentials or misuse.

---

# 22. Likely subjective question — IAM components

> Differentiate IAM users, groups, policies and roles.

Strong answer:

> An IAM user represents an individual person or application that can authenticate to AWS. An IAM group is a collection of users that require similar permissions. An IAM policy is a permission document that defines which AWS actions and resources are allowed or denied. An IAM role contains permissions that can be assumed temporarily by users, applications or AWS services rather than being permanently associated with one identity.

---

# 23. Securing a new AWS account

A newly created AWS account begins with a **root user**.

The root user has extremely powerful access.

Therefore, it should not be used for everyday administration.

The module recommends creating an administrative IAM identity for routine work and protecting root access carefully. 

---

# 24. Root user vs IAM user

Think:

```text
Root user
→ Master key

IAM user
→ Normal employee key
```

The root user can perform highly sensitive account tasks.

The module includes examples such as changing the AWS Support plan. 

### Exam rule

> Do not use the root user for ordinary daily tasks.

---

# 25. Account-security steps

A useful sequence based on the module is:

```text
Protect root credentials
↓
Create administrative IAM identity
↓
Enable MFA
↓
Create individual identities
↓
Use groups and policies
↓
Apply least privilege
↓
Use roles where appropriate
↓
Monitor account activity
```

The exact order is less important than understanding the logic.

---

# 26. Individual users instead of shared accounts

Do not create:

```text
username: ITTeam
password: sharedpassword123
```

for ten employees.

Why?

Because then:

```text
Who performed the action?
→ Nobody knows precisely
```

Individual identities improve:

* accountability;
* auditing;
* access removal;
* permission management.

This is an important security principle for subjective explanation.

---

# 27. AWS CloudTrail

**AWS CloudTrail** records user activity and API requests in an AWS account.

The key question it answers is:

> **Who did what?**

Example:

> “Who changed the S3 bucket policy?”

Use:

**CloudTrail**

The module specifically uses account-activity recording as a security control. 

Memory:

```text
CloudTrail
→ Activity trail
→ Who performed the API action?
```

---

# 28. AWS Organizations and service control policies

The module's securing-accounts material also introduces centrally managing multiple AWS accounts.

Think:

```text
AWS Organizations
→ Manage multiple AWS accounts
```

A **Service Control Policy**, or SCP, can set organisation-level permission boundaries.

The key distinction:

```text
SCP
→ Limits what can be permitted

IAM
→ Grants permissions to identities
```

So:

> An SCP does not automatically grant access.

If the SCP allows something but IAM does not:

```text
Still denied
```

---

# 29. Security services you should recognise

Module 4 includes several services that solve very different problems.

| Requirement                     | AWS service       |
| ------------------------------- | ----------------- |
| Manage encryption keys          | AWS KMS           |
| Authenticate application users  | Amazon Cognito    |
| DDoS protection                 | AWS Shield        |
| Record API activity             | AWS CloudTrail    |
| Manage multiple accounts        | AWS Organizations |
| Evaluate resource configuration | AWS Config        |
| Access compliance reports       | AWS Artifact      |

These distinctions are very exam-friendly because the service names themselves are not especially helpful.

---

# 30. AWS Key Management Service

**AWS KMS** is used to create and manage encryption keys.

Think:

```text
Data
↓ encryption key
Encrypted data
```

KMS helps control access to and usage of encryption keys.

### Scenario

> “The company needs central management of encryption keys.”

**AWS KMS**

---

# 31. Amazon Cognito

**Amazon Cognito** is used for authentication and access control for users of applications.

Think:

```text
Customer signs up
↓
Customer signs in
↓
Application authenticates customer
```

This is different from IAM.

```text
IAM
→ AWS administrators, identities and services

Cognito
→ End users of applications
```

### Scenario

> “Millions of customers need to sign into a mobile application.”

**Amazon Cognito**

---

# 32. AWS Shield

**AWS Shield** helps protect applications against **Distributed Denial-of-Service (DDoS)** attacks.

A DDoS attack attempts to overwhelm a service with large amounts of traffic.

```text
Huge malicious traffic
↓
Application
↓
Potential disruption
```

The module distinguishes Shield Standard and Shield Advanced, with Shield Standard available without an additional charge in the teaching material. 

### Scenario

> “The company wants protection against DDoS attacks.”

**AWS Shield**

---

# 33. Protecting data: at rest vs in transit

This is another major subjective topic.

Data exists in two important states:

```text
Data at rest
Data in transit
```



---

# 34. Encryption at rest

**Data at rest** means stored data.

Examples:

```text
Object stored in S3
File stored in EFS
Data stored in EBS
Database record stored in RDS
```

The purpose of encryption is to make the stored information unreadable without the appropriate encryption key.

Think:

```text
Stored data
→ Encrypt
→ Ciphertext
```

AWS KMS can help manage encryption keys.

---

# 35. Encryption in transit

**Data in transit** means data moving across a network.

Examples:

```text
Browser → Website
EC2 → EFS
Application → Database
On-premises → S3
```

The module mentions protections such as:

```text
TLS
HTTPS
Certificates
```



Memory:

```text
At rest
→ Stored

In transit
→ Moving
```

---

# 36. At-rest vs in-transit answer

> Encryption at rest protects data while it is stored on media such as EBS, S3 or database storage. Encryption in transit protects data while it is moving across a network, for example between a browser and a web application, and commonly uses technologies such as TLS or HTTPS. Both forms of encryption are required because protecting stored data does not automatically protect network traffic.

---

# 37. Securing Amazon S3

The module discusses protecting S3 access through several mechanisms, including:

* S3 Block Public Access;
* IAM policies;
* bucket policies;
* encryption;
* access control lists. 

The most intuitive distinction:

```text
IAM policy
→ Permission attached to identity

Bucket policy
→ Permission attached to bucket

Block Public Access
→ Helps prevent unintended public access
```

---

# 38. S3 Block Public Access

If the question says:

> “The company wants to prevent an S3 bucket from accidentally becoming public.”

Think:

**S3 Block Public Access**

This is a classic scenario clue. 

---

# 39. Compliance does not mean AWS does everything for you

The compliance section is easy to misunderstand.

AWS can provide:

```text
Compliance programs
Security controls
Audit information
Certifications
Reports
```

But the customer must still configure its workload appropriately.

Running something on AWS does **not automatically make the workload compliant**.

That would be convenient, but unfortunately auditors have yet to accept “it's in the cloud” as an entire compliance strategy.

---

# 40. AWS compliance program categories

The module groups AWS compliance programs into three broad categories:

1. **Certifications and attestations**
2. **Laws, regulations and privacy**
3. **Alignments and frameworks** 

Examples in the module include ISO certifications, GDPR, HIPAA and industry security frameworks.

For the subjective exam, understand the purpose:

> AWS provides information about its policies, processes and controls so customers can assess how AWS supports their own compliance obligations.

---

# 41. AWS Config

**AWS Config** is used to:

* assess AWS resource configurations;
* audit configurations;
* evaluate them;
* monitor configuration changes;
* compare actual configuration against desired configuration;
* maintain configuration history. 

The simplest question it answers is:

> **How is this AWS resource configured?**

Example:

```text
Required:
S3 bucket must be encrypted

AWS Config:
Checks actual configuration
↓
Compliant / non-compliant
```

---

# 42. AWS Artifact

**AWS Artifact** provides access to AWS security and compliance reports and agreements.

The module mentions examples such as:

```text
AWS ISO certifications
PCI reports
SOC reports
```



Memory:

```text
Artifact
→ Compliance documents
```

Not:

```text
Artifact
→ Automatically fixes compliance
```

It provides evidence and reports.

---

# 43. AWS Config vs Artifact vs CloudTrail

This comparison is very useful:

| Service          | Main question                         |
| ---------------- | ------------------------------------- |
| **CloudTrail**   | Who did what?                         |
| **AWS Config**   | How is the resource configured?       |
| **AWS Artifact** | Where are the AWS compliance reports? |

Scenario:

> “Who changed the S3 policy?”

**CloudTrail**

> “Is this S3 bucket currently configured according to our rule?”

**AWS Config**

> “Auditor wants AWS SOC report.”

**AWS Artifact**

---

# 44. Likely subjective question — Explain IAM

A good full answer:

> AWS Identity and Access Management is used to control access to AWS resources. IAM supports authentication and authorisation by defining identities and permissions. IAM users represent people or applications, IAM groups collect users with similar permissions, IAM policies define allowed or denied actions, and IAM roles provide permissions that can be temporarily assumed. IAM follows implicit deny by default, explicit deny overrides allow, and AWS recommends the principle of least privilege.

---

# 45. Likely subjective question — Explain how to secure a new AWS account

> A new AWS account should be secured by protecting the root user and avoiding its use for routine administration. An administrative IAM identity should be created for normal tasks, and multi-factor authentication should be enabled, particularly for privileged identities. Individual IAM identities should be created instead of sharing accounts, strong password policies should be used, permissions should follow least privilege, roles should be used where appropriate, and account activity should be monitored using AWS CloudTrail.

---

# 46. Likely subjective question — Explain encryption at rest and in transit

> Encryption at rest protects stored data, such as information stored in S3, EBS or databases. Encryption in transit protects data while it is travelling over a network, such as between a browser and a web server. AWS services can use encryption keys managed through AWS KMS for stored data, while protocols such as TLS and HTTPS are used to protect data in transit.

---

# 47. Likely subjective question — Explain AWS Config and AWS Artifact

> AWS Config is used to assess, audit and evaluate AWS resource configurations. It can record configuration changes and compare actual configurations with desired configurations, which supports security analysis and compliance auditing. AWS Artifact is different because it provides access to AWS security and compliance reports and agreements, such as ISO, PCI and SOC documentation.

---

# 48. Scenario-answering method

As with the earlier modules, use:

```text
1. Identify the concept/service.
2. Explain what it does.
3. Connect it to the scenario.
```

Example:

> A company finds that an employee may have modified an S3 bucket policy. Management wants to know which user made the change.

Weak answer:

> AWS CloudTrail.

Better answer:

> The company should use AWS CloudTrail because CloudTrail records user activity and API requests made in an AWS account. It can therefore help identify which identity changed the S3 bucket policy and when the action occurred.

The second answer proves understanding instead of merely throwing a service name at the examiner and hoping for mercy.

---

# 49. High-priority scenario clues

| If the question says...         | Think...                     |
| ------------------------------- | ---------------------------- |
| Physical AWS infrastructure     | AWS responsibility           |
| EC2 guest OS patching           | Customer responsibility      |
| Security group configuration    | Customer responsibility      |
| Shared security duties          | Shared Responsibility Model  |
| Identity                        | IAM user                     |
| Users with same permissions     | IAM group                    |
| Permission document             | IAM policy                   |
| Temporary assumable permissions | IAM role                     |
| Extra login factor              | MFA                          |
| Minimum permissions             | Least privilege              |
| Conflicting allow and deny      | Explicit Deny wins           |
| Root access                     | Protect it / don't use daily |
| Who changed resource?           | CloudTrail                   |
| Multiple AWS accounts           | AWS Organizations            |
| Encryption keys                 | AWS KMS                      |
| Application users               | Amazon Cognito               |
| DDoS                            | AWS Shield                   |
| Stored data                     | Encryption at rest           |
| Network traffic                 | Encryption in transit / TLS  |
| Prevent public S3 access        | S3 Block Public Access       |
| Check configuration             | AWS Config                   |
| Compliance reports              | AWS Artifact                 |

---

# 50. Common mistakes to avoid

**AWS secures everything because it is cloud-hosted.**
Wrong.

```text
AWS → OF the cloud
Customer → IN the cloud
```

**AWS patches every EC2 guest OS.**
Wrong. The customer handles EC2 guest OS patching.

**IAM role = IAM group.**
Wrong.

```text
Group → users
Role → assumable permissions
```

**Authentication = authorisation.**
Wrong.

```text
Authentication → Who?
Authorisation → What can they do?
```

**Explicit Allow beats Explicit Deny.**
Wrong.

```text
Explicit Deny wins.
```

**Least privilege means giving Admin access temporarily.**
No. It means giving only required permissions.

**SCP grants permissions.**
No. It limits possible permissions.

**Cognito manages AWS administrators.**
Usually wrong in this module. IAM handles AWS identities; Cognito handles application users.

**KMS encrypts network traffic by itself.**
Not the idea. KMS manages encryption keys; TLS/HTTPS protects data in transit.

**Artifact automatically makes an application compliant.**
No. Artifact provides reports and agreements.

---

# 51. What I would prioritise before the subjective exam

If time is short, master these:

```text
1. Shared responsibility
   AWS → OF
   Customer → IN

2. IAM
   User
   Group
   Policy
   Role

3. Permission logic
   Explicit Deny > Allow > Implicit Deny
   Least privilege

4. Account protection
   Protect root
   MFA
   Individual identities
   CloudTrail

5. Security services
   Organizations
   KMS
   Cognito
   Shield

6. Data protection
   At rest
   In transit

7. Compliance
   Config
   Artifact
```

These map directly to the module objectives. 

---

# Final 2-minute revision

```text
SHARED RESPONSIBILITY
─────────────────────
AWS
→ Security OF the cloud

Customer
→ Security IN the cloud
```

```text
IAM
───
User   → Identity
Group  → Users with same permissions
Policy → Permission document
Role   → Temporary assumable permissions
```

```text
PERMISSION RULE
───────────────
Explicit Deny
>
Explicit Allow
>
Implicit Deny

Best practice:
Least privilege
```

```text
ACCOUNT SECURITY
────────────────
Protect root
Enable MFA
Create individual identities
Use groups/policies
Use roles
Monitor with CloudTrail
```

```text
SECURITY SERVICES
─────────────────
Organizations → Multiple accounts
KMS           → Encryption keys
Cognito       → Application-user authentication
Shield        → DDoS protection
CloudTrail    → Who did what?
```

```text
DATA SECURITY
─────────────
At rest
→ Stored data
→ Encryption / KMS

In transit
→ Moving data
→ TLS / HTTPS
```

```text
COMPLIANCE
──────────
AWS Config
→ How is the resource configured?

AWS Artifact
→ Compliance reports and agreements
```

The **single most important mental model** for Module 4 is:

```text
AWS builds and secures the cloud infrastructure.

The customer decides who gets access,
what is configured,
what data is stored,
and how that data is protected.
```

Everything else in Module 4—IAM, MFA, least privilege, KMS, CloudTrail, Config and Artifact—is basically a tool for carrying out the customer's side of that responsibility. 

</details>

<details>
<summary><strong> Module 5: Networking and Content Delivery — Subjective Exam Preparation</strong></summary>

For a **subjective exam**, Module 5 is mainly about being able to look at a network scenario and explain:

* **where resources should be placed**;
* **how traffic reaches them**;
* **how private resources reach the internet safely**;
* **how networks connect to each other**;
* **how network traffic is secured**;
* **how users are routed to an application**;
* **how content is delivered with lower latency**.

The module itself is organised into six topics: networking basics, Amazon VPC, VPC networking, VPC security, Amazon Route 53, and Amazon CloudFront. 

The whole chapter can be reduced to one flow:

```text
IP addresses tell us WHERE devices are
        ↓
VPC creates our AWS network
        ↓
Subnets divide the network
        ↓
Route tables decide WHERE traffic goes
        ↓
Gateways/connectivity provide paths
        ↓
Security groups/NACLs decide WHAT traffic is allowed
        ↓
Route 53 tells users WHERE the application is
        ↓
CloudFront brings content CLOSER to users
```

---

# 1. Networking basics: what is a network?

A **network** is a collection of devices that communicate with each other.

The diagram on page 5 shows two subnets connected through a router:

```text
Devices
  │
Subnet 1
  │
Router
  │
Subnet 2
  │
Devices
```

The three basic ideas are:

```text
IP address → identifies a device
Subnet     → divides a network
Router     → directs traffic between networks
```



For most subjective questions, you do not need to turn into a network engineer. You just need enough networking knowledge to understand how AWS VPC works.

---

# 2. IP address

An **IP address** identifies a network device.

Example:

```text
192.0.2.10
```

The module introduces:

```text
IPv4 → 32 bits
IPv6 → 128 bits
```



For this module, most of the VPC examples use IPv4.

### Subjective answer

> An IP address uniquely identifies a device or network interface so that network traffic can be sent to the correct destination. IPv4 uses 32-bit addresses, while IPv6 uses 128-bit addresses and provides a much larger address space.

---

# 3. CIDR notation

AWS networks are commonly defined using **Classless Inter-Domain Routing**, or **CIDR**.

Example:

```text
192.0.2.0/24
```

The `/24` means that the first 24 bits are fixed as the **network portion**.

The remaining bits identify hosts.

Page 8 illustrates this division directly. 

A useful rule:

```text
Smaller CIDR prefix number
→ More available addresses

Larger CIDR prefix number
→ Fewer available addresses
```

For example:

```text
/16 → larger network
/24 → smaller network
/28 → much smaller network
```

---

# 4. Important CIDR sizes from the module

When creating a VPC, the module states that:

```text
Largest IPv4 CIDR block → /16
Smallest IPv4 CIDR block → /28
```

and subnet CIDR blocks **cannot overlap**. 

Example:

```text
VPC: 10.0.0.0/16

Possible subnets:
10.0.1.0/24
10.0.2.0/24
```

But overlapping address ranges would create a problem.

---

# 5. AWS reserves five addresses in each IPv4 subnet

The page 14 diagram is particularly exam-friendly.

For:

```text
10.0.0.0/24
```

there are theoretically:

```text
256 total addresses
```

but AWS reserves five addresses:

```text
10.0.0.0   → Network address
10.0.0.1   → Internal communication
10.0.0.2   → DNS resolution
10.0.0.3   → Future use
10.0.0.255 → Network broadcast address
```

Therefore:

```text
256 - 5 = 251 usable addresses
```



### Possible calculation question

> A subnet uses `/24`. How many IPv4 addresses are available for AWS resources?

**251 usable addresses** according to this module.

---

# 6. OSI model

The module introduces the seven-layer OSI model:

| Layer          | Main idea                  |
| -------------- | -------------------------- |
| 7 Application  | Application network access |
| 6 Presentation | Data format/encryption     |
| 5 Session      | Manages sessions           |
| 4 Transport    | Host-to-host communication |
| 3 Network      | Routing and IP             |
| 2 Data Link    | Local network / MAC        |
| 1 Physical     | Signals and bits           |

Important protocols shown include:

```text
Layer 7 → HTTP(S), FTP
Layer 4 → TCP, UDP
Layer 3 → IP
Layer 2 → MAC
```



For subjective prep, I would **not prioritise memorising every protocol** unless your lecturer specifically likes OSI questions.

The most relevant layers for this AWS module are:

```text
Layer 3 → IP / routing
Layer 4 → TCP / UDP
Layer 7 → HTTP / HTTPS
```

---

# 7. Amazon VPC — the central concept

**Amazon Virtual Private Cloud (VPC)** enables you to create a logically isolated section of AWS where you define your own virtual network.

The module states that you control:

* IP address ranges;
* subnets;
* route tables;
* network gateways;
* network configuration;
* multiple layers of security. 

The simplest analogy:

```text
AWS Cloud → Country

Your VPC → Your private city

Subnet → Neighbourhood

Route table → Road signs

Gateway → City entrance/exit
```

---

# 8. Good subjective answer — Amazon VPC

> Amazon VPC enables an organisation to create a logically isolated virtual network within the AWS Cloud. The customer can define the IP address range, create subnets, configure route tables and network gateways, and apply multiple layers of security. This allows the organisation to customise its AWS network according to application requirements.

---

# 9. VPC versus subnet

This is essential.

The module states:

```text
VPC
→ Belongs to one AWS Region
→ Can span multiple Availability Zones

Subnet
→ Part of a VPC
→ Belongs to exactly one Availability Zone
```



Visualise it:

```text
AWS Region
│
└── VPC
    ├── Subnet A → Availability Zone A
    └── Subnet B → Availability Zone B
```

---

# 10. Public versus private subnet

The module classifies subnets as:

```text
Public
Private
```

The difference is not the subnet's name.

The important factor is its **routing**.

A **public subnet** has a route to an **internet gateway**.

A private subnet does not have a direct route to the internet gateway.

Conceptually:

```text
Public subnet
→ Can contain internet-facing resources

Private subnet
→ Used for resources that should not be directly internet-accessible
```

---

# 11. Example architecture

Suppose you have:

* a public website;
* a backend database.

A sensible design is:

```text
Internet
   ↓
Public subnet
└── Web server
      ↓
Private subnet
└── Database
```

Why?

Because customers need access to the web server.

They have no legitimate reason to communicate directly with the database.

That distinction becomes one of the main design requirements in the module's VPC activity. 

---

# 12. Route table

A **route table** contains rules that determine where network traffic is directed.

Each route contains:

```text
Destination
+
Target
```

Example from page 17:

```text
Destination: 10.0.0.0/16
Target: local
```

Every VPC route table contains a built-in **local route**, which allows resources inside the VPC to communicate with one another. That local route cannot be deleted. 

---

# 13. Route-table analogy

Imagine driving.

You reach a road sign saying:

```text
City Centre → Straight
Airport     → Left
Highway     → Right
```

A route table does essentially the same thing for packets.

Example:

```text
10.0.0.0/16 → local

0.0.0.0/0 → internet gateway
```

Meaning:

```text
Traffic for this VPC
→ Keep local

Traffic for anywhere else
→ Send toward internet gateway
```

---

# 14. `0.0.0.0/0`

This appears repeatedly in the module.

You should recognise:

```text
0.0.0.0/0
```

as representing **all IPv4 destinations**.

So:

```text
0.0.0.0/0 → Internet Gateway
```

basically means:

> Traffic that does not match a more specific internal route can be sent toward the internet.

---

# 15. Internet gateway

An **internet gateway** provides connectivity between a VPC and the internet.

Page 20 shows a public subnet whose route table contains:

```text
10.0.0.0/16 → local

0.0.0.0/0 → Internet gateway
```



Think:

```text
VPC
↓
Internet Gateway
↓
Internet
```

---

# 16. Public internet access requires more than an internet gateway

A common mistake is:

> “Attach an internet gateway and every EC2 instance becomes public.”

No.

For a resource such as an EC2 instance to communicate directly with the internet, the architecture generally needs appropriate:

```text
Public IP
+
Route to internet gateway
+
Security rules
```

The route provides the path.

The public address identifies the resource externally.

The security control determines whether the traffic is allowed.

---

# 17. NAT gateway

This is one of the most important scenario services.

A **NAT gateway** allows resources in a private subnet to initiate connections to the internet without making those resources directly accessible from the internet.

Example:

> A private database needs to download software patches.

You do **not** want:

```text
Internet
↔
Database directly
```

Instead:

```text
Private server
     ↓
NAT gateway
     ↓
Internet gateway
     ↓
Internet
```

Page 21 shows the private subnet sending `0.0.0.0/0` traffic to the NAT gateway, while the public subnet routes internet traffic to the internet gateway. 

---

# 18. Internet gateway vs NAT gateway

Memorise this distinction:

```text
Internet Gateway
→ Direct internet connectivity for public resources

NAT Gateway
→ Outbound internet access for private resources
```

Scenario:

> “The EC2 instance must be accessible directly by customers.”

Think:

**Public subnet + internet gateway**

Scenario:

> “The private database must download updates but remain inaccessible from the public internet.”

Think:

**NAT gateway**

---

# 19. Elastic IP address

The module distinguishes between:

* an automatically assigned public IPv4 address;
* an **Elastic IP address**.

An Elastic IP:

* is associated with the AWS account;
* can be allocated and remapped;
* may involve additional cost. 

Think:

```text
Normal public IP
→ May be dynamically assigned

Elastic IP
→ Stable public address controlled by customer
```

---

# 20. Elastic Network Interface

An **Elastic Network Interface (ENI)** is a virtual network interface.

The module states that it can:

* be attached to an instance;
* be detached and attached to another instance;
* carry its network attributes with it. 

Think:

```text
EC2 instance
└── Virtual network card
    ├── Private IP
    └── Network attributes
```

For subjective exams, this is lower priority than VPC, routes and gateways.

---

# 21. VPC networking options

The module's Section 3 summary lists eight VPC networking options:

1. Internet gateway
2. NAT gateway
3. VPC endpoint
4. VPC peering
5. VPC sharing
6. AWS Site-to-Site VPN
7. AWS Direct Connect
8. AWS Transit Gateway 

You do not need to explain all eight equally deeply, but you should recognise the scenario each solves.

---

# 22. VPC peering

**VPC peering** creates private connectivity between two VPCs.

Conceptually:

```text
VPC A
 ↕
Peering connection
 ↕
VPC B
```

The VPCs can then communicate using private IP addresses when routing is configured appropriately.

### Important restriction

Peering is **not transitive**.

If:

```text
VPC A ↔ VPC B
VPC B ↔ VPC C
```

that does not automatically mean:

```text
VPC A ↔ VPC C
```

---

# 23. Good answer — VPC peering

> VPC peering provides private network connectivity between two VPCs. Resources in the peered VPCs can communicate using private IP addresses when the appropriate routes are configured. However, VPC peering is not transitive, so one VPC cannot automatically use another VPC as an intermediate path to a third VPC.

---

# 24. VPC sharing

VPC sharing enables multiple AWS accounts to deploy resources into centrally managed shared subnets.

The main idea is:

```text
One account
→ Manages network

Other accounts
→ Deploy resources into shared subnets
```

This allows central network governance while still keeping workloads distributed across accounts. 

---

# 25. AWS Site-to-Site VPN

**Site-to-Site VPN** connects an organisation's on-premises network to AWS through an encrypted VPN connection over the internet.

Conceptually:

```text
Company data centre
       ↓
Customer gateway
       ↓
Encrypted internet tunnel
       ↓
AWS VPC
```

### Best scenario clue

> “Securely connect an existing office/data centre to AWS over the internet.”

Think:

**Site-to-Site VPN**

---

# 26. AWS Direct Connect

**AWS Direct Connect** provides a dedicated network connection between an organisation and AWS.

The important contrast is:

```text
Site-to-Site VPN
→ Encrypted connection using internet

Direct Connect
→ Dedicated network connection
```

The module's scenario preparation associates Direct Connect with more consistent network connectivity than an ordinary internet-based connection. 

---

# 27. Site-to-Site VPN vs Direct Connect

| Site-to-Site VPN                        | Direct Connect                      |
| --------------------------------------- | ----------------------------------- |
| Uses internet path                      | Dedicated connection                |
| Encrypted tunnel                        | Dedicated network connectivity      |
| Faster/easier to establish conceptually | More enterprise-oriented setup      |
| Internet performance may vary           | More consistent network performance |

### Scenario clue

> “The company needs a dedicated network path between its data centre and AWS.”

**Direct Connect**

> “The company needs an encrypted connection over the internet.”

**Site-to-Site VPN**

---

# 28. VPC endpoint

A **VPC endpoint** provides private access from a VPC to supported AWS services without requiring:

* a public IP;
* a NAT gateway;
* an internet gateway.

Scenario from the module preparation:

> A private EC2 instance must access Amazon S3 without using public internet connectivity.

Answer:

**VPC endpoint**. 

---

# 29. Gateway endpoints

The module identifies gateway VPC endpoints for:

```text
Amazon S3
Amazon DynamoDB
```



Subjective answer:

> A VPC endpoint enables private communication between a VPC and supported AWS services without sending the traffic through a public internet path. This is useful when private resources need access to services such as S3 or DynamoDB without using a public IP address or NAT gateway.

---

# 30. AWS Transit Gateway

When only two VPCs need to communicate, VPC peering is manageable.

Now imagine:

```text
20 VPCs
5 VPN connections
On-premises networks
Direct Connect
```

Trying to create pairwise connections everywhere becomes a networking plate of spaghetti.

The diagram on page 27 shows AWS Transit Gateway replacing many individual connections with a central hub. 

Think:

```text
       VPC A
         |
VPC B — Transit Gateway — VPC C
         |
      VPN / on-prem
```

---

# 31. Good answer — Transit Gateway

> AWS Transit Gateway acts as a central networking hub that can connect multiple VPCs, VPN connections and other networks. It simplifies network architecture when an organisation has many separate networks because each network can connect to the central transit gateway instead of requiring a large number of individual peer-to-peer connections.

---

# 32. Choosing the connectivity option

| Requirement                              | Best match       |
| ---------------------------------------- | ---------------- |
| Public internet connectivity             | Internet gateway |
| Private resources need outbound internet | NAT gateway      |
| Private access to S3/DynamoDB            | VPC endpoint     |
| Connect two VPCs                         | VPC peering      |
| Multiple accounts use same network       | VPC sharing      |
| On-prem → AWS encrypted over internet    | Site-to-Site VPN |
| Dedicated on-prem → AWS connection       | Direct Connect   |
| Centrally connect many networks          | Transit Gateway  |

This table is extremely valuable for scenario questions.

---

# 33. VPC security

The module focuses on two network firewalls:

```text
Security group
Network ACL
```

These are similar enough to confuse students and different enough to cost marks.

The Section 4 takeaway explicitly says both can be used as firewall options for a VPC architecture. 

---

# 34. Security group

A **security group** acts as a virtual firewall for an instance or network interface.

Think:

```text
Security group
→ Protects individual resources
```

It controls things such as:

```text
Protocol
Port
Source
Destination
```

Example:

```text
TCP port 443
Source: Anywhere
→ Allow HTTPS to web server
```

---

# 35. Security groups use allow rules

A security group supports:

```text
ALLOW
```

rules.

It does **not** contain explicit deny rules in this module.

Traffic that is not allowed is implicitly blocked.



Example:

```text
Allow HTTPS
Allow SSH from company address

Everything else
→ Not allowed
```

---

# 36. Security groups are stateful

This is perhaps the most important security-group property.

**Stateful** means that if traffic is allowed in one direction as part of an established connection, the response traffic is automatically permitted.

Example:

```text
User → HTTPS → Web server
```

If inbound HTTPS is allowed:

```text
Web server → Response → User
```

is automatically permitted as response traffic.

You do not need a separate rule specifically for that response. 

---

# 37. Network ACL

A **Network Access Control List (NACL)** protects traffic at the **subnet level**.

Think:

```text
Security group → individual instance/network interface
Network ACL    → entire subnet
```



---

# 38. Network ACL supports allow AND deny

Unlike security groups, network ACLs support:

```text
ALLOW
DENY
```

This means they can explicitly block traffic from specific address ranges.

Scenario:

> “Block traffic from a known malicious IP range at the subnet boundary.”

Think:

**Network ACL**. 

---

# 39. Network ACL rules use numbers

NACL rules are evaluated from the **lowest rule number upward** until a matching rule is found.

Example:

```text
100 → Allow HTTPS
110 → Deny malicious IP
120 → Allow SSH
```

Rule 100 is evaluated before 110.

The first matching rule wins. 

---

# 40. Network ACLs are stateless

A network ACL is **stateless**.

That means it does not remember the connection.

If inbound traffic is allowed, the appropriate return traffic must also be permitted by an outbound rule.

```text
Inbound request → Checked

Outbound response → Checked again
```



---

# 41. Security group vs Network ACL

This is arguably the **most important comparison in Module 5**.

| Feature          | Security Group               | Network ACL                |
| ---------------- | ---------------------------- | -------------------------- |
| Protection level | Instance / network interface | Subnet                     |
| Rules            | Allow only                   | Allow and deny             |
| Stateful?        | Yes                          | No                         |
| Return traffic   | Automatically allowed        | Must be explicitly allowed |
| Rule evaluation  | Rules collectively apply     | Lowest-numbered match wins |

Memory:

```text
SECURITY GROUP
→ Instance
→ Stateful
→ Allow only

NETWORK ACL
→ Subnet
→ Stateless
→ Allow + Deny
```

---

# 42. Likely subjective question — Security group vs NACL

> A security group is a virtual firewall that operates at the instance or network-interface level and contains allow rules. It is stateful, meaning that return traffic for an allowed connection is automatically permitted. A network ACL operates at the subnet level and supports both allow and deny rules. Network ACLs are stateless, so inbound and outbound traffic must be permitted separately, and their rules are evaluated in numerical order until a match is found.

That is a strong full-mark comparison.

---

# 43. Designing the module's VPC scenario

The module gives a scenario involving:

* a public website;
* a private backend database;
* separate subnets;
* internet access for database patching;
* high availability;
* at least one custom firewall layer. 

A logical design is:

```text
                 Internet
                    │
            Internet Gateway
                    │
        ┌───────────┴───────────┐
        │                       │
     AZ A                     AZ B
        │                       │
 Public subnet A          Public subnet B
 Web/app server           Web/app server
        │                       │
 Private subnet A         Private subnet B
 Database                 Database/standby
```

For private-server outbound access:

```text
Private subnet
     ↓
NAT gateway in public side
     ↓
Internet gateway
```

And use:

```text
Security groups
and/or
Network ACLs
```

for firewall protection.

---

# 44. How to justify that architecture

For a subjective answer, don't merely draw boxes.

Explain the reasoning:

> The web server should be placed in a public subnet because customers need to reach it from the internet. The database should be placed in a private subnet so it is not directly internet-accessible. A NAT gateway can allow the private database or backend server to initiate outbound internet connections for updates while remaining private. Resources can be distributed across multiple Availability Zones for high availability, while security groups or network ACLs provide firewall protection.

That justification is what gets marks.

---

# 45. Amazon Route 53

**Amazon Route 53** is a highly available and scalable **Domain Name System (DNS)** service.

Its fundamental job is:

```text
Human-readable domain name
↓
Numeric IP address / destination
```

Example:

```text
www.example.com
↓
Route 53
↓
Application destination
```

The module also covers routing policies, multi-Region routing and DNS failover. 

---

# 46. DNS analogy

Think of a phone contact list.

You remember:

```text
"Mum"
```

not:

```text
+60-12-1234567
```

Your phone translates the meaningful name into the number.

DNS does something similar:

```text
www.company.com
→ IP address
```

---

# 47. Route 53 functions

For Module 5, remember that Route 53 can support things such as:

* DNS resolution;
* domain registration;
* routing policies;
* health checks;
* failover;
* multi-Region architectures. 

---

# 48. Route 53 routing policies

The module includes several routing approaches.

The most exam-relevant are:

```text
Simple
Weighted
Latency-based
Geolocation
Failover
Multivalue
```

The key is not memorising the names. It is matching each one to the scenario.

---

# 49. Simple routing

Use **simple routing** for basic DNS routing when no specialised routing logic is required.

Think:

```text
One ordinary destination
→ Simple
```

---

# 50. Weighted routing

Weighted routing distributes traffic according to specified proportions.

Example:

```text
Version A → 90%
Version B → 10%
```

Use cases:

* testing a new version;
* gradual rollout;
* splitting traffic.

Scenario:

> “Send 90% of customers to server A and 10% to server B.”

**Weighted routing**. 

---

# 51. Latency-based routing

Latency-based routing sends users toward the AWS Region that provides the lowest network latency.

Example:

```text
Asian user
→ whichever Region provides lower latency

European user
→ whichever Region provides lower latency
```

Scenario clue:

> “Route each user to the Region with the best network response time.”

**Latency-based routing**. 

---

# 52. Geolocation routing

Geolocation routing uses the user's geographic location.

Example:

```text
Malaysia → Malaysian/Asian application
Europe   → European application
```

Scenario:

> “European customers should see one website while Malaysian customers see another.”

**Geolocation routing**. 

---

# 53. Failover routing

Failover routing is used when you have:

```text
Primary
+
Backup
```

Route 53 health checks can determine whether the primary application is healthy.

If not:

```text
Primary unhealthy
↓
Route users to backup
```

Page 53 specifically describes Route 53 DNS failover using backup/failover scenarios, multi-Region architectures and health checks. 

---

# 54. Good subjective answer — Route 53 failover

> Amazon Route 53 can improve application availability by using DNS failover and health checks. Route 53 monitors the health of the primary application endpoint and normally directs users to it. If the primary endpoint becomes unhealthy, Route 53 can direct users to a configured backup endpoint, which reduces the impact of the failure.

---

# 55. Route 53 routing quick map

| Requirement                  | Routing policy |
| ---------------------------- | -------------- |
| Basic routing                | Simple         |
| 90% / 10% traffic split      | Weighted       |
| Lowest network delay         | Latency-based  |
| User's geographical location | Geolocation    |
| Primary → backup on failure  | Failover       |

That is sufficient for most scenario questions.

---

# 56. Multi-Region architecture

The module notes that a multi-Region deployment can improve application performance for a global audience. 

Conceptually:

```text
Users in Asia
→ Asia Region

Users in Europe
→ European Region
```

Route 53 can help direct users appropriately.

Benefits can include:

* lower latency;
* better global performance;
* higher availability when designed appropriately.

---

# 57. Amazon CloudFront

**Amazon CloudFront** is AWS's **Content Delivery Network (CDN)**.

Its job is to cache and deliver content using infrastructure closer to users.

Think:

```text
Route 53
→ Finds WHERE to go

CloudFront
→ Brings CONTENT closer
```

This distinction is essential.

---

# 58. Why CloudFront exists

Suppose your origin server is far away.

Without CloudFront:

```text
User
↓
Long distance
↓
Origin
```

Every request goes all the way back to the origin.

With CloudFront:

```text
User
↓
Nearby edge location
↓
Cached content
```

The result is:

* lower latency;
* faster delivery;
* less load on the origin.

The module's CloudFront section and study material emphasise these benefits.  

---

# 59. CloudFront origin

The **origin** is the original source of the content.

Possible origins in the module material include resources such as:

```text
Amazon S3
EC2
Elastic Load Balancing
Other web servers
```

Conceptually:

```text
Origin
↓
CloudFront
↓
Edge locations
↓
Users
```

---

# 60. Cache hit

A **cache hit** occurs when the requested content already exists at the edge location.

```text
User asks for image
↓
Image already at edge
↓
Return image immediately
```

No origin request is necessary for that request.

---

# 61. Cache miss

A **cache miss** means the requested object is not available at that edge cache.

Conceptually:

```text
User
↓
Edge location
↓
Regional edge cache
↓
Origin
```

The content is retrieved and can then be cached for subsequent requests. 

---

# 62. Edge location vs Regional edge cache

```text
Edge location
→ Close to users
→ Popular cached content

Regional edge cache
→ Larger intermediate cache
→ Between edge and origin
```

The Regional edge cache can keep less frequently requested content from having to travel all the way back to the origin each time.

---

# 63. Route 53 vs CloudFront

This is another important comparison.

| Route 53                  | CloudFront                      |
| ------------------------- | ------------------------------- |
| DNS service               | CDN                             |
| Resolves domain names     | Caches content                  |
| Selects destination       | Delivers content close to users |
| Supports routing policies | Uses edge infrastructure        |
| Supports DNS failover     | Reduces latency/origin load     |

Memory:

```text
Route 53
→ WHERE?

CloudFront
→ CONTENT FASTER
```

---

# 64. Likely subjective question — Explain Amazon VPC

> Amazon VPC allows an organisation to create a logically isolated virtual network in AWS. A VPC belongs to one AWS Region and can span multiple Availability Zones. The organisation defines its IP address range, creates subnets, configures route tables and gateways, and applies security controls. Public subnets can be used for internet-facing resources while private subnets can isolate internal resources such as databases.

---

# 65. Likely subjective question — Public vs private subnet

> A public subnet is a subnet whose routing provides connectivity to an internet gateway, making it suitable for resources that need direct internet connectivity, such as public web servers. A private subnet does not provide direct internet-gateway access and is suitable for internal resources such as databases. Private resources can still initiate outbound internet access through a NAT gateway when necessary.

---

# 66. Likely subjective question — Internet gateway vs NAT gateway

> An internet gateway connects a VPC to the internet and is used by resources that require direct internet connectivity. A NAT gateway is used when resources in a private subnet need to initiate outbound internet connections while remaining inaccessible from unsolicited inbound internet traffic. Therefore, an internet gateway supports public connectivity, whereas a NAT gateway preserves the private nature of backend resources.

---

# 67. Likely subjective question — VPN vs Direct Connect

> AWS Site-to-Site VPN provides an encrypted connection between an on-premises network and AWS over the internet. AWS Direct Connect provides dedicated network connectivity between the organisation and AWS and is suitable when more consistent network performance is required. Therefore, VPN emphasises secure internet-based connectivity, while Direct Connect provides a dedicated network path.

---

# 68. Likely subjective question — Explain Route 53

> Amazon Route 53 is a highly available and scalable DNS service that translates domain names into network destinations. It supports several routing policies, including weighted, latency-based, geolocation and failover routing. Route 53 can also perform health checks and direct users to backup endpoints when a primary endpoint becomes unhealthy, improving availability.

---

# 69. Likely subjective question — Explain CloudFront

> Amazon CloudFront is AWS's Content Delivery Network. It caches content at edge locations closer to end users so that requests do not always need to reach the original content source. This reduces network latency, improves content-delivery performance and reduces the workload on the origin server.

---

# 70. How to answer a VPC design scenario

Use this method:

### Step 1 — Identify what must be public

Example:

```text
Web server
→ Customers need access
→ Public subnet
```

### Step 2 — Identify what must stay private

```text
Database
→ Private subnet
```

### Step 3 — Decide internet path

```text
Public resource
→ Internet gateway

Private resource needing outbound updates
→ NAT gateway
```

### Step 4 — Add high availability

```text
Resources across multiple Availability Zones
```

### Step 5 — Add security

```text
Security groups
and/or
Network ACLs
```

That gives you a structured subjective answer instead of randomly drawing AWS icons until the page resembles a conspiracy board.

---

# 71. High-priority scenario clues

| If the question says...                        | Think...         |
| ---------------------------------------------- | ---------------- |
| Isolated AWS network                           | VPC              |
| Divide VPC                                     | Subnet           |
| Resource internet-facing                       | Public subnet    |
| Backend database                               | Private subnet   |
| Direct public internet connectivity            | Internet gateway |
| Private server needs outbound internet         | NAT gateway      |
| Private access to S3/DynamoDB                  | VPC endpoint     |
| Connect two VPCs                               | VPC peering      |
| Share subnets across accounts                  | VPC sharing      |
| Encrypted on-premises connection over internet | Site-to-Site VPN |
| Dedicated on-premises connection               | Direct Connect   |
| Many VPCs/networks centrally connected         | Transit Gateway  |
| Individual instance firewall                   | Security group   |
| Subnet firewall                                | Network ACL      |
| Stateful                                       | Security group   |
| Stateless                                      | Network ACL      |
| Explicit deny network traffic                  | Network ACL      |
| Domain name → IP                               | Route 53         |
| 90/10 traffic                                  | Weighted         |
| Lowest latency                                 | Latency-based    |
| Geographic origin                              | Geolocation      |
| Primary/backup                                 | Failover         |
| Cache content near users                       | CloudFront       |
| Original content source                        | Origin           |
| Object already at edge                         | Cache hit        |

---

# 72. Common mistakes to avoid

**A VPC spans multiple Regions.**
Wrong.

```text
VPC → One Region
```

---

**A subnet spans several Availability Zones.**
Wrong.

```text
Subnet → One AZ
```

---

**A subnet is public because it has a public-sounding name.**
Wrong.

Routing determines whether it has internet-gateway connectivity.

---

**Internet gateway = NAT gateway.**
Wrong.

```text
IGW → Public/direct internet
NAT → Private outbound internet
```

---

**NAT gateway allows internet users to directly reach the private server.**
Wrong.

Its purpose here is outbound connectivity for private resources.

---

**VPC peering is transitive.**
Wrong.

```text
A ↔ B
B ↔ C

does not automatically mean

A ↔ C
```

---

**Security groups contain deny rules.**
Wrong.

They use allow rules.

---

**Security groups are stateless.**
Wrong.

They are stateful.

---

**Network ACLs are stateful.**
Wrong.

They are stateless.

---

**Network ACL protects an individual EC2 instance.**
Not in this model.

```text
NACL → subnet
Security Group → instance/ENI
```

---

**Route 53 caches website files.**
Wrong.

```text
Route 53 → DNS/routing
CloudFront → caching/content delivery
```

---

**CloudFront is where the original content must live.**
Wrong.

CloudFront retrieves from an **origin** and caches copies closer to users.

---

# 73. What I would prioritise for the subjective exam

If time is short, learn these **seven things extremely well**:

```text
1. VPC vs subnet
   VPC → Region
   Subnet → AZ

2. Public vs private subnet

3. Internet Gateway vs NAT Gateway

4. VPC connectivity options
   Endpoint
   Peering
   VPN
   Direct Connect
   Transit Gateway

5. Security Group vs Network ACL

6. Route 53 routing
   Weighted
   Latency
   Geolocation
   Failover

7. CloudFront
   CDN
   Edge location
   Cache
   Origin
```

These align closely with the module's objectives and section summaries.  

# Final 2-minute revision

```text
NETWORK
───────
IP address → Identifies device
CIDR       → Address range
Subnet     → Divides network
Route      → Chooses path
```

```text
VPC
───
One Region
Can span multiple AZs

Subnet
→ One Availability Zone

Public subnet
→ Internet-facing

Private subnet
→ Internal resources
```

```text
CONNECTIVITY
────────────
Internet Gateway
→ Public internet

NAT Gateway
→ Private outbound internet

VPC Endpoint
→ Private access to AWS service

VPC Peering
→ Two VPCs

Site-to-Site VPN
→ Encrypted internet tunnel

Direct Connect
→ Dedicated connection

Transit Gateway
→ Central network hub
```

```text
SECURITY GROUP
──────────────
Instance / ENI
Stateful
Allow only
Return traffic automatic
```

```text
NETWORK ACL
───────────
Subnet
Stateless
Allow + Deny
Lowest-numbered matching rule wins
Return traffic requires rules
```

```text
ROUTE 53
────────
DNS

Weighted
→ Percentage

Latency-based
→ Lowest latency

Geolocation
→ User location

Failover
→ Primary + backup
```

```text
CLOUDFRONT
──────────
CDN
Edge locations
Regional edge caches
Origin
Cache hit / miss

Main purpose:
Lower latency
Reduce origin load
```

The **single most important mental model** in Module 5 is:

```text
VPC
→ Build the network

SUBNETS
→ Divide the network

ROUTES + GATEWAYS
→ Move traffic

SECURITY GROUPS + NACLs
→ Control traffic

ROUTE 53
→ Tell users where to go

CLOUDFRONT
→ Deliver the content faster
```

Once that chain makes sense, Module 5 stops looking like twenty unrelated AWS networking terms and becomes one network architecture story.

</details>

<details>
<summary><strong>Module 6: Compute — Subjective Exam Preparation</strong></summary>

For a **subjective exam**, Module 6 is mainly testing whether you can look at a workload and decide:

> **How should this application run in AWS, and how much infrastructure should the customer manage?**

The module covers six areas: compute services overview, Amazon EC2, EC2 cost optimisation, container services, AWS Lambda, and AWS Elastic Beanstalk. 

The whole module can be understood as this spectrum:

```text
MORE INFRASTRUCTURE CONTROL
        ↓
Amazon EC2
        ↓
Containers on EC2
        ↓
AWS Fargate
        ↓
Elastic Beanstalk / Lambda
        ↓
LESS INFRASTRUCTURE MANAGEMENT
```

The important skill is **choosing the right compute model for the scenario**, not simply memorising definitions.

---

# 1. Start with the compute-service map

The easiest way to separate the services is:

| Requirement                                   | Think                 |
| --------------------------------------------- | --------------------- |
| Full virtual-machine and OS control           | **Amazon EC2**        |
| Package application into containers           | **Containers**        |
| AWS-native container orchestration            | **Amazon ECS**        |
| Kubernetes on AWS                             | **Amazon EKS**        |
| Run containers without managing servers       | **AWS Fargate**       |
| Store container images                        | **Amazon ECR**        |
| Run code only when an event happens           | **AWS Lambda**        |
| Upload a normal web app and let AWS deploy it | **Elastic Beanstalk** |

 

Think:

```text
Need a SERVER?
→ EC2

Need a CONTAINER?
→ ECS / EKS

Need container compute WITHOUT managing servers?
→ Fargate

Need a FUNCTION?
→ Lambda

Need to deploy a WEB APPLICATION easily?
→ Elastic Beanstalk
```

---

# 2. What is Amazon EC2?

**Amazon Elastic Compute Cloud (EC2)** provides virtual machines in AWS.

The module states that EC2 lets you run Windows or Linux virtual machines and gives you control over the guest operating system. EC2 instances are launched from Amazon Machine Images into a VPC. 

Think of EC2 as:

> **Renting a computer in AWS.**

You decide things such as:

```text
Operating system
CPU
Memory
Storage
Network
Software
Security
```

### Good subjective answer

> Amazon EC2 is an AWS compute service that provides resizable virtual machines called instances. Customers can choose the operating system, instance type, networking, storage and security settings and have control over the guest operating system. EC2 is suitable when an organisation requires flexible virtual-machine computing and greater control over the underlying software environment.

---

# 3. When should you use EC2?

Use EC2 when the scenario says things like:

* full operating-system control;
* install custom software;
* run a traditional server application;
* configure the environment manually;
* need a web, application, game, mail or file server.

A scenario might say:

> “The company needs administrator access to the operating system and must install custom software.”

Think:

**Amazon EC2**

Not Lambda or Beanstalk.

---

# 4. EC2 vs a managed service

One activity in the module compares running SQL Server on:

```text
Amazon EC2
vs
Amazon RDS
```

With EC2, the customer manages more:

```text
Operating system
Database installation
Patching
Backups
High availability
Configuration
```

With RDS, AWS manages more of those tasks. 

The central trade-off is:

```text
EC2
→ More control
→ More responsibility

Managed service
→ Less control
→ Less administration
```

### Good exam explanation

> Amazon EC2 provides greater control because the customer manages the operating system and installed applications. A managed service reduces administrative responsibility because AWS manages more of the underlying environment. Therefore, EC2 is appropriate when customisation and operating-system control are required, whereas a managed service is preferable when the organisation wants to reduce infrastructure-management tasks.

---

# 5. The nine EC2 launch decisions

The module teaches **nine key choices** when launching an EC2 instance:

```text
1. AMI
2. Instance type
3. Network settings
4. IAM role
5. User data
6. Storage
7. Tags
8. Security group
9. Key pair
```



You should understand what each one controls.

---

# 6. AMI — Amazon Machine Image

An **AMI** is a template used to create an EC2 instance.

It may contain:

* Windows or Linux;
* preinstalled software;
* configuration.

Think:

```text
AMI
= Blueprint

EC2 instance
= Actual building created from blueprint
```

### Subjective answer

> An Amazon Machine Image is a template used to launch EC2 instances. It contains an operating system and may also contain preinstalled software and configuration. Using an AMI allows organisations to launch multiple instances with a consistent starting environment.

---

# 7. AMI is not the running server

Do not confuse:

```text
AMI
→ Template

EC2 instance
→ Running virtual machine
```

Scenario:

> “The company wants to launch 20 identical web servers.”

One sensible method is:

```text
Configure one environment
↓
Create AMI
↓
Launch multiple EC2 instances
```

---

# 8. EC2 instance type

The **instance type** determines the hardware resources available to the EC2 instance.

The module highlights:

```text
CPU
Memory
Storage
Network performance
```



Common categories in the module include:

```text
General purpose
Compute optimised
Memory optimised
Storage optimised
Accelerated computing
```

---

# 9. Choosing an instance category

### General purpose

Balanced CPU and memory.

Think:

> ordinary web/application workload.

### Compute optimised

More processing power.

Think:

> CPU-intensive calculation.

### Memory optimised

More RAM.

Think:

> in-memory database.

### Storage optimised

High storage performance.

Think:

> large storage-intensive workload.

### Accelerated computing

Special hardware such as accelerators.

Think:

> machine learning or graphics.

---

# 10. Instance-name example

The module gives an example such as:

```text
t3.large
```

Interpret it as:

```text
t     → Family
3     → Generation
large → Size
```

The important exam concept is not memorising every instance family.

It is understanding:

> **The instance type should match the workload.**

---

# 11. Network settings

When launching EC2, you choose where it will run.

Think:

```text
VPC
↓
Subnet
↓
EC2 instance
```

Network configuration can determine things such as whether the instance:

* is in a public or private subnet;
* receives a public address;
* can communicate with other resources.

For detailed subnet/gateway concepts, that links directly back to Module 5.

---

# 12. IAM role for EC2

An **IAM role** gives an EC2 instance permission to access other AWS services.

Example:

```text
EC2 application
↓
IAM role
↓
Amazon S3
```

Suppose the application needs to read files from S3.

Instead of placing permanent AWS credentials inside the application, an IAM role can grant the required permissions.

### Important distinction

```text
IAM role
→ AWS permissions

Security group
→ Network traffic
```

Do not mix them up.

---

# 13. User data

**User data** allows a script to run when an instance is first launched.

The module specifically identifies user data as a way to provide a script that runs the first time the instance launches. 

Example:

```text
Launch EC2
↓
User-data script executes
↓
Install web server
↓
Download application
↓
Start service
```

### Subjective answer

> EC2 user data allows a startup script to be provided when an instance is launched. It can automate initial configuration tasks such as installing software, downloading application files or starting services, reducing the need for manual configuration.

---

# 14. EC2 storage

The module introduces storage choices for EC2.

The two important concepts are:

```text
Amazon EBS
EC2 Instance Store
```

## Amazon EBS

Persistent block storage.

```text
Stop instance
↓
EBS data can remain
```

## Instance Store

Temporary local storage.

Suitable for data that can be recreated.

```text
Temporary/cache data
→ Instance Store
```

The later Storage module explains these in more detail.

---

# 15. Tags

A **tag** is key-value metadata attached to an AWS resource.

Example:

```text
Name = WebServer01
Department = Finance
Environment = Production
```

Tags can help with:

* organisation;
* filtering;
* automation;
* cost allocation.

Think:

```text
Tag
→ Label the resource
```

---

# 16. Security groups

A **security group** is a set of firewall rules controlling traffic to an EC2 instance.

The module says rules specify things such as:

```text
Source
Port
Protocol
```



Example:

```text
TCP 443
Source: Anywhere
→ Allow HTTPS
```

For administration:

```text
TCP 22
Source: Company IP
→ Allow SSH
```

### Good subjective answer

> A security group acts as a virtual firewall for an EC2 instance. It controls allowed network traffic based on criteria such as protocol, port and source address. Security groups should be configured so that only necessary traffic is permitted.

---

# 17. Key pair

A **key pair** supports secure administrative access to EC2.

The module says:

```text
AWS stores → Public key
Customer stores → Private key
```

For Linux, the private key can be used for SSH access. For Windows, it can be used to obtain the administrator password. 

Memory:

```text
Security group
→ Who can reach the server over the network?

Key pair
→ How do I securely log into the server?
```

---

# 18. EC2 lifecycle

An EC2 instance can move through states such as:

```text
AMI
↓
Pending
↓
Running
```

From running, it may be:

```text
Rebooted
Stopped
Hibernated
Terminated
```

The module emphasises that only **EBS-backed instances** can be stopped. 

---

# 19. Reboot vs stop vs terminate

This is very likely to appear in a subjective or scenario question.

| Action        | Meaning                                      |
| ------------- | -------------------------------------------- |
| **Reboot**    | Restart the instance                         |
| **Stop**      | Shut it down temporarily; it can start again |
| **Terminate** | Permanently remove the instance              |

Memory:

```text
Reboot
→ Restart

Stop
→ Turn off temporarily

Terminate
→ Delete
```

---

# 20. Stop vs terminate

Suppose a development server is not needed overnight.

You might:

```text
STOP
```

because it is needed again tomorrow.

If the server is permanently no longer required:

```text
TERMINATE
```

Do not write:

> “Stop means delete the EC2 instance.”

That is incorrect.

---

# 21. Public IP after stop/start

The module's lifecycle material teaches that an automatically assigned public IPv4 address may change after an instance is stopped and started.

If a persistent public address is required:

> **Use an Elastic IP address.** 

So:

```text
Temporary automatic public IP
→ May change

Persistent public IPv4
→ Elastic IP
```

---

# 22. Instance metadata

An EC2 instance can obtain information about itself through **instance metadata**.

For example:

```text
Instance ID
Availability Zone
IP information
```

Think:

> “What does this instance know about itself?”

→ **Instance metadata**

This is usually lower priority than AMI, user data, lifecycle and pricing, but it can appear as a distinction.

---

# 23. Amazon CloudWatch for EC2

**Amazon CloudWatch** captures and reviews EC2 metrics. The module specifically mentions it in the EC2 section summary. 

Examples include:

```text
CPU utilisation
Network traffic
Disk operations
Status checks
```

The teaching material distinguishes:

```text
Basic monitoring → 5-minute interval
Detailed monitoring → 1-minute interval
```



The important subjective idea is:

> **CloudWatch helps you understand whether EC2 resources are healthy and appropriately sized.**

---

# 24. EC2 pricing models

The module introduces:

```text
On-Demand Instances
Reserved Instances
Spot Instances
Dedicated Instances
Dedicated Hosts
Scheduled Reserved Instances
```



The best way to learn them is by workload pattern.

---

# 25. On-Demand Instances

On-Demand means:

* no long-term commitment;
* pay according to usage;
* flexible.

Best suited to:

```text
Short-term
Unpredictable
Changing workloads
```

### Scenario

> “A startup does not know how long it will need the server.”

**On-Demand**

### Subjective answer

> On-Demand Instances allow customers to use EC2 without a long-term commitment and pay according to usage. They are suitable for short-term, unpredictable or changing workloads where flexibility is more important than long-term discounts.

---

# 26. Reserved Instances

The module describes Reserved Instances as providing discounted EC2 pricing in exchange for a **1-year or 3-year commitment**. 

Best suited to:

```text
Stable
Predictable
Long-running workloads
```

### Scenario

> “A production application will run continuously for three years.”

Think:

**Reserved Instances**

### Subjective answer

> Reserved Instances are suitable for predictable workloads that are expected to run for a long period. Customers commit for a one-year or three-year term and can receive discounted pricing compared with flexible On-Demand usage.

---

# 27. Spot Instances

Spot Instances use spare AWS capacity at significantly lower prices, but the module states they can be interrupted by AWS with a **2-minute notification**. 

Best for:

```text
Batch processing
Rendering
Flexible workloads
Fault-tolerant jobs
Jobs that can restart
```

Bad fit:

```text
Critical non-interruptible database
```

### Subjective answer

> Spot Instances provide access to unused EC2 capacity at potentially much lower cost. However, AWS can interrupt the instance, so Spot is most appropriate for flexible and fault-tolerant workloads such as batch processing rather than applications that cannot tolerate interruption.

---

# 28. Dedicated Instance vs Dedicated Host

These sound similar but are different.

## Dedicated Instance

The EC2 instance runs on hardware dedicated to a **single customer**.

## Dedicated Host

The customer receives an entire physical server dedicated to their use.

The module associates Dedicated Hosts with benefits such as licensing and regulatory/compliance requirements. 

Memory:

```text
Dedicated Instance
→ Dedicated hardware

Dedicated Host
→ Entire physical host
```

---

# 29. Scheduled Reserved Instances

In the module, Scheduled Reserved Instances are designed for recurring schedules.

Example:

```text
Every Monday
8 AM – 5 PM
```

and you need reserved capacity on that repeating schedule.

Think:

**Scheduled Reserved Instance**. 

For the subjective exam, this is probably lower priority than On-Demand, Reserved and Spot.

---

# 30. Pricing-model decision table

| Workload                       | Best fit in module          |
| ------------------------------ | --------------------------- |
| Uncertain / temporary          | On-Demand                   |
| Predictable / continuous       | Reserved                    |
| Flexible / interruptible       | Spot                        |
| Physical licensing requirement | Dedicated Host              |
| Single-customer hardware       | Dedicated Instance          |
| Fixed recurring schedule       | Scheduled Reserved Instance |

Memory:

```text
Uncertain → On-Demand
Predictable → Reserved
Interruptible → Spot
Physical host requirement → Dedicated Host
```

---

# 31. Four pillars of EC2 cost optimisation

The module gives four pillars:

```text
1. Right-size
2. Increase elasticity
3. Use the optimal pricing model
4. Optimise storage choices
```



This is very likely to be useful for a subjective question.

---

# 32. Pillar 1 — Right-size

**Right-sizing** means matching resources to actual workload requirements.

Consider:

```text
CPU
Memory
Storage
Network throughput
```

The module recommends using CloudWatch metrics to identify idle or over-sized instances and says:

> **Right-size, then reserve.** 

Example:

```text
16 vCPU instance
Average CPU utilisation = 3%

Possible improvement:
Move to smaller instance
```

### Good answer

> Right-sizing means selecting an EC2 instance that matches the actual CPU, memory, storage and networking requirements of the workload. CloudWatch metrics can be used to identify underutilised instances. Reducing an unnecessarily large instance can lower cost without reducing required application performance.

---

# 33. Pillar 2 — Increase elasticity

The module recommends stopping or hibernating EBS-backed instances when they are not required and using automatic scaling to match resource usage with demand. 

Example:

```text
Development server required:
8 AM – 6 PM

At night:
Stop it
```

Or:

```text
Low demand
→ fewer instances

High demand
→ more instances
```

### Subjective answer

> Increasing elasticity means adjusting compute capacity according to actual demand and avoiding running unnecessary resources. For example, development instances can be stopped when not in use, and automatic scaling can increase or decrease capacity according to workload demand.

---

# 34. Pillar 3 — Optimal pricing model

Do not use the same pricing model blindly for everything.

The module gives examples such as:

```text
Variable workload
→ On-Demand + Spot

Predictable workload
→ Reserved

Serverless possibility
→ Consider Lambda
```



You can even combine models:

```text
Predictable baseline
→ Reserved

Unexpected peak
→ On-Demand

Interruptible batch work
→ Spot
```

### Good answer

> Cost can be optimised by selecting pricing models according to workload behaviour. Predictable baseline workloads can use Reserved Instances, unpredictable workloads can use On-Demand Instances, and interruption-tolerant workloads can use Spot Instances. Different pricing models can also be combined within the same architecture.

---

# 35. Pillar 4 — Optimise storage choices

The module recommends:

* resizing EBS volumes;
* selecting appropriate EBS volume types;
* deleting unnecessary snapshots;
* considering lower-cost storage where performance allows;
* using S3 storage options and lifecycle policies where appropriate. 

The important idea:

> Do not pay for more storage performance or capacity than the application requires.

### Good answer

> Storage optimisation involves matching storage performance and capacity to application requirements. Organisations can resize EBS volumes, select more appropriate volume types, remove unnecessary snapshots and move suitable data to lower-cost storage services or lifecycle tiers.

---

# 36. Cost optimisation is continuous

The module explicitly says:

> **Cost optimisation is an ongoing process.**

Recommendations include:

* use cost-allocation tags;
* define metrics;
* set targets;
* review regularly;
* assign responsibility for optimisation. 

So a strong subjective answer should avoid implying:

> “Optimise the architecture once and then forget it forever.”

Usage changes over time.

---

# 37. Containers

A **container** packages an application together with what it needs to run.

Think:

```text
Application code
+
Libraries
+
Dependencies
=
Container
```

The main benefit is consistency.

```text
Developer laptop
Test
Production
```

can all run the same packaged application.

---

# 38. Container vs virtual machine

A virtual machine includes a complete guest operating system.

A container shares the underlying OS environment and packages the application and its dependencies.

Conceptually:

```text
VIRTUAL MACHINE

App
Libraries
Guest OS
────────
Hypervisor


CONTAINER

App
Libraries
────────
Shared OS
```

Therefore, containers are generally:

* lighter;
* faster to start;
* more portable.

For the module, the important concept is not low-level container internals; it is knowing how AWS runs and manages them.

---

# 39. Docker

The module introduces Docker in the container section.

Think:

```text
Docker image
→ Packaged application template

Container
→ Running instance of that image
```

This is similar to:

```text
AMI
→ EC2 instance
```

in concept.

---

# 40. Container orchestration

If you have one container, manual management is simple.

If you have:

```text
500 containers
across
50 servers
```

you need help with:

```text
Where each container runs
Scaling
Networking
Load distribution
Replacement after failure
```

That is **container orchestration**.

---

# 41. Amazon ECS

**Amazon Elastic Container Service (ECS)** is AWS's container orchestration service.

It helps run and manage containers across compute capacity.

Think:

```text
Containers
↓
Amazon ECS decides where/how to run them
↓
EC2 or Fargate provides compute
```

The module's ECS cluster slide focuses heavily on whether the customer wants to manage the underlying cluster. 

---

# 42. ECS on EC2 vs ECS on Fargate

This distinction is important.

## ECS backed by EC2

The customer manages:

```text
EC2 infrastructure
Operating environment
Capacity
```

Benefit:

> more control.

## ECS backed by Fargate

AWS manages the underlying server infrastructure.

Customer focuses more on:

```text
Containers
Applications
CPU/memory requirements
```

The module summarises:

```text
Want to manage ECS cluster infrastructure?
→ ECS on EC2

Don't want to manage servers?
→ ECS on Fargate
```



---

# 43. AWS Fargate

**AWS Fargate** provides serverless compute for containers.

“Serverless” does **not** mean servers disappear.

It means:

> The customer does not provision and manage the underlying servers.

### Scenario

> “The company wants to run containers but does not want to manage EC2 instances.”

**AWS Fargate**

### Good answer

> AWS Fargate enables organisations to run containers without managing the underlying EC2 servers. Customers define their container and compute requirements while AWS manages the infrastructure used to run the containers, reducing administrative overhead.

---

# 44. Kubernetes

The module defines Kubernetes as open-source software for **container orchestration**.

It automates:

```text
Container provisioning
Networking
Load distribution
Scaling
```

and can be used both on-premises and in the cloud. 

Think:

```text
Docker
→ Runs containers

Kubernetes
→ Manages many containers/nodes
```

---

# 45. Amazon EKS

**Amazon Elastic Kubernetes Service (EKS)** enables Kubernetes to run on AWS.

The module says it is Kubernetes-conformant and compatible with Kubernetes tools and add-ons. 

### Scenario

> “The company already uses Kubernetes and wants to migrate those workloads to AWS.”

Think:

**Amazon EKS**

### Good answer

> Amazon EKS is AWS's managed Kubernetes service. It enables organisations to run Kubernetes-based container workloads on AWS while remaining compatible with Kubernetes tools and workloads, making it suitable for organisations that already use Kubernetes.

---

# 46. ECS vs EKS

This distinction is essential:

```text
ECS
→ AWS-native container orchestration

EKS
→ Kubernetes on AWS
```

Scenario:

> “No Kubernetes requirement; company wants AWS's own managed container orchestrator.”

**ECS**

Scenario:

> “Must use Kubernetes.”

**EKS**

---

# 47. Amazon ECR

**Amazon Elastic Container Registry (ECR)** is a managed Docker container registry for storing, managing and deploying container images. 

Think:

```text
ECR
→ Store images

ECS / EKS
→ Orchestrate containers

EC2 / Fargate
→ Provide compute
```

This is an extremely useful service map.

---

# 48. Container-service map

```text
Docker
→ Build/package containers

ECR
→ Store container images

ECS
→ AWS-native orchestration

EKS
→ Kubernetes orchestration

Fargate
→ Run containers without managing servers
```

If you learn only one container diagram, learn that one.

---

# 49. AWS Lambda

**AWS Lambda** is a serverless compute service for running code in response to events or schedules.

Conceptually:

```text
Event occurs
↓
Lambda function runs
↓
Work finishes
```

The customer does not provision EC2 servers for the function.

The module lists benefits including:

* multiple programming languages;
* automated administration;
* built-in fault tolerance;
* function orchestration;
* pay-per-use pricing. 

---

# 50. Event-driven computing

Lambda is particularly useful when code should run **because something happened**.

Example:

```text
Image uploaded to S3
↓
Lambda triggered
↓
Resize image
↓
Save thumbnail
```

Or:

```text
Scheduled time
↓
Lambda
↓
Stop development EC2 instances
```

The module includes the schedule-based EC2 automation example. 

---

# 51. Lambda execution role

A Lambda function may need permission to access other AWS services.

Example:

```text
Lambda
↓
Needs to stop EC2
```

The Lambda function uses an **execution role** granting the required permissions.

Important distinction:

```text
Event source
→ Tells Lambda WHEN to run

Execution role
→ Tells Lambda WHAT AWS actions it may perform
```

---

# 52. Lambda use cases

Think Lambda when the scenario involves:

```text
File processing
Automation
Scheduled task
Notifications
Event-driven code
Small API logic
Data transformation
```

and the organisation does not want to manage servers.

---

# 53. Lambda limits in the module

The **2022 course material** states:

```text
Maximum execution time → 15 minutes
Maximum memory → 10,240 MB
```



For your exam based on these slides, those are the values to use.

Therefore, if the scenario says:

> “A single task must run continuously for six hours.”

Lambda is probably not the intended answer.

---

# 54. Good subjective answer — Lambda

> AWS Lambda is a serverless compute service that runs code in response to events or schedules. AWS manages the underlying infrastructure, scaling and administration, while the customer focuses on the function code. Lambda is well suited to short, event-driven tasks such as file processing, automation and scheduled actions because the customer does not need to provision continuously running servers.

---

# 55. EC2 vs Lambda

| EC2                              | Lambda                          |
| -------------------------------- | ------------------------------- |
| Virtual machine                  | Function                        |
| Customer manages OS              | AWS manages infrastructure      |
| Can run continuously             | Runs when triggered             |
| Greater control                  | Less administration             |
| Pay for running compute          | Pay based on function usage     |
| Suitable for traditional servers | Suitable for event-driven tasks |

Memory:

```text
Need a COMPUTER
→ EC2

Need CODE to run when something happens
→ Lambda
```

---

# 56. AWS Elastic Beanstalk

**AWS Elastic Beanstalk** simplifies deployment of web applications.

The module says it automatically handles:

```text
Infrastructure provisioning
Configuration
Deployment
Load balancing
Automatic scaling
Health monitoring
Analysis/debugging
Logging
```



The customer mainly uploads the application code.

---

# 57. Elastic Beanstalk workflow

Think:

```text
Developer writes application
↓
Uploads code to Elastic Beanstalk
↓
Beanstalk provisions environment
↓
Deploys application
↓
Handles load balancing/scaling/monitoring
```

The module supports platforms such as:

```text
Java
.NET
PHP
Node.js
Python
Ruby
Go
Docker
```



---

# 58. Elastic Beanstalk responsibility model

The page 81 diagram essentially shows:

```text
YOU MANAGE
→ Application code

AWS MANAGES MORE OF:
→ HTTP server
→ Application server
→ Language interpreter/platform
→ Operating system
→ Host
```



This is why Beanstalk is considered a more managed application platform.

---

# 59. Elastic Beanstalk pricing

The module states:

> **There is no additional charge for Elastic Beanstalk itself.**

You pay for the underlying AWS resources it uses. 

For example:

```text
Elastic Beanstalk
↓ may provision
EC2
Load balancer
Storage
Other AWS resources
```

Those underlying resources can still be billed.

So:

```text
No separate Beanstalk fee
≠
Application is completely free
```

---

# 60. Benefits of Elastic Beanstalk

The module summarises benefits as:

```text
Fast and simple to start
Developer productivity
Difficult to outgrow
Complete resource control
```



The important subjective idea is:

> It provides easy application deployment without completely hiding the underlying AWS resources.

---

# 61. Good subjective answer — Elastic Beanstalk

> AWS Elastic Beanstalk is a managed service that simplifies deployment of web applications. Developers upload their application code, while Elastic Beanstalk handles tasks such as infrastructure provisioning, deployment, load balancing, automatic scaling, health monitoring and logging. It supports several common application platforms and allows developers to focus more on application development while still retaining access to the underlying AWS resources.

---

# 62. EC2 vs Elastic Beanstalk

| EC2                                             | Elastic Beanstalk                                     |
| ----------------------------------------------- | ----------------------------------------------------- |
| Build/manage server environment yourself        | Upload application and let service deploy environment |
| Greater infrastructure control                  | Less infrastructure work                              |
| Customer configures more                        | AWS automates more                                    |
| Suitable for unusual/custom server environments | Suitable for common web applications                  |

Scenario:

> “The developer needs root-level OS customisation.”

**EC2**

Scenario:

> “The developer wants to upload Python web code and let AWS handle scaling and load balancing.”

**Elastic Beanstalk**

---

# 63. Lambda vs Elastic Beanstalk

This distinction is very exam-friendly.

| Lambda               | Elastic Beanstalk             |
| -------------------- | ----------------------------- |
| Function-based       | Application-based             |
| Event driven         | Web application environment   |
| Runs when triggered  | Application remains deployed  |
| Serverless functions | Managed platform              |
| Short tasks          | Conventional web applications |

Think:

```text
"Run this function when an image arrives."
→ Lambda

"Deploy my Python web application."
→ Elastic Beanstalk
```

The module's sample exam question specifically asks which AWS service can quickly deploy applications using programming languages such as .NET and Java; the answer is **Elastic Beanstalk**. 

---

# 64. The big compute comparison

| Requirement                          | Best starting answer |
| ------------------------------------ | -------------------- |
| Full OS control                      | EC2                  |
| AWS-native containers                | ECS                  |
| Kubernetes                           | EKS                  |
| Containers without server management | Fargate              |
| Store container images               | ECR                  |
| Event-driven function                | Lambda               |
| Managed conventional web app         | Elastic Beanstalk    |

This is probably the most useful table for scenario questions.

---

# 65. Likely subjective question — Explain Amazon EC2

> Amazon EC2 is a compute service that provides virtual machines in the AWS Cloud. Customers launch EC2 instances from AMIs and can select the instance type, networking, IAM role, storage, security groups and key pair according to their requirements. EC2 gives the customer control over the guest operating system, making it suitable for workloads that require server customisation and traditional virtual-machine computing.

---

# 66. Likely subjective question — Explain the EC2 launch decisions

A strong answer:

> When launching an EC2 instance, the customer must make several configuration decisions. The AMI determines the operating-system and starting software environment, while the instance type determines CPU, memory, storage and network capability. Network settings determine where the instance runs, an IAM role grants AWS permissions, user data can automate startup configuration, storage provides persistent or temporary data capacity, tags organise the resource, security groups control network traffic, and the key pair provides secure administrative access.

That paragraph efficiently covers all nine.

---

# 67. Likely subjective question — Explain EC2 pricing models

> Amazon EC2 provides several pricing models for different usage patterns. On-Demand Instances provide flexibility with no long-term commitment and are suited to unpredictable workloads. Reserved Instances provide discounted pricing in exchange for a one-year or three-year commitment and are suited to predictable workloads. Spot Instances can provide substantial cost savings but can be interrupted by AWS, making them suitable for flexible and fault-tolerant workloads. Dedicated Hosts provide an entire physical server and can support licensing or compliance requirements.

---

# 68. Likely subjective question — Explain the four cost-optimisation pillars

> The four EC2 cost-optimisation pillars are right-sizing, increasing elasticity, selecting the optimal pricing model and optimising storage choices. Right-sizing matches instance resources to actual CPU, memory, storage and network needs. Elasticity reduces cost by using resources only when required. The pricing model should match workload behaviour, such as Reserved Instances for predictable workloads and Spot for interruption-tolerant tasks. Storage should also be sized and selected according to actual performance requirements, with unnecessary volumes or snapshots removed.

---

# 69. Likely subjective question — Containers vs VMs

> A virtual machine includes a complete guest operating system for each VM, while containers package applications and their dependencies while sharing more of the underlying operating-system environment. As a result, containers are generally lighter and faster to start. Container orchestration services such as Amazon ECS or Amazon EKS can then manage many containers across compute resources.

---

# 70. Likely subjective question — ECS, EKS, Fargate and ECR

> Amazon ECS is AWS's container orchestration service, while Amazon EKS enables organisations to run Kubernetes on AWS. AWS Fargate provides compute for containers without requiring customers to manage the underlying servers. Amazon ECR is different because it is a managed registry used to store and manage container images. Therefore, ECR stores the images, ECS or EKS orchestrates the containers, and EC2 or Fargate provides the compute capacity where they run.

That answer is extremely useful because it separates four easily confused services.

---

# 71. How to answer a compute scenario

Use this approach:

```text
1. Identify what is being run.
2. Determine how much control is required.
3. Determine whether servers should be managed.
4. Match the service.
5. Justify why alternatives are less appropriate.
```

Example:

> A company needs code to resize an image whenever a file is uploaded to S3. The task only runs for a few seconds, and the company does not want to manage servers.

Weak answer:

> AWS Lambda.

Better answer:

> AWS Lambda is the most appropriate service because it runs code in response to events without requiring the customer to provision servers. The S3 upload can trigger the Lambda function, which can resize the image and finish after processing. EC2 would require a continuously managed virtual machine even though the task only runs when an image is uploaded.

That is the type of justification subjective exams reward.

---

# 72. Scenario practice

### Scenario A

> A company needs complete control over Linux and must install specialised software.

**EC2**

Because EC2 gives guest-OS control.

---

### Scenario B

> The server is required continuously for three years.

**Reserved Instances**

Because usage is predictable and long term.

---

### Scenario C

> A video-rendering job can stop and resume later, and cost is the priority.

**Spot Instances**

Because the workload tolerates interruption.

---

### Scenario D

> A company needs to run containers but does not want to manage EC2 servers.

**AWS Fargate**

---

### Scenario E

> A company already uses Kubernetes.

**Amazon EKS**

---

### Scenario F

> Developers need somewhere to store container images.

**Amazon ECR**

---

### Scenario G

> A file upload should automatically trigger five seconds of processing.

**AWS Lambda**

---

### Scenario H

> Developers want to upload a Java web application while AWS handles infrastructure, scaling and load balancing.

**Elastic Beanstalk**

---

### Scenario I

> An EC2 instance averages 4% CPU utilisation.

**Right-size the instance**

---

### Scenario J

> A development EC2 instance is unused every night.

**Stop/hibernate it when unused to increase elasticity.**

---

# 73. High-priority scenario clues

| If the question says...             | Think...            |
| ----------------------------------- | ------------------- |
| Virtual machine                     | EC2                 |
| Full OS control                     | EC2                 |
| Instance template                   | AMI                 |
| CPU/RAM/network specification       | Instance type       |
| Startup automation                  | User data           |
| AWS permission for EC2              | IAM role            |
| Network firewall                    | Security group      |
| Secure EC2 login                    | Key pair            |
| Persistent public IPv4              | Elastic IP          |
| Instance performance metrics        | CloudWatch          |
| Temporarily turn server off         | Stop                |
| Permanently remove server           | Terminate           |
| Unpredictable workload              | On-Demand           |
| Predictable workload                | Reserved            |
| Interruptible workload              | Spot                |
| Physical server licensing           | Dedicated Host      |
| Underutilised EC2                   | Right-size          |
| Stop unused servers                 | Increase elasticity |
| Containers                          | ECS/EKS             |
| Kubernetes                          | EKS                 |
| No server management for containers | Fargate             |
| Store Docker images                 | ECR                 |
| Event-driven code                   | Lambda              |
| Upload normal web app               | Elastic Beanstalk   |

---

# 74. Common mistakes to avoid

**AMI = EC2 instance.**
Wrong.

```text
AMI → Template
EC2 instance → Running VM
```

**Instance type determines operating system.**
Wrong.

```text
AMI → OS/software
Instance type → CPU/RAM/network/resources
```

**IAM role controls network ports.**
Wrong.

```text
IAM role → AWS permissions
Security group → Network access
```

**User data = stored application data.**
Wrong.

User data is primarily a startup script/configuration mechanism in this module.

**Stop = terminate.**
Wrong.

```text
Stop → Can restart
Terminate → Permanently removed
```

**Spot Instances are best for critical non-interruptible systems.**
Wrong.

They can be interrupted.

**Reserved Instances are always best because they are cheaper.**
Wrong.

They only make sense when the usage is predictable enough to justify commitment.

**ECR runs containers.**
Wrong.

```text
ECR → Stores images
ECS/EKS → Orchestrates
EC2/Fargate → Runs compute
```

**Fargate replaces ECS.**
Wrong.

Fargate can provide compute for containers managed through services such as ECS.

**ECS = Kubernetes.**
Wrong.

```text
ECS → AWS-native
EKS → Kubernetes
```

**Lambda means there are physically no servers.**
Wrong.

AWS manages the servers; the customer does not provision them.

**Lambda is a normal continuously running server.**
Wrong.

It is function-based, event-driven compute.

**Elastic Beanstalk means everything is free.**
Wrong.

The module says there is no additional Beanstalk charge, but underlying AWS resources are still billed. 

---

# 75. What I would prioritise before the subjective exam

If time is short, master these **seven areas**:

```text
1. EC2 basics
   AMI
   Instance type
   User data
   IAM role
   Security group
   Key pair

2. EC2 lifecycle
   Reboot
   Stop
   Terminate

3. EC2 pricing
   On-Demand
   Reserved
   Spot
   Dedicated Host

4. Cost optimisation
   Right-size
   Elasticity
   Pricing model
   Storage

5. Containers
   ECS
   EKS
   Fargate
   ECR

6. Lambda
   Event-driven
   Serverless
   Execution role

7. Elastic Beanstalk
   Web application deployment
   Provisioning
   Scaling
   Load balancing
```

These correspond closely to the formal Module 6 objectives. 

# Final 2-minute revision

```text
COMPUTE CHOICE
──────────────
Full VM control
→ EC2

Container orchestration
→ ECS

Kubernetes
→ EKS

Containers without servers
→ Fargate

Store container images
→ ECR

Event-driven function
→ Lambda

Managed web application
→ Elastic Beanstalk
```

```text
EC2 LAUNCH
──────────
AMI
→ OS/template

Instance type
→ CPU/RAM/network

IAM role
→ AWS permissions

User data
→ Startup script

Storage
→ Data

Tags
→ Labels

Security group
→ Network firewall

Key pair
→ Secure login
```

```text
EC2 LIFECYCLE
─────────────
Reboot
→ Restart

Stop
→ Temporary shutdown

Terminate
→ Permanent removal

Persistent public IP
→ Elastic IP
```

```text
EC2 PRICING
───────────
On-Demand
→ Unpredictable

Reserved
→ Predictable

Spot
→ Interruptible

Dedicated Host
→ Physical host/licensing
```

```text
COST OPTIMISATION
─────────────────
1. Right-size
2. Increase elasticity
3. Optimal pricing model
4. Optimise storage
```

```text
CONTAINERS
──────────
Docker
→ Package application

ECR
→ Store images

ECS
→ AWS-native orchestration

EKS
→ Kubernetes

Fargate
→ Serverless container compute
```

```text
LAMBDA
──────
Event occurs
↓
Function runs
↓
Function finishes

No server provisioning
Pay per use
15-minute maximum runtime in module
```

```text
ELASTIC BEANSTALK
─────────────────
Upload web-app code
↓
AWS provisions infrastructure
↓
Deployment
Load balancing
Scaling
Monitoring
```

The **single most important mental model** for Module 6 is:

```text
EC2
→ "Give me the SERVER and let me control it."

CONTAINERS
→ "Package my APPLICATION consistently."

FARGATE
→ "Run my CONTAINERS without me managing servers."

LAMBDA
→ "Run this CODE when something happens."

ELASTIC BEANSTALK
→ "Deploy my WEB APPLICATION and manage much of the environment for me."
```

Once you can distinguish those five ideas and justify them from a scenario, most of the difficult subjective questions in Module 6 become much easier. 

</details>


<details>
<summary><strong>Module 7: Storage — Subjective Exam Preparation</strong></summary>

For a **subjective exam**, Module 7 is mainly testing whether you can look at a storage requirement and decide:

> **What kind of storage does this workload need, and which AWS storage service fits that behaviour best?**

The module focuses on four services:

```text
Amazon EBS        → Block storage
Amazon S3         → Object storage
Amazon EFS        → Shared file storage
Amazon S3 Glacier → Long-term archival storage
```

Its objectives specifically include identifying storage types, explaining the functionality of EBS, S3, EFS and S3 Glacier, and differentiating between them. 

The entire chapter can be remembered as:

```text
Need a virtual disk?
→ EBS

Need to store complete objects/files?
→ S3

Need several Linux servers to share the same files?
→ EFS

Need cheap long-term archives?
→ S3 Glacier
```

---

# 1. First understand the three main storage models

Before memorising AWS services, understand **how the data is stored**.

```text
Block storage  → Amazon EBS
Object storage → Amazon S3
File storage   → Amazon EFS

Archival object storage → Amazon S3 Glacier
```

This is probably the most important distinction in the module.

---

# 2. Block storage

**Block storage** divides data into small blocks.

The operating system can treat the storage like a disk.

Suppose there is a 1 GB file and you change one character.

With block storage:

```text
1 GB file
↓
Locate the affected block
↓
Change that block
```

The module's page 7 diagram explicitly contrasts this with object storage: block storage can update the relevant piece rather than replacing the whole object. 

### Typical uses

Think:

* operating-system disks;
* database disks;
* applications that frequently modify data;
* EC2 boot volumes.

AWS service:

> **Amazon EBS**

---

# 3. Object storage

With **object storage**, a file is stored as an object rather than as a series of directly editable disk blocks.

Conceptually:

```text
Object
├── Data
├── Metadata
└── Unique key
```

If the object changes, the object is generally replaced as a complete object in the model taught by the module.

Typical examples:

```text
photo.jpg
video.mp4
report.pdf
backup.zip
```

AWS service:

> **Amazon S3**

---

# 4. File storage

**File storage** behaves more like a shared network folder.

It presents:

```text
/folder
   /subfolder
      file.txt
      report.pdf
```

Several computers can access the same files through a file-system protocol.

AWS service:

> **Amazon EFS**

---

# 5. The easiest storage-type comparison

| Requirement             | Storage type    | AWS service |
| ----------------------- | --------------- | ----------- |
| Disk attached to EC2    | Block           | EBS         |
| Photos, videos, backups | Object          | S3          |
| Shared Linux folder     | File            | EFS         |
| Long-term rare archive  | Archival object | S3 Glacier  |

This table alone answers a surprising number of scenario questions.

---

# Section 1 — Amazon EBS

# 6. What is Amazon EBS?

**Amazon Elastic Block Store (EBS)** provides block-level storage volumes that can be attached to Amazon EC2 instances.

The module says EBS volumes are:

* block-level storage;
* automatically replicated within their Availability Zone;
* usable for EC2 boot volumes;
* suitable for file systems;
* suitable for database hosts;
* suitable for enterprise applications. 

Think:

> **EBS = virtual hard disk for EC2.**

---

# 7. Good subjective answer — Amazon EBS

> Amazon EBS provides persistent block-level storage volumes for Amazon EC2 instances. An EBS volume behaves similarly to a virtual hard disk and can be used for operating-system boot volumes, databases, file systems and enterprise applications. EBS volumes are replicated within their Availability Zone and can be backed up using snapshots.

---

# 8. EBS persists independently of EC2

One very important property:

> **An EBS volume persists independently from the EC2 instance.**

The module states that EBS volumes persist independently and are billed based on the amount of storage provisioned. 

So:

```text
EC2 instance stops
↓
EBS volume remains
↓
Instance starts again
↓
Data can still be there
```

This links back to Module 6:

```text
EBS → Persistent
Instance Store → Ephemeral
```

---

# 9. EBS is Availability-Zone based

An EBS volume belongs to an Availability Zone.

Think:

```text
Availability Zone A
├── EC2 instance
└── EBS volume
```

This is why EBS is different from services like S3, where data is redundantly stored across facilities in a Region.

A common exam trap is assuming an EBS volume itself is a multi-AZ shared disk.

It is not.

---

# 10. EBS volume types

The module divides EBS into four main types:

```text
SSD
├── General Purpose
└── Provisioned IOPS

HDD
├── Throughput-Optimized
└── Cold
```



For a subjective exam, choosing among these four is more important than memorising the old numeric limits shown in the 2022 slides.

---

# 11. General Purpose SSD

The module describes **General Purpose SSD** as recommended for most workloads.

Typical examples include:

* system boot volumes;
* virtual desktops;
* low-latency interactive applications;
* development;
* testing. 

Think:

```text
Ordinary workload
→ General Purpose SSD
```

### Scenario

> “A company needs a normal boot disk for a web server.”

Answer:

**General Purpose SSD**

---

# 12. Provisioned IOPS SSD

Use **Provisioned IOPS SSD** when the workload requires high and consistent I/O performance.

The module associates it with:

* critical business applications;
* sustained IOPS;
* large database workloads. 

Think:

```text
High-performance database
→ Provisioned IOPS SSD
```

### Good answer

> Provisioned IOPS SSD is intended for critical workloads that require consistently high input/output operations, such as large databases or business-critical applications. The required IOPS performance can be provisioned according to workload needs.

---

# 13. What is IOPS?

**IOPS** means:

> **Input/output operations per second.**

It measures:

```text
How many storage operations
can be completed each second?
```

Think of a database performing:

```text
Read customer
Update balance
Write order
Read inventory
Write transaction
```

Many small operations mean IOPS matters.

---

# 14. Throughput

**Throughput** asks:

> **How much data can move per second?**

Imagine reading one enormous log file.

```text
500 GB log
↓
Sequentially stream data
```

The concern is less about thousands of tiny operations and more about how much data can pass through the storage.

Memory:

```text
IOPS
→ How many operations?

Throughput
→ How much data?
```

This distinction is highly useful for choosing EBS types.

---

# 15. Throughput-Optimized HDD

The module associates **Throughput-Optimized HDD** with:

* streaming workloads;
* big data;
* data warehouses;
* log processing;
* consistent high throughput at low cost.

It cannot be used as a boot volume in the module. 

Think:

```text
Large sequential data
→ Throughput-Optimized HDD
```

### Scenario

> “A company processes very large log files sequentially.”

Answer:

**Throughput-Optimized HDD**

---

# 16. Cold HDD

**Cold HDD** is intended for large volumes of infrequently accessed data where low storage cost matters.

The module also says it cannot be used as a boot volume. 

Think:

```text
Rarely accessed
+
Large HDD workload
+
Lowest EBS storage cost important
→ Cold HDD
```

Do not confuse this with Glacier.

```text
Cold HDD → Still an EBS disk
Glacier  → Archive object storage
```

---

# 17. EBS volume type decision table

| Requirement                             | EBS type                 |
| --------------------------------------- | ------------------------ |
| Most workloads / boot volume            | General Purpose SSD      |
| Critical high-IOPS database             | Provisioned IOPS SSD     |
| Big data / logs / sequential throughput | Throughput-Optimized HDD |
| Rarely accessed low-cost HDD data       | Cold HDD                 |

Memory:

```text
Normal       → General Purpose
Database     → Provisioned IOPS
Big streams  → Throughput-Optimized
Cold data    → Cold HDD
```

---

# 18. EBS snapshots

An **EBS snapshot** is a **point-in-time backup** of an EBS volume.

The module says snapshots can be used to recreate a new volume later. 

Think:

```text
EBS volume
↓
Snapshot
↓
Point-in-time backup
↓
Create new EBS volume later
```

### Analogy

An EBS volume is the room.

The snapshot is a photograph of the room.

The photo tells you what the room looked like at that moment.

It is not the room itself.

---

# 19. Snapshot vs volume

This is a very common confusion:

```text
EBS volume
→ Active storage used by EC2

EBS snapshot
→ Point-in-time backup
```

### Subjective answer

> An EBS volume is active block storage that can be attached to an EC2 instance. An EBS snapshot is a point-in-time backup of that volume that can later be used to create a new EBS volume.

---

# 20. EBS encryption

The module identifies encryption as an EBS feature and states that encrypted EBS volumes do not carry an additional encryption charge in the course material. 

For subjective purposes:

> Encryption protects data stored on the volume from unauthorised access when the proper key or permissions are not available.

You do not need to overcomplicate this if the question is specifically from Module 7.

---

# 21. EBS elasticity

EBS storage can be changed as requirements change.

The module says EBS supports:

```text
Increase capacity
Change to another volume type
```



Example:

```text
100 GB General Purpose SSD
↓ workload changes
Increase capacity
or
Change storage type
```

This is why the service includes the word **Elastic**.

---

# 22. EBS pricing

The module explains that EBS charges can depend on:

* provisioned storage;
* provisioned IOPS for relevant volume types;
* snapshots;
* cross-Region outbound transfer. 

The key exam principle:

> EBS volume cost is based on **provisioned capacity**, not merely the amount of data you happened to write.

Example:

```text
Provisioned:
500 GB

Used:
100 GB
```

The provisioned amount still matters for billing.

---

# Section 2 — Amazon S3

# 23. What is Amazon S3?

**Amazon Simple Storage Service (S3)** is a fully managed **object-storage service**.

The module states:

* data is stored as objects in buckets;
* storage is virtually unlimited;
* an individual object is limited to 5 TB in the course material;
* S3 is designed for **11 nines of durability**;
* access can be controlled at bucket and object level. 

Think:

> **S3 = enormous cloud warehouse for objects.**

---

# 24. Bucket vs object

An **S3 bucket** is the container.

An **object** is the actual stored item.

```text
my-company-bucket
├── photo.jpg
├── report.pdf
├── video.mp4
└── backup.zip
```

So:

```text
Bucket
→ Container

Object
→ Stored file/data + metadata + key
```

---

# 25. Good subjective answer — Amazon S3

> Amazon S3 is a fully managed object-storage service that stores data as objects inside buckets. It provides virtually unlimited storage and is designed for very high durability. S3 is suitable for use cases such as backups, application assets, static website content, media files, software distribution and big-data staging.

The module lists these common S3 scenarios directly. 

---

# 26. S3 durability

The module says S3 is designed for:

```text
99.999999999% durability
```

or:

> **11 nines of durability.**



Do not confuse:

```text
Durability
→ Will the data survive?

Availability
→ Can I access it right now?
```

These are related but different ideas.

---

# 27. S3 data redundancy

The module's page 26 diagram shows S3 data being redundantly stored across facilities within the selected Region. 

Conceptually:

```text
S3 object
↓
Facility 1
Facility 2
Facility 3
within Region
```

So S3 is different from an EBS volume that belongs to one Availability Zone.

---

# 28. Common S3 use cases

The module gives examples including:

* application assets;
* static web hosting;
* backup and disaster recovery;
* big-data staging;
* media hosting;
* software delivery. 

Scenario:

> “A website needs somewhere to store millions of customer photos and videos.”

Think:

**S3**

---

# 29. Why S3 is not EBS

Suppose a database constantly modifies small portions of a large database file.

That behaves like a disk workload.

Use:

> **EBS**

Suppose a customer uploads:

```text
holiday.jpg
```

and you want to store and retrieve that complete object.

Use:

> **S3**

Memory:

```text
Frequently modify parts of a disk
→ EBS

Store/retrieve complete objects
→ S3
```

---

# 30. S3 storage classes

The module lists six storage classes:

1. S3 Standard
2. S3 Intelligent-Tiering
3. S3 Standard-Infrequent Access
4. S3 One Zone-Infrequent Access
5. S3 Glacier
6. S3 Glacier Deep Archive 

The entire purpose of these classes is to match **cost with access pattern**.

---

# 31. S3 Standard

Use **S3 Standard** for frequently accessed data.

Think:

```text
Website images
Active application files
Frequently downloaded content
```

Scenario:

> “Users access these objects every day.”

Answer:

**S3 Standard**

---

# 32. S3 Intelligent-Tiering

Use **S3 Intelligent-Tiering** when the access pattern is uncertain or changes over time.

Example:

```text
Month 1 → Frequently accessed
Month 4 → Rarely accessed
Month 8 → Frequently accessed again
```

Think:

> “We genuinely don't know whether this data will be hot or cold.”

→ **Intelligent-Tiering**

---

# 33. S3 Standard-IA

**IA** means **Infrequent Access**.

Use S3 Standard-IA when:

* data is accessed rarely;
* but when it is needed, it still needs rapid access.

Think:

```text
Rarely accessed
+
Fast retrieval still needed
→ Standard-IA
```

Typical example:

> Backup files that are normally untouched but must be restored rapidly if something goes wrong.

---

# 34. Standard-IA is NOT Glacier

This is a very important exam distinction.

```text
S3 Standard-IA
→ Infrequent access
→ Rapid retrieval

S3 Glacier
→ Archive
→ Retrieval may take minutes or hours
```

“Infrequent access” does **not automatically mean Glacier**.

Always ask:

> **How quickly must the data be retrieved?**

---

# 35. S3 One Zone-IA

S3 One Zone-IA is for infrequently accessed data where:

* lower cost matters;
* one Availability Zone is acceptable;
* the data can be recreated.

Think:

```text
Secondary/recreatable copy
+
Rarely accessed
+
One AZ acceptable
→ One Zone-IA
```

Do not use this reasoning for the only existing copy of irreplaceable data.

---

# 36. S3 Glacier and Deep Archive

The module lists both as archival classes.

Think:

```text
Archive
→ Glacier

Very deep / very long-term archive
→ Glacier Deep Archive
```

The general trade-off is:

```text
Less frequent access
↓
Lower storage cost
↓
Slower / more expensive retrieval
```

---

# 37. S3 storage-class scenario table

| Requirement                          | Storage class           |
| ------------------------------------ | ----------------------- |
| Frequently accessed                  | S3 Standard             |
| Access pattern unpredictable         | S3 Intelligent-Tiering  |
| Rarely accessed but rapid retrieval  | S3 Standard-IA          |
| Rare, recreatable, one AZ acceptable | S3 One Zone-IA          |
| Long-term archive                    | S3 Glacier              |
| Deep long-term archive               | S3 Glacier Deep Archive |

This is worth memorising.

---

# 38. S3 pricing factors

The module identifies four main cost factors:

```text
1. Storage class
2. Amount of storage
3. Requests
4. Data transfer
```



This is important because:

> **S3 pricing is not only “how many GB are stored.”**

---

# 39. S3 request pricing

The module states that request types can affect cost, including:

```text
PUT
COPY
POST
LIST
GET
```



So even a bucket storing a modest amount of data could still generate cost from millions of requests.

---

# 40. S3 data transfer

According to the module:

```text
Transfer IN to S3
→ Free

Transfer OUT of the S3 Region
→ Can incur charges
```

The module also states there is no transfer charge in its examples for S3 to CloudFront or EC2 in the same Region. 

For the exam, use the wording taught by this course.

---

# Section 3 — Amazon EFS

# 41. What is Amazon EFS?

**Amazon Elastic File System (EFS)** provides shared file storage over a network.

The module states that EFS:

* provides file storage in AWS;
* supports shared storage;
* supports NFS 4.0 and 4.1;
* works with Linux-based EC2 AMIs;
* can scale to petabyte size;
* has elastic capacity;
* is useful for web serving, content management, media processing, analytics and home directories. 

Think:

> **EFS = shared network folder for Linux EC2 instances.**

---

# 42. The easiest EFS example

Suppose three EC2 servers need the exact same files.

```text
EC2 A ─┐
EC2 B ─┼── EFS
EC2 C ─┘
```

All of them can access the same shared file system.

This is the core reason EFS exists.

---

# 43. Why separate EBS volumes do not solve the same problem

Suppose:

```text
EC2 A → EBS A
EC2 B → EBS B
EC2 C → EBS C
```

You now have three separate disks.

They are not automatically one shared folder.

If the question says:

> “All instances need the same shared files.”

Think:

**EFS**, not “give everybody their own EBS volume and hope the files achieve telepathy.”

---

# 44. What is NFS?

EFS supports **Network File System (NFS) 4.0 and 4.1** according to the module. 

NFS allows a remote file system to appear like a normal mounted directory.

Example:

```text
Amazon EFS
↓ NFS
/mnt/shared
```

Applications can then work with normal files and folders.

---

# 45. EFS mount targets

The module's EFS architecture shows **mount targets** inside VPC subnets.

A mount target is:

> A network access point that EC2 instances use to reach the EFS file system.



Important:

```text
EFS file system
→ The actual shared files

Mount target
→ Network entrance to those files
```

A mount target is **not a second EFS file system**.

---

# 46. EFS and Availability Zones

The module states:

* mount targets are created in VPC subnets;
* normally one is created per Availability Zone;
* they must be in the same VPC. 

Conceptually:

```text
AZ A → Mount target ┐
AZ B → Mount target ├── One EFS file system
AZ C → Mount target ┘
```

This allows EC2 instances in multiple AZs to access the same EFS file system.

---

# 47. EFS automatically scales

EFS capacity grows and shrinks as files are added or removed.

The module says:

```text
Add files
→ Storage grows

Remove files
→ Storage shrinks

Pay for what you use
```



This is a major difference from EBS, where you provision a volume size.

---

# 48. Good subjective answer — Amazon EFS

> Amazon EFS is a fully managed shared file-storage service. It allows multiple Linux-based EC2 instances to access the same files through the NFS protocol. EFS uses mount targets in VPC subnets to provide network access to the file system and automatically scales its storage capacity as files are added or removed. It is suitable for workloads such as web serving, content management, media processing, analytics and shared home directories.

---

# 49. EFS vs EBS

| EBS                  | EFS                                      |
| -------------------- | ---------------------------------------- |
| Block storage        | File storage                             |
| Behaves like disk    | Behaves like shared folder               |
| EC2 storage volume   | Shared across multiple EC2 instances     |
| Capacity provisioned | Capacity scales automatically            |
| AZ-based volume      | Network file system across mount targets |

Memory:

```text
Need a disk
→ EBS

Need a shared folder
→ EFS
```

---

# 50. EFS vs S3

| EFS                         | S3                              |
| --------------------------- | ------------------------------- |
| File system                 | Object storage                  |
| Files/folders               | Buckets/objects                 |
| Mounted through NFS         | Accessed as objects             |
| Shared Linux workloads      | Massive scalable object storage |
| Traditional file operations | Object operations/API access    |

Scenario:

> “Application expects `/shared/uploads/photo.jpg` to exist as a mounted file.”

Think:

**EFS**

Scenario:

> “Application stores millions of uploaded images as objects.”

Think:

**S3**

---

# Section 4 — Amazon S3 Glacier

# 51. What is Amazon S3 Glacier?

The module describes S3 Glacier as a storage service designed for:

* security;
* durability;
* extremely low cost;
* low-cost data archiving;
* long-term backup. 

Think:

> **Glacier = archive warehouse.**

You put data there because you want to keep it, not because you expect to read it every five minutes.

---

# 52. Typical Glacier scenarios

Think:

```text
Legal records
Historical backups
Old media
Compliance data
Long-term records
```

The strongest keyword is:

> **Archive**

If the question says:

> “Stored for ten years and almost never accessed.”

Glacier should immediately come to mind.

---

# 53. Glacier durability and security

The module states Glacier is designed for **11 nines durability** and supports encryption in transit and at rest. It also introduces **Vault Lock** for enforcing compliance policies. 

For a subjective answer:

> Glacier combines low-cost archival storage with durability and security controls for long-term data retention.

---

# 54. Glacier retrieval options

The 2022 module gives three retrieval choices:

| Retrieval option | Time stated in module |
| ---------------- | --------------------: |
| **Expedited**    |           1–5 minutes |
| **Standard**     |             3–5 hours |
| **Bulk**         |            5–12 hours |



For an exam based on these slides, use these module values.

---

# 55. Glacier retrieval logic

Think:

```text
Urgent archive retrieval
→ Expedited

Normal retrieval
→ Standard

Large, non-urgent retrieval
→ Bulk
```

General trade-off:

```text
Faster retrieval
→ More expensive

Slower retrieval
→ Lower cost
```

---

# 56. S3 vs Glacier

The module compares S3 and S3 Glacier directly:

```text
S3
→ Millisecond-scale active object access
→ Higher storage cost

Glacier
→ Minutes/hours archive retrieval
→ Lower storage cost
```



The key distinction is:

```text
S3
→ Active objects

Glacier
→ Archive
```

---

# 57. Lifecycle policies

The module explains that S3 content can automatically be moved into Glacier using lifecycle archiving.

Example shown:

```text
S3 object
↓ after 30 days
Glacier archive
↓ after 5 years
Delete
```



This is extremely useful for cost optimisation.

---

# 58. Why lifecycle rules matter

Suppose CCTV footage is heavily accessed only for 30 days.

Keeping seven years of footage in expensive frequently accessed storage is wasteful.

A lifecycle design might be:

```text
Recent data
→ S3 Standard

Older data
→ Lower-cost storage

Archive
→ Glacier

Retention ends
→ Delete
```

### Good answer

> S3 lifecycle policies can automatically move objects between storage classes or archive them into S3 Glacier according to age. This helps organisations reduce storage cost while enforcing retention policies without manually moving every object.

---

# 59. Likely subjective question — Differentiate EBS, S3, EFS and Glacier

A strong answer:

> Amazon EBS provides block-level storage volumes primarily for EC2 instances and behaves like a virtual disk, making it suitable for boot volumes and databases. Amazon S3 provides highly scalable object storage for files such as images, backups and application assets. Amazon EFS provides a shared network file system that multiple Linux EC2 instances can access through NFS. Amazon S3 Glacier is designed for low-cost long-term archival data that is rarely accessed and can tolerate slower retrieval.

That is probably the single most useful paragraph in Module 7.

---

# 60. Likely subjective question — EBS volume types

> Amazon EBS provides both SSD and HDD volume types. General Purpose SSD is recommended for most workloads and boot volumes. Provisioned IOPS SSD is designed for critical applications and large databases requiring sustained high IOPS. Throughput-Optimized HDD is suited to large sequential workloads such as logs, big data and data warehouses, while Cold HDD is intended for infrequently accessed throughput-oriented data where low cost is important.

---

# 61. Likely subjective question — EBS snapshots

> An EBS snapshot is a point-in-time backup of an EBS volume. Snapshots can be used to recreate new EBS volumes and therefore support backup and recovery. A snapshot is different from an active EBS volume because the volume is the storage attached to an EC2 instance, while the snapshot is a backup representation of that storage.

---

# 62. Likely subjective question — S3 storage classes

A concise full answer:

> Amazon S3 provides several storage classes to match different access patterns. S3 Standard is intended for frequently accessed objects. S3 Intelligent-Tiering is suitable when access patterns are uncertain or changing. S3 Standard-IA is for infrequently accessed objects that still require rapid retrieval, while One Zone-IA is a lower-cost option for infrequently accessed recreatable data that can be stored in one Availability Zone. S3 Glacier and Glacier Deep Archive are designed for long-term archival storage.

---

# 63. Likely subjective question — Explain EFS

> Amazon EFS provides managed shared file storage for Linux-based EC2 instances. It supports NFS and enables multiple instances to access the same files simultaneously. Mount targets provide network access to the EFS file system from VPC subnets, and EFS automatically grows and shrinks as files are added or removed.

---

# 64. Likely subjective question — Standard-IA vs Glacier

> S3 Standard-IA is designed for objects that are accessed infrequently but still require rapid retrieval when needed. S3 Glacier is intended for long-term archival data and offers lower storage cost in exchange for slower retrieval that may take minutes or hours. Therefore, Standard-IA is more suitable when occasional immediate access is required, while Glacier is more appropriate when data is archived and retrieval speed is less important.

---

# 65. How to answer storage scenario questions

Use this sequence:

```text
1. Ask how the data must be accessed.
2. Decide storage type.
3. Consider performance.
4. Consider access frequency.
5. Consider whether multiple instances share it.
6. Consider retrieval-time requirements.
7. Choose the service/class and justify it.
```

Example:

> Several Linux EC2 instances need simultaneous access to the same uploaded files.

Weak answer:

> EFS.

Better answer:

> Amazon EFS is the best choice because it provides shared network file storage that multiple Linux EC2 instances can mount and access through NFS. Separate EBS volumes would provide independent block devices rather than one common shared file system.

---

# 66. Scenario practice

### Scenario A

> An EC2 instance needs a boot disk.

**Amazon EBS — General Purpose SSD**

Because EBS provides block storage and General Purpose SSD is recommended for most workloads and boot volumes.

---

### Scenario B

> A critical database needs sustained high I/O operations.

**Provisioned IOPS SSD**

Because the workload is IOPS-sensitive.

---

### Scenario C

> A company processes huge sequential log files.

**Throughput-Optimized HDD**

Because the workload is throughput-oriented.

---

### Scenario D

> A company stores millions of uploaded photos.

**Amazon S3**

Because photos are naturally stored as objects.

---

### Scenario E

> The access pattern of objects changes unpredictably.

**S3 Intelligent-Tiering**

---

### Scenario F

> Backup files are rarely accessed, but when needed they must be available rapidly.

**S3 Standard-IA**

Not Glacier, because rapid retrieval is important.

---

### Scenario G

> An infrequently used secondary copy can be recreated and only one AZ is required.

**S3 One Zone-IA**

---

### Scenario H

> Multiple Linux EC2 instances need the same shared directory.

**Amazon EFS**

---

### Scenario I

> Financial records must be retained for many years and almost never accessed.

**Amazon S3 Glacier**

---

### Scenario J

> A Glacier archive is urgently required within minutes.

**Expedited retrieval**, using the module's retrieval options.

---

# 67. High-priority scenario clues

| Question says...                   | Think...                 |
| ---------------------------------- | ------------------------ |
| Virtual disk                       | EBS                      |
| EC2 boot volume                    | EBS                      |
| Database disk                      | EBS                      |
| High IOPS                          | Provisioned IOPS SSD     |
| Big sequential logs                | Throughput-Optimized HDD |
| Rarely accessed EBS data           | Cold HDD                 |
| Point-in-time backup               | EBS snapshot             |
| Photos/videos/objects              | S3                       |
| Bucket                             | S3                       |
| 11 nines durability                | S3 / Glacier in module   |
| Frequent object access             | S3 Standard              |
| Unknown access pattern             | Intelligent-Tiering      |
| Rare + rapid retrieval             | Standard-IA              |
| Rare + recreatable + one AZ        | One Zone-IA              |
| Shared Linux files                 | EFS                      |
| NFS                                | EFS                      |
| Multiple EC2 instances same folder | EFS                      |
| Mount target                       | EFS                      |
| Long-term archive                  | Glacier                  |
| Minutes/hours retrieval            | Glacier                  |
| Automatically archive old S3 data  | Lifecycle policy         |

---

# 68. Common mistakes to avoid

**EBS is object storage.**
Wrong.

```text
EBS → Block
S3  → Object
```

---

**S3 behaves like a traditional EC2 disk.**
Wrong.

S3 stores objects.

---

**EFS is object storage.**
Wrong.

```text
EFS → File storage
```

---

**A snapshot is a running EBS disk.**
Wrong.

```text
Volume   → Active storage
Snapshot → Backup
```

---

**Every infrequently accessed object belongs in Glacier.**
Wrong.

Ask whether **rapid retrieval** is required.

```text
Rare + rapid
→ Standard-IA

Archive + slower retrieval acceptable
→ Glacier
```

---

**Provisioned IOPS is always the best EBS volume because it is fastest.**
Wrong.

General Purpose SSD is recommended for most workloads in the module.

---

**Throughput and IOPS are the same thing.**
Wrong.

```text
IOPS
→ Number of operations

Throughput
→ Amount of data
```

---

**Cold HDD and Glacier are the same.**
Wrong.

```text
Cold HDD
→ EBS disk

Glacier
→ Archival object storage
```

---

**Several EBS disks automatically create shared storage.**
Wrong.

Use **EFS** when multiple Linux EC2 instances need the same shared file system.

---

**Each EFS mount target is a separate file system.**
Wrong.

Mount targets are network access points to **one EFS file system**.

---

**Glacier is designed for frequently accessed application files.**
Wrong.

It is for archival data.

---

# 69. What I would prioritise before the subjective exam

If time is short, master these seven areas:

```text
1. Storage types
   Block → EBS
   Object → S3
   File → EFS
   Archive → Glacier

2. EBS types
   General Purpose
   Provisioned IOPS
   Throughput-Optimized
   Cold

3. IOPS vs throughput

4. EBS snapshots

5. S3 classes
   Standard
   Intelligent-Tiering
   Standard-IA
   One Zone-IA
   Glacier
   Deep Archive

6. EFS
   Shared
   Linux
   NFS
   Mount targets

7. Glacier
   Archive
   Lifecycle
   Retrieval options
```

These align directly with the Module 7 learning objectives. 

# Final 2-minute revision

```text
STORAGE TYPE
────────────
EBS
→ Block
→ Disk

S3
→ Object
→ Bucket

EFS
→ File
→ Shared folder

Glacier
→ Archive
```

```text
EBS TYPES
─────────
General Purpose SSD
→ Most workloads / boot

Provisioned IOPS SSD
→ High-performance database

Throughput-Optimized HDD
→ Big sequential data / logs

Cold HDD
→ Rarely accessed low-cost HDD
```

```text
PERFORMANCE
───────────
IOPS
→ How many operations?

Throughput
→ How much data?
```

```text
EBS BACKUP
──────────
Volume
→ Active disk

Snapshot
→ Point-in-time backup
```

```text
S3 CLASSES
──────────
Standard
→ Frequent

Intelligent-Tiering
→ Unknown/changing access

Standard-IA
→ Rare + rapid retrieval

One Zone-IA
→ Rare + recreatable + one AZ

Glacier
→ Archive

Deep Archive
→ Deep archive
```

```text
EFS
───
Shared network file system
Linux EC2
NFS 4.0 / 4.1
Mount targets in subnets
Automatically scales
```

```text
GLACIER
───────
Long-term archival
Low storage cost

Expedited → 1–5 min
Standard  → 3–5 hr
Bulk      → 5–12 hr

Lifecycle:
S3 → Glacier → Delete
```

The **single most important mental model** in Module 7 is:

```text
EBS
→ "I need a DISK."

S3
→ "I need to store OBJECTS."

EFS
→ "My servers need the same SHARED FILES."

GLACIER
→ "I need to KEEP this for a long time,
   but I probably won't OPEN it often."
```

Once you can identify those four behaviours from a scenario, most Module 7 subjective questions become much easier. 

</details>

<details>
<summary><strong>Module 8: Databases — Subjective Exam Preparation</strong></summary>

For a **subjective exam**, Module 8 is mainly testing whether you can look at a database requirement and decide:

> **What kind of database workload is this, and which AWS database service best fits it?**

The module focuses on four services:

```text
Amazon RDS      → Managed relational databases
Amazon DynamoDB → Fast and flexible NoSQL
Amazon Redshift → Data warehouse / analytics
Amazon Aurora   → High-performance relational database
```

The module objectives specifically require you to explain RDS, DynamoDB, Redshift and Aurora and understand their functionality. 

The entire chapter can be reduced to this decision:

```text
Relationships + SQL + transactions?
→ RDS

Massive key-value/document data?
→ DynamoDB

Historical analytics / data warehouse?
→ Redshift

High-performance MySQL/PostgreSQL-compatible relational DB?
→ Aurora

Need full operating-system control?
→ Database on EC2
```

---

# 1. First understand the database problem

Not all data should be stored in the same type of database.

Imagine an online shop.

It has:

```text
Customers
Orders
Payments
Products
```

These records have relationships.

For example:

```text
Customer
   ↓ places
Order
   ↓ contains
Product
```

A **relational database** makes sense.

But suppose the company also stores millions of user sessions where the application simply wants:

```text
GET User123
PUT User123
```

It may prefer a highly scalable NoSQL database such as DynamoDB.

And if management wants to analyse:

```text
10 years of sales
across
500 million transactions
```

that is a different workload again.

Use:

> **Redshift**

The main lesson of Module 8 is therefore:

> **Use the right database for the right job.**

Page 54 of the module makes exactly this point. 

---

# 2. Relational databases

A relational database stores structured data in **tables**.

Example:

### Customers

| CustomerID | Name  |
| ---------- | ----- |
| C001       | Amir  |
| C002       | Sarah |

### Orders

| OrderID | CustomerID | Amount |
| ------- | ---------- | -----: |
| O101    | C001       |  RM200 |
| O102    | C001       |  RM450 |

The relationship is:

```text
Customers.CustomerID
        ↓
Orders.CustomerID
```

Relational databases are useful when:

* relationships matter;
* structured schemas matter;
* SQL queries are required;
* transactions must remain consistent.

AWS services in this module:

```text
Amazon RDS
Amazon Aurora
```

---

# 3. NoSQL databases

NoSQL databases are more flexible in how records are structured.

One record might contain:

```text
UserID
Name
Country
```

while another has:

```text
UserID
Name
Country
Subscription
PreferredDevice
```

That flexibility is one of DynamoDB's characteristics: items in the same table can have different attributes. 

Think:

```text
Relational
→ Strong structure and relationships

NoSQL
→ Flexible structure and massive scalable access
```

---

# Section 1 — Amazon RDS

# 4. What is Amazon RDS?

**Amazon Relational Database Service (RDS)** is a managed service for setting up and operating relational databases in AWS.

The module's central definition is:

> RDS is a managed service that sets up and operates a relational database in the cloud. 

Think:

> **RDS = AWS manages much of the database infrastructure for you.**

---

# 5. Why use a managed database?

Running a relational database yourself involves work such as:

```text
Installing operating system
Patching operating system
Installing database software
Patching database software
Backups
High availability
Scaling
Server maintenance
Physical infrastructure
```

The module describes these as challenges of traditional relational database management. 

RDS removes much of that operational burden.

---

# 6. Managed vs unmanaged

The module contrasts:

```text
UNMANAGED

You manage:
Scaling
Fault tolerance
Availability
```

with:

```text
MANAGED

These capabilities are
typically built into the service
```



An intuitive example:

### Database on EC2

You have more control.

But you also manage much more yourself.

### Amazon RDS

AWS manages more of the underlying database environment.

---

# 7. Who manages what in RDS?

This is highly examinable.

According to the course's RDS responsibility slide:

### Customer manages

```text
Application optimisation
```

### AWS manages

```text
OS installation and patches
Database software installation and patches
Database backups
High availability
Scaling
Physical power/racking
Server maintenance
```



### Good subjective answer

> Amazon RDS is a managed relational database service. AWS manages infrastructure-related tasks such as operating-system installation and patching, database software installation and patching, backups, high availability, scaling and server maintenance. The customer remains responsible for areas such as application optimisation.

---

# 8. RDS vs database on EC2

This is a good scenario comparison.

| Database on EC2                       | Amazon RDS                         |
| ------------------------------------- | ---------------------------------- |
| Customer manages OS                   | AWS manages OS                     |
| Customer installs DB                  | AWS manages installation           |
| Customer patches DB                   | AWS manages patching               |
| Customer designs backups              | RDS provides managed backups       |
| More infrastructure control           | Less infrastructure administration |
| Useful if OS/custom features required | Good managed relational solution   |

Page 54 specifically states that if the workload requires operating-system access or application/database features unsupported by AWS database services, running the database on **Amazon EC2** may be appropriate. 

---

# 9. Good subjective answer — RDS vs EC2

> Running a database on Amazon EC2 provides greater control because the customer can access the operating system and customise the database environment. However, the customer must manage activities such as patching, backups and high availability. Amazon RDS is a managed relational database service in which AWS manages much of this operational work. Therefore, RDS is preferable when reduced administration is desired, while EC2 is more suitable when full operating-system access or unsupported custom features are required.

---

# 10. RDS database engines

The module lists several RDS engines:

```text
MySQL
Amazon Aurora
Microsoft SQL Server
PostgreSQL
MariaDB
Oracle
```



For the exam, the important idea is:

> RDS is **not one database engine**.

RDS is the managed service that supports several relational database engines.

---

# 11. RDS DB instance

An RDS DB instance consists conceptually of three main decisions:

```text
Database engine
+
DB instance class
+
Storage
```

The module says the instance class determines:

```text
CPU
Memory
Network performance
```

while storage choices include options such as:

```text
Magnetic
General Purpose SSD
Provisioned IOPS
```



---

# 12. RDS inside a VPC

The page 12 architecture is very useful.

It shows:

```text
Internet users
      ↓
EC2 application
in public subnet
      ↓
Amazon RDS
in private subnet
```



This makes sense because:

> Users normally connect to the **application**, not directly to the database.

The database can remain protected in the private part of the VPC.

---

# 13. Good architecture explanation

A subjective answer could say:

> An application server can be placed in a public subnet so that users can access the application, while the Amazon RDS database is placed in a private subnet. The application communicates with the database internally, reducing the need for the database itself to be directly accessible from the internet.

This also connects Module 8 to what you learned in Module 5.

---

# 14. RDS Multi-AZ

**Multi-AZ deployment** is about:

> **High availability.**

The module diagram shows:

```text
Availability Zone 1
Primary RDS instance
        ↓
Synchronous replication
        ↓
Availability Zone 2
Standby RDS instance
```



The important keywords:

```text
Primary
Standby
Different Availability Zones
Synchronous replication
High availability
```

---

# 15. Why Multi-AZ helps

Suppose the primary database fails.

Without a standby:

```text
Primary fails
↓
Database unavailable
```

With Multi-AZ:

```text
Primary fails
↓
Standby can take over
↓
Application continues
```

So the purpose is:

```text
Availability
Fault tolerance
Failover
```

---

# 16. Synchronous replication

**Synchronous replication** means the standby database is updated as part of the primary database write process.

Conceptually:

```text
Application writes order
        ↓
Primary records order
        ↓
Standby receives update
        ↓
Write completed
```

This helps keep the standby closely aligned with the primary.

---

# 17. Multi-AZ is NOT mainly read scaling

This distinction is one of the most important in Module 8:

```text
MULTI-AZ
→ High availability

READ REPLICA
→ Read scalability
```

Do not write:

> “Use Multi-AZ because the application has too many read queries.”

The better answer is:

> **Use a read replica.**

---

# 18. RDS read replicas

An RDS **read replica** is a copy of the primary database used to serve read operations.

The module states that read replicas:

* use **asynchronous replication**;
* can be promoted to primary if needed;
* are suitable for read-heavy workloads;
* offload read queries. 

Conceptually:

```text
            Write queries
                ↓
         Primary database
                │
       asynchronous replication
                ↓
           Read replica
                ↑
             Reads
```

---

# 19. Why read replicas help

Suppose:

```text
Writes per minute = 1,000
Reads per minute  = 100,000
```

The primary database may become overloaded with read queries.

Instead:

```text
Writes
→ Primary

Some reads
→ Read replica
```

This reduces the workload on the primary.

---

# 20. Asynchronous replication

With asynchronous replication:

```text
Primary receives update
↓
Primary can continue
↓
Replica receives update shortly afterward
```

Therefore, there may temporarily be a delay between the primary and replica.

The important exam phrase is:

> **Read replicas use asynchronous replication.**

---

# 21. Multi-AZ vs read replica

This table is worth memorising.

| Multi-AZ                | Read Replica                |
| ----------------------- | --------------------------- |
| High availability       | Read scalability            |
| Primary + standby       | Primary + readable copy     |
| Synchronous replication | Asynchronous replication    |
| Standby for failover    | Replica serves read queries |
| Protect against failure | Reduce read workload        |

Memory:

```text
Multi-AZ
→ Keep database alive

Read replica
→ Make reading lighter
```

---

# 22. Likely subjective question — Multi-AZ vs read replica

> An RDS Multi-AZ deployment improves high availability by synchronously replicating data from a primary database to a standby instance in another Availability Zone. If the primary fails, the standby can take over. A read replica is different because it uses asynchronous replication and is intended to serve read queries and reduce the workload on the primary database. Therefore, Multi-AZ is mainly for availability, while read replicas are mainly for read scalability.

That is one of the most important answers to know.

---

# Section 2 — Amazon DynamoDB

# 23. What is DynamoDB?

The module describes **Amazon DynamoDB** as:

> A fast and flexible NoSQL database service for any scale.

It provides:

* NoSQL database tables;
* virtually unlimited storage;
* items with differing attributes;
* low-latency queries;
* scalable read/write throughput. 

Think:

> **DynamoDB = fast NoSQL database for massive scalable key-based workloads.**

---

# 24. When should you think DynamoDB?

Scenario keywords:

```text
NoSQL
Key-value
Document
Massive scale
Low latency
Flexible attributes
Rapidly changing workload
Mobile
Web
Gaming
IoT
```

The module specifically highlights mobile, web, gaming, advertising technology and IoT applications. 

---

# 25. DynamoDB's core components

The module says DynamoDB has three core components:

```text
Table
Item
Attribute
```



Relational comparison:

| Relational DB | DynamoDB  |
| ------------- | --------- |
| Table         | Table     |
| Row           | Item      |
| Column        | Attribute |

So:

```text
Table
→ Collection

Item
→ One record

Attribute
→ One piece of information
```

---

# 26. DynamoDB example

Suppose you have a table:

```text
Players
```

One item:

```text
PlayerID = P001
Name = Amir
Level = 12
```

Another:

```text
PlayerID = P002
Name = Sarah
Level = 42
PreferredDevice = Mobile
Membership = Premium
```

The items do not necessarily need identical attributes.

That is part of DynamoDB's flexibility.

---

# 27. Primary keys

DynamoDB supports two primary-key designs in the module:

```text
1. Partition key

2. Partition key + sort key
```



---

# 28. Partition key

A simple primary key contains one **partition key**.

Example:

```text
PlayerID = P001
```

This uniquely identifies the item.

Think:

```text
Partition key
→ Which item / partition?
```

---

# 29. Partition key + sort key

A composite key contains:

```text
Partition key
+
Sort key
```

Example:

```text
CustomerID = C001
OrderDate = 2026-08-01
```

This allows several items to share the same partition key while being distinguished by the sort key.

Example:

| CustomerID | OrderDate |
| ---------- | --------- |
| C001       | 1 Aug     |
| C001       | 5 Aug     |
| C001       | 8 Aug     |

Same customer.

Different orders.

---

# 30. What does partitioning mean?

As DynamoDB grows, data is distributed across **partitions**.

The partition key helps determine where an item is stored.

Conceptually:

```text
Partition key
     ↓
Hash calculation
     ↓
Storage partition
```

This allows DynamoDB to scale horizontally across resources.

The module's partitioning section is directly connected to this primary-key design. 

---

# 31. Query vs Scan

This distinction is very useful in a subjective question.

## Query

Uses a key to find relevant items.

```text
CustomerID = C001
```

DynamoDB can target the relevant data.

## Scan

Examines many or all items in a table.

```text
Look through everything
until matching items are found
```

The important concept:

```text
Query
→ More targeted

Scan
→ Broader / potentially less efficient
```

---

# 32. DynamoDB low latency

The module states that DynamoDB provides:

> **consistent, single-digit millisecond latency at any scale**

and says it has no limits on table size or throughput in the course material. 

For your exam based on this module, associate:

```text
Single-digit millisecond latency
→ DynamoDB
```

---

# 33. DynamoDB storage model

The module states that DynamoDB:

* runs exclusively on SSDs;
* supports key-value and document models;
* can replicate tables across chosen AWS Regions;
* supports console, CLI and API access. 

You probably do not need to memorise every bullet, but the strongest exam keywords are:

```text
NoSQL
Key-value
Document
Low latency
Scalable throughput
```

---

# 34. RDS vs DynamoDB

| Amazon RDS                      | DynamoDB                    |
| ------------------------------- | --------------------------- |
| Relational                      | NoSQL                       |
| Structured relationships        | Flexible items              |
| SQL                             | Key/document access         |
| Complex relational queries      | Key-based scalable access   |
| Transactions and related tables | Massive scalable workloads  |
| Managed DB instance             | Fully managed NoSQL service |

Scenario:

> Customers, orders, payments and invoices have clear relationships.

**RDS**

Scenario:

> Millions of game players are retrieved by PlayerID.

**DynamoDB**

---

# 35. Good subjective answer — DynamoDB

> Amazon DynamoDB is a fully managed NoSQL database service designed for fast and flexible performance at scale. It stores data in tables containing items and attributes and supports key-value and document data models. DynamoDB uses primary keys consisting of either a partition key or a partition key and sort key. It provides scalable read and write throughput and low-latency access, making it suitable for mobile, web, gaming and IoT workloads.

---

# Section 3 — Amazon Redshift

# 36. What is Amazon Redshift?

**Amazon Redshift** is AWS's managed **data warehouse**.

The module's section summary describes it as a:

> Fast, fully managed data warehouse service.

It also highlights:

* scaling;
* columnar storage;
* parallel processing;
* automatic monitoring;
* built-in encryption. 

Think:

> **Redshift = analyse huge amounts of historical data.**

---

# 37. Transaction database vs data warehouse

This is the central distinction.

### Operational database

Handles individual business transactions.

Example:

```text
Create one order
Update one customer
Process one payment
```

Use:

```text
RDS / Aurora
```

### Data warehouse

Handles large analytical questions.

Example:

```text
Analyse 500 million orders
over 10 years
by country and month
```

Use:

```text
Redshift
```

---

# 38. RDS vs Redshift

Memorise:

```text
RDS
→ Run the business

Redshift
→ Analyse the business
```

More formally:

| RDS                         | Redshift                |
| --------------------------- | ----------------------- |
| Transactional relational DB | Data warehouse          |
| Day-to-day records          | Historical analytics    |
| Individual writes/reads     | Large aggregate queries |
| Application database        | BI/analytics database   |

---

# 39. Redshift architecture

The module's page 42 diagram shows:

```text
SQL Clients / BI Tools
          ↓
      Leader node
          ↓
   Compute nodes
```

and shows Redshift working with data from sources such as:

```text
Amazon S3
Amazon DynamoDB
```



---

# 40. Leader node

The **leader node** coordinates queries.

Conceptually:

```text
Analyst submits SQL query
        ↓
Leader node
        ↓
Divides the work
        ↓
Compute nodes
        ↓
Results combined
```

Think:

> **Leader node = manager.**

---

# 41. Compute nodes

Compute nodes perform the actual processing on portions of the data.

Instead of:

```text
One computer
→ Process 10 billion rows alone
```

Redshift can do:

```text
Node 1 → Part A
Node 2 → Part B
Node 3 → Part C
Node 4 → Part D
```

at the same time.

This is **parallel processing**.

---

# 42. Massively parallel processing

The concept is:

```text
Big job
↓
Divide into smaller jobs
↓
Many compute nodes process simultaneously
↓
Combine results
```

This is one major reason Redshift is suited for large analytical workloads.

---

# 43. Columnar storage

Traditional transactional databases often organise information primarily by rows.

For analytics, Redshift uses **columnar storage**.

Conceptually, instead of:

```text
Order1: Date | Customer | Product | Price
Order2: Date | Customer | Product | Price
```

it can organise data around columns:

```text
Dates
Customers
Products
Prices
```

Why is that useful?

Suppose the query only needs:

```text
Date
Price
```

Redshift can focus on those relevant columns instead of reading all unrelated data.

The module explicitly identifies columnar storage as a core Redshift feature. 

---

# 44. Redshift use cases

The module gives use cases including:

* enterprise data warehousing;
* big data;
* SaaS analytics;
* scaling analytical capacity;
* adding analytics to applications. 

Scenario clues:

```text
Data warehouse
Business intelligence
Historical analytics
Big data
Dashboard
Large analytical SQL query
```

→ **Amazon Redshift**

---

# 45. Good subjective answer — Redshift

> Amazon Redshift is a fast, fully managed data-warehouse service designed for large-scale analytics. It uses columnar storage so analytical queries can focus on relevant columns and uses parallel-processing architecture to distribute work across compute nodes. A leader node coordinates queries submitted by SQL clients or business-intelligence tools. Redshift is suitable for enterprise data warehousing, big-data analytics and reporting over large historical datasets.

---

# 46. Common Redshift scenario

> A retailer wants to analyse ten years of sales data to identify long-term purchasing trends.

Answer:

**Amazon Redshift**

Why?

Because this is:

```text
Historical
Large-scale
Analytical
```

not ordinary day-to-day transaction processing.

---

# Section 4 — Amazon Aurora

# 47. What is Amazon Aurora?

Amazon Aurora is a relational database engine designed by AWS.

It is compatible with:

```text
MySQL
PostgreSQL
```

and is provided through the Amazon RDS managed environment.

The module includes Aurora among the RDS engine choices. 

Think:

> **Aurora = AWS-designed high-performance relational database compatible with MySQL or PostgreSQL.**

---

# 48. Aurora is relational

Do not confuse it with DynamoDB.

```text
Aurora
→ Relational

DynamoDB
→ NoSQL
```

Aurora is appropriate when you still need things associated with a relational database:

```text
SQL
Tables
Relationships
Transactions
```

but want an AWS-designed database with strong performance and availability.

---

# 49. Aurora compatibility

A company might already use MySQL.

It wants to migrate but does not want to rewrite its entire application for a completely different database system.

Aurora provides:

```text
Aurora MySQL-Compatible

or

Aurora PostgreSQL-Compatible
```

This is one of its key benefits.

---

# 50. Managed Aurora capabilities

The module's Aurora material highlights automation of tasks such as:

```text
Provisioning
Patching
Backup
Recovery
Failure detection
Repair
```

Aurora is designed as a managed relational database experience.

---

# 51. Aurora high availability

The module's Aurora architecture emphasises resilience across multiple Availability Zones.

The underlying idea is:

```text
Copies of database storage
across multiple AZs
↓
Failure of one component/location
does not mean loss of every copy
```

This supports:

```text
High availability
Durability
Recovery
```

---

# 52. Aurora benefits

The Aurora section emphasises characteristics such as:

```text
High performance
Scalability
High availability
Durability
Security
MySQL compatibility
PostgreSQL compatibility
Managed operation
```

The core exam clue is:

> **Enterprise-class relational database compatible with MySQL or PostgreSQL.**

---

# 53. RDS vs Aurora

This can be confusing because Aurora is associated with RDS.

The easiest way to think about it is:

```text
Amazon RDS
→ Managed relational database service

Amazon Aurora
→ AWS-designed relational database engine
   available through that managed environment
```

Other RDS engines include:

```text
MySQL
PostgreSQL
MariaDB
Oracle
SQL Server
```

Aurora is the AWS-designed option.

---

# 54. Aurora vs DynamoDB

| Aurora                             | DynamoDB                             |
| ---------------------------------- | ------------------------------------ |
| Relational                         | NoSQL                                |
| SQL                                | Key-value/document                   |
| Structured relationships           | Flexible attributes                  |
| MySQL/PostgreSQL compatible        | AWS NoSQL model                      |
| Transactional relational workloads | Massive scalable key-based workloads |

Scenario:

> Existing MySQL application needs an enterprise-class AWS database.

Think:

**Aurora MySQL-Compatible**

Scenario:

> Mobile game needs millions of PlayerID lookups.

Think:

**DynamoDB**

---

# 55. Aurora vs Redshift

```text
Aurora
→ Run transactional relational applications

Redshift
→ Analyse large datasets
```

Example:

> “Process today's customer order.”

**Aurora/RDS**

> “Analyse every order from the last decade.”

**Redshift**

---

# 56. Good subjective answer — Aurora

> Amazon Aurora is an AWS-designed relational database engine that is compatible with MySQL and PostgreSQL and is managed through Amazon RDS. It is designed for enterprise relational workloads and provides high performance, scalability, availability and durability. Aurora also automates operational tasks such as provisioning, patching, backup, recovery and failure repair.

---

# 57. The right database for the right job

The module's own page 54 gives a useful decision structure. 

| Requirement                                           | Best fit                                |
| ----------------------------------------------------- | --------------------------------------- |
| Enterprise relational database                        | Amazon RDS                              |
| Fast flexible NoSQL at scale                          | DynamoDB                                |
| Full OS access/custom features                        | Database on EC2                         |
| Data warehouse / specialised analytics                | Purpose-built database such as Redshift |
| High-performance MySQL/PostgreSQL relational workload | Aurora                                  |

---

# 58. Likely subjective question — Explain Amazon RDS

A good answer:

> Amazon RDS is a managed relational database service that simplifies the setup, operation and scaling of relational databases in AWS. It supports multiple database engines including MySQL, PostgreSQL, MariaDB, Oracle, Microsoft SQL Server and Amazon Aurora. AWS manages tasks such as operating-system and database software installation and patching, backups, scaling and high availability, while the customer focuses more on application optimisation.

---

# 59. Likely subjective question — Multi-AZ vs read replica

> Amazon RDS Multi-AZ is primarily designed for high availability. It maintains a standby database in another Availability Zone using synchronous replication so that the standby can take over if the primary fails. An RDS read replica uses asynchronous replication and is designed to handle read-heavy workloads by offloading read queries from the primary database. Therefore, Multi-AZ is for availability while read replicas are for read scalability.

Memorise that answer.

---

# 60. Likely subjective question — Explain DynamoDB

> Amazon DynamoDB is a fully managed NoSQL database service designed for fast and flexible performance at scale. It stores information in tables consisting of items and attributes and supports key-value and document models. DynamoDB uses primary keys consisting of a partition key or a partition key with a sort key and provides scalable read/write throughput with low-latency access.

---

# 61. Likely subjective question — Explain Redshift

> Amazon Redshift is a fully managed data-warehouse service used for analysing large amounts of data. It uses columnar storage to improve analytical query efficiency and parallel-processing architecture to distribute workloads across compute nodes. A leader node coordinates queries from SQL clients and business-intelligence tools, making Redshift suitable for big-data analytics and historical business reporting.

---

# 62. Likely subjective question — Explain Aurora

> Amazon Aurora is an AWS-designed relational database engine that is compatible with MySQL and PostgreSQL and is managed through Amazon RDS. It provides high performance, scalability, availability and durability and automates tasks such as provisioning, patching, backup, recovery and failure detection. It is suitable for enterprise applications that require a high-performance relational database while maintaining MySQL or PostgreSQL compatibility.

---

# 63. Likely subjective question — Relational vs NoSQL

> A relational database stores structured information in tables with defined relationships and is suitable for applications requiring transactions, SQL and relationships between records. A NoSQL database such as DynamoDB provides a more flexible data model using items and attributes and is suitable for workloads that need rapid scaling, key-value or document access and low latency.

---

# 64. How to answer a database scenario

Use this method:

```text
1. Ask whether relationships matter.
2. Ask whether the workload is transactional or analytical.
3. Ask whether massive key-based scale is required.
4. Ask whether MySQL/PostgreSQL compatibility matters.
5. Ask whether OS-level control is required.
6. Choose the service.
7. Explain why.
```

Example:

> An ecommerce company stores customers, orders, invoices and payments. These records have relationships and transactions must remain consistent.

Weak answer:

> RDS.

Better answer:

> Amazon RDS is appropriate because the workload contains structured relational data such as customers, orders, invoices and payments that have clear relationships and require transactional processing. RDS provides a managed relational database while AWS manages much of the underlying maintenance, backups and availability.

That second answer is what subjective marking normally rewards.

---

# 65. Scenario practice

### Scenario A

> A company needs a database for customers, orders and payments.

**Amazon RDS**

Reason:

```text
Structured
Relational
Transactional
```

---

### Scenario B

> An application must survive failure of the Availability Zone containing its primary database.

**RDS Multi-AZ**

Reason:

```text
Primary + standby
Different AZ
Synchronous replication
```

---

### Scenario C

> An application has extremely heavy read traffic.

**RDS read replica**

Reason:

```text
Offload reads
Asynchronous replication
```

---

### Scenario D

> A mobile game stores millions of player records accessed by PlayerID.

**DynamoDB**

Reason:

```text
NoSQL
Key-based
Low latency
Large scale
```

---

### Scenario E

> The organisation wants to analyse ten years of sales data using BI dashboards.

**Redshift**

Reason:

```text
Data warehouse
Historical analytics
```

---

### Scenario F

> A company already has a MySQL application but wants an AWS-designed enterprise relational database.

**Amazon Aurora MySQL-Compatible**

---

### Scenario G

> A company must install unsupported database extensions and requires direct OS access.

**Database on EC2**

Page 54 specifically maps operating-system access or unsupported application features to databases on Amazon EC2. 

---

# 66. High-priority scenario clues

| If the question says...          | Think...        |
| -------------------------------- | --------------- |
| Managed relational               | RDS             |
| SQL + transactions               | RDS             |
| Several relational DB engines    | RDS             |
| High availability                | Multi-AZ        |
| Synchronous replication          | Multi-AZ        |
| Standby database                 | Multi-AZ        |
| Read-heavy                       | Read replica    |
| Asynchronous replication         | Read replica    |
| NoSQL                            | DynamoDB        |
| Key-value                        | DynamoDB        |
| Document                         | DynamoDB        |
| Flexible attributes              | DynamoDB        |
| Single-digit millisecond latency | DynamoDB        |
| Partition key                    | DynamoDB        |
| Sort key                         | DynamoDB        |
| Data warehouse                   | Redshift        |
| Business intelligence            | Redshift        |
| Historical analysis              | Redshift        |
| Columnar storage                 | Redshift        |
| Parallel processing              | Redshift        |
| Leader + compute nodes           | Redshift        |
| MySQL/PostgreSQL compatible      | Aurora          |
| AWS-designed relational engine   | Aurora          |
| Full OS access                   | Database on EC2 |

---

# 67. Common mistakes to avoid

**RDS is NoSQL.**
Wrong.

```text
RDS → Relational
DynamoDB → NoSQL
```

---

**DynamoDB items must all have identical attributes.**
Wrong.

The module explicitly says items can have differing attributes. 

---

**Multi-AZ and read replicas are the same thing.**
Wrong.

```text
Multi-AZ
→ Availability

Read replica
→ Read performance/scalability
```

---

**Multi-AZ standby is mainly used to handle normal read traffic.**
Wrong for the concept taught here.

The standby's main role is availability and failover.

---

**Read replicas use synchronous replication.**
Wrong.

```text
Multi-AZ → Synchronous
Read replica → Asynchronous
```

---

**Redshift is best for ecommerce checkout transactions.**
Wrong.

```text
RDS/Aurora → Transaction
Redshift → Analytics
```

---

**DynamoDB is a data warehouse.**
Wrong.

Redshift is the data warehouse service in this module.

---

**Aurora is unrelated to RDS.**
Wrong.

Aurora appears as one of the engines within the RDS environment in the module. 

---

**Aurora supports Oracle and SQL Server compatibility.**
Wrong.

The module associates Aurora with:

```text
MySQL
PostgreSQL
```

---

**Managed database means the customer has nothing to manage.**
Wrong.

The course specifically keeps **application optimisation** on the customer's side for RDS. 

---

# 68. What I would prioritise before the subjective exam

If time is short, master these **six areas**:

```text
1. RDS
   Managed relational database
   AWS vs customer responsibility

2. Multi-AZ vs Read Replica
   Multi-AZ → availability
   Replica → reads

3. DynamoDB
   NoSQL
   Table / item / attribute
   Partition key / sort key

4. Redshift
   Data warehouse
   Columnar
   Parallel processing

5. Aurora
   MySQL/PostgreSQL compatible
   High-performance relational database

6. Database selection
   RDS vs DynamoDB vs Redshift vs Aurora vs EC2
```

Those areas directly cover the module objectives. 

# Final 2-minute revision

```text
AMAZON RDS
──────────
Managed relational DB

AWS manages:
OS
DB software
Patching
Backups
Scaling
High availability

Customer:
Application optimisation
```

```text
RDS AVAILABILITY
────────────────
Multi-AZ
→ Primary + standby
→ Synchronous
→ High availability

Read Replica
→ Asynchronous
→ Read-heavy workloads
→ Offload queries
```

```text
DYNAMODB
────────
NoSQL
Table
Item
Attribute

Primary key:
Partition key

or

Partition key + Sort key

Low latency
Scalable read/write throughput
```

```text
REDSHIFT
────────
Data warehouse
Historical analytics
SQL / BI

Leader node
↓
Compute nodes

Columnar storage
Parallel processing
```

```text
AURORA
──────
Relational
AWS-designed
Managed through RDS

Compatible with:
MySQL
PostgreSQL

High performance
Scalable
Highly available
```

```text
FAST DATABASE DECISION
──────────────────────

Transactions + relationships?
→ RDS

Massive NoSQL / key-value?
→ DynamoDB

Historical analytics?
→ Redshift

Enterprise MySQL/PostgreSQL?
→ Aurora

Full OS control?
→ Database on EC2
```

The **single most important mental model** for Module 8 is:

```text
RDS
→ "RUN my relational business data."

DYNAMODB
→ "LOOK UP massive flexible data quickly."

REDSHIFT
→ "ANALYSE huge amounts of historical data."

AURORA
→ "Give me a high-performance AWS relational database
   that still works with MySQL/PostgreSQL."
```

Once those four purposes are clear, most Module 8 subjective scenarios become a matter of identifying **what the database is being asked to do**, rather than trying to memorise four similar-looking AWS service names. 

</details>