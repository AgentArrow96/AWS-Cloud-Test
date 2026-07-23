# Intuitive Explanation Covering Module 3 - 8 of Distributed & Parallel Computing

---

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
<summary><strong>Module 3 AWS-Style Objective Test Preparation</strong></summary>

# Module 3 AWS-Style Objective Test Preparation

Module 3 has only two formal learning objectives:

1. Differentiate **AWS Regions, Availability Zones, and edge locations**.
2. Identify common **AWS services and their service categories**. 

The test below uses original questions, but follows AWS’s official style: either **multiple choice** with one correct answer and three plausible distractors, or **multiple response** with two or more correct answers from at least five choices. AWS deliberately makes the wrong answers sound reasonable, because apparently knowing the answer was not enough; the alternatives must also attempt psychological warfare. ([AWS Documentation][1])

## What AWS questions usually look like

Expect wording such as:

* “Which AWS service…?”
* “Which component BEST meets these requirements?”
* “A company wants to… Which solution should it use?”
* “Which statement is correct?”
* “Select TWO.”

The questions generally test service recognition and the **best fit**, not obscure configuration commands. Official AWS practice sets are specifically designed to demonstrate this exam style. ([Amazon Web Services, Inc.][2])

---

# Part 1: What you must know before the test

## Infrastructure hierarchy

```text
AWS Global Infrastructure
└── AWS Region
    ├── Availability Zone
    │   ├── Data centre
    │   └── Data centre
    └── Availability Zone
        └── Data centre

Points of Presence
├── Edge locations
└── Regional edge caches
```

| Component               | Meaning                                                                  | Main exam clue                                       |
| ----------------------- | ------------------------------------------------------------------------ | ---------------------------------------------------- |
| **Region**              | A geographical area containing multiple AZs                              | Compliance, location, service availability and price |
| **Availability Zone**   | An isolated infrastructure partition containing one or more data centres | Fault isolation and resilience                       |
| **Data centre**         | Physical facility containing servers and networking equipment            | Where processing and storage physically occur        |
| **Edge location**       | Site that caches and delivers content close to users                     | CloudFront and low latency                           |
| **Regional edge cache** | Larger cache between edge locations and the origin                       | Less frequently accessed content                     |

AWS recommends using multiple Availability Zones to improve resilience. Cross-Region data replication is controlled by the customer rather than automatically happening merely because AWS owns a large map. 

## Selecting an AWS Region

Remember **CLAS**:

| Letter | Factor                                |
| ------ | ------------------------------------- |
| **C**  | Compliance and data governance        |
| **L**  | Latency and customer proximity        |
| **A**  | Availability of required AWS services |
| **S**  | Service cost in that Region           |

The closest Region is not always the correct one. Regulations come first; a slightly faster illegal architecture remains illegal.

## Infrastructure characteristics

| Term                  | Meaning                                                    |
| --------------------- | ---------------------------------------------------------- |
| **Elasticity**        | Automatically adjusts capacity according to current demand |
| **Scalability**       | Can grow to accommodate increasing demand                  |
| **Fault tolerance**   | Continues operating even when a component fails            |
| **High availability** | Minimises downtime and maintains operational performance   |

## Resource scope

```text
VPC       → Regional
Subnet    → One Availability Zone
EC2       → Regional service
Lambda    → Regional service
IAM       → Global service
Route 53  → Global service
```

## Service-category map

| Category                              | Services shown in Module 3                                                                                        |
| ------------------------------------- | ----------------------------------------------------------------------------------------------------------------- |
| **Compute**                           | EC2, EC2 Auto Scaling, ECS, EKS, Fargate, Lambda, Elastic Beanstalk                                               |
| **Storage**                           | S3, S3 Glacier, EBS, EFS                                                                                          |
| **Database**                          | RDS, Aurora, DynamoDB, Redshift                                                                                   |
| **Networking and Content Delivery**   | VPC, Elastic Load Balancing, Direct Connect, VPN, Transit Gateway, Route 53, CloudFront                           |
| **Security, Identity and Compliance** | IAM, Organizations, Cognito, KMS, Shield, Artifact                                                                |
| **Cost Management**                   | AWS Budgets, Cost Explorer, Cost and Usage Report                                                                 |
| **Management and Governance**         | Management Console, CLI, CloudWatch, CloudTrail, Config, Trusted Advisor, Well-Architected Tool, AWS Auto Scaling |

These are the category groupings shown in the module.       

---

# Part 2: Module 3 Mock Test

**Questions:** 30
**Suggested time:** 35 minutes
**Instructions:** Choose one answer unless the question says **Select TWO**.

---

## Infrastructure questions

### 1. Which AWS global infrastructure component is a geographical area that contains multiple Availability Zones?

A. An edge location
B. An AWS Region
C. A data centre
D. A Regional edge cache

---

### 2. A government agency is legally required to keep its data within a particular country. Which factor should receive the highest priority when selecting an AWS Region?

A. Number of edge locations
B. Data governance and legal requirements
C. Number of EC2 instance types
D. Distance from the nearest data centre

---

### 3. A company wants to reduce the response time experienced by most of its customers. Which Region-selection factor is MOST relevant?

A. The physical size of the Region
B. The number of IAM users
C. Proximity to the customers
D. The number of security groups

---

### 4. Which statement BEST describes an Availability Zone?

A. A geographical area that contains several Regions
B. A content-caching site located near end users
C. An isolated infrastructure partition containing one or more data centres
D. A global network that resolves domain names

---

### 5. A company wants its application to remain available if one AWS data-centre location fails. Which approach should it use?

A. Deploy resources across multiple Availability Zones
B. Place all resources in one large EC2 instance
C. Use a single edge location
D. Create multiple IAM users

---

### 6. Who controls whether customer data is replicated from one AWS Region to another?

A. Amazon CloudFront
B. The Availability Zone
C. AWS Support
D. The customer

---

### 7. Which AWS infrastructure component is the physical facility where data resides and processing occurs?

A. AWS Region
B. Data centre
C. Edge location
D. VPC

---

### 8. Which component does Amazon CloudFront primarily use to deliver cached content with lower latency?

A. IAM groups
B. Availability Zones
C. Edge locations
D. Security groups

---

### 9. CloudFront content is requested infrequently and is no longer stored at the nearest edge location. Which component can retain the content between the edge location and the origin?

A. Availability Zone
B. Regional edge cache
C. Internet gateway
D. VPC

---

### 10. Which components form AWS Points of Presence? **Select TWO.**

A. Edge locations
B. Availability Zones
C. AWS Regions
D. Regional edge caches
E. Data centres

---

## Infrastructure characteristic questions

### 11. An application automatically increases capacity during a sale and decreases capacity after the sale ends. Which infrastructure characteristic does this demonstrate?

A. Durability
B. Elasticity
C. Compliance
D. Fault isolation

---

### 12. A system can expand from supporting 10,000 users to supporting one million users. Which characteristic does this demonstrate?

A. High availability
B. Data sovereignty
C. Fault tolerance
D. Scalability

---

### 13. A system continues operating correctly after one of its components fails. Which characteristic does this describe?

A. Fault tolerance
B. Elasticity
C. Latency
D. Governance

---

### 14. A company wants to maintain a high level of operational performance while minimising downtime. Which characteristic is the company seeking?

A. Horizontal scaling
B. Regional caching
C. High availability
D. Data replication

---

## AWS resource-scope questions

### 15. At which infrastructure level does an Amazon VPC exist?

A. Data-centre level
B. Region level
C. Edge-location level
D. Global level

---

### 16. At which infrastructure level does a subnet exist?

A. Across all AWS Regions
B. Across several Availability Zones
C. Within one Availability Zone
D. Within one edge location

---

### 17. Which AWS services are global rather than Regional? **Select TWO.**

A. Amazon EC2
B. AWS Identity and Access Management
C. AWS Lambda
D. Amazon Route 53
E. Amazon VPC

---

### 18. Which AWS services are Regional? **Select TWO.**

A. AWS Identity and Access Management
B. Amazon EC2
C. Amazon Route 53
D. AWS Lambda
E. AWS Organizations

---

## Service-category questions

### 19. Which service belongs to the **Compute** service category?

A. Amazon S3
B. Amazon Elastic Container Service
C. Amazon RDS
D. Amazon CloudFront

---

### 20. Which service belongs to the **Storage** service category?

A. Amazon EFS
B. AWS Lambda
C. Amazon Route 53
D. Amazon DynamoDB

---

### 21. Which service belongs to the **Database** service category?

A. Amazon VPC
B. AWS Shield
C. Amazon EBS
D. Amazon Redshift

---

### 22. Which service belongs to the **Networking and Content Delivery** category?

A. Amazon Aurora
B. AWS Budgets
C. AWS Direct Connect
D. AWS CloudTrail

---

### 23. Which service belongs to the **Security, Identity and Compliance** category?

A. Amazon EC2
B. AWS Key Management Service
C. Amazon EFS
D. AWS Cost Explorer

---

### 24. Which service belongs to the **Cost Management** category?

A. AWS Cost Explorer
B. AWS Config
C. Amazon Cognito
D. AWS Lambda

---

### 25. Which service belongs to the **Management and Governance** category?

A. Amazon DynamoDB
B. Amazon CloudFront
C. AWS KMS
D. AWS CloudTrail

---

### 26. Which services belong to the **Compute** category? **Select TWO.**

A. AWS Lambda
B. Amazon S3
C. AWS Fargate
D. Amazon DynamoDB
E. Amazon Route 53

---

### 27. Which services belong to the **Storage** category? **Select TWO.**

A. Amazon Aurora
B. Amazon EBS
C. Amazon VPC
D. AWS Shield
E. Amazon S3 Glacier

---

### 28. Which services belong to the **Database** category? **Select TWO.**

A. Amazon Aurora
B. Amazon CloudFront
C. AWS Config
D. Amazon DynamoDB
E. AWS Budgets

---

### 29. Which services belong to the **Security, Identity and Compliance** category? **Select TWO.**

A. Amazon Redshift
B. Amazon Cognito
C. Amazon EFS
D. Elastic Load Balancing
E. AWS Artifact

---

### 30. Which services belong to the **Management and Governance** category? **Select TWO.**

A. Amazon CloudWatch
B. Amazon RDS
C. Amazon Route 53
D. AWS Trusted Advisor
E. Amazon S3

---

# Stop here before checking the answers

<details>
<summary><strong>Open answer key and explanations</strong></summary>

## Answer key

|  Q |  Answer  | Why                                                                                                 |
| -: | :------: | --------------------------------------------------------------------------------------------------- |
|  1 |   **B**  | A Region is a geographical area containing multiple AZs.                                            |
|  2 |   **B**  | Compliance and legal requirements override convenience or latency.                                  |
|  3 |   **C**  | Placing resources closer to customers generally reduces latency.                                    |
|  4 |   **C**  | An AZ is an isolated infrastructure partition containing discrete data centres.                     |
|  5 |   **A**  | Multiple AZs protect against failure affecting one location.                                        |
|  6 |   **D**  | Customers decide whether their data is replicated across Regions.                                   |
|  7 |   **B**  | Data centres are the physical facilities where storage and processing occur.                        |
|  8 |   **C**  | CloudFront uses edge locations to cache content near users.                                         |
|  9 |   **B**  | Regional edge caches retain less frequently accessed content between edge locations and the origin. |
| 10 | **A, D** | Points of Presence include edge locations and Regional edge caches.                                 |
| 11 |   **B**  | Elasticity means dynamically increasing and decreasing capacity.                                    |
| 12 |   **D**  | Scalability is the ability to accommodate growth.                                                   |
| 13 |   **A**  | Fault tolerance means continuing to operate despite a failure.                                      |
| 14 |   **C**  | High availability aims to minimise downtime.                                                        |
| 15 |   **B**  | A VPC belongs to one AWS Region.                                                                    |
| 16 |   **C**  | A subnet exists within one Availability Zone.                                                       |
| 17 | **B, D** | IAM and Route 53 are global services.                                                               |
| 18 | **B, D** | EC2 and Lambda resources are created within selected Regions.                                       |
| 19 |   **B**  | ECS is a compute service for containerised workloads.                                               |
| 20 |   **A**  | EFS is managed file storage.                                                                        |
| 21 |   **D**  | Redshift is a database and data-warehouse service.                                                  |
| 22 |   **C**  | Direct Connect is a networking service.                                                             |
| 23 |   **B**  | KMS manages encryption keys and belongs to security.                                                |
| 24 |   **A**  | Cost Explorer is used to examine AWS spending and usage.                                            |
| 25 |   **D**  | CloudTrail is grouped under management and governance.                                              |
| 26 | **A, C** | Lambda and Fargate are compute services.                                                            |
| 27 | **B, E** | EBS and S3 Glacier are storage services.                                                            |
| 28 | **A, D** | Aurora and DynamoDB are database services.                                                          |
| 29 | **B, E** | Cognito and Artifact belong to security, identity and compliance.                                   |
| 30 | **A, D** | CloudWatch and Trusted Advisor belong to management and governance.                                 |

</details>

---

# Score interpretation

|        Score | Readiness                                                                   |
| -----------: | --------------------------------------------------------------------------- |
|    **27–30** | Strongly prepared                                                           |
|    **23–26** | Nearly ready; revise the mistakes                                           |
|    **18–22** | Core knowledge exists, but AWS distractors are still working                |
| **Below 18** | Review the infrastructure hierarchy and service categories before retesting |

## The five most dangerous exam confusions

```text
Region ≠ Availability Zone
Availability Zone ≠ data centre
Multi-AZ ≠ Multi-Region
Edge location ≠ Availability Zone
Elasticity ≠ scalability
```

And for category questions:

```text
CloudFront → Networking and Content Delivery
CloudTrail → Management and Governance
CloudWatch → Management and Governance
Cost Explorer → Cost Management
Artifact → Security, Identity and Compliance
```

Reply with an answer string such as `1B, 2B, 3C...`, and I’ll grade it without revealing the answers first.

[1]: https://docs.aws.amazon.com/aws-certification/latest/cloud-practitioner-02/cloud-practitioner-02.html "AWS Certified Cloud Practitioner (CLF-C02) - AWS Certified Cloud Practitioner"
[2]: https://aws.amazon.com/certification/certification-prep/ "Prepare for your AWS Certification Exam | Training and Certification | AWS"

---

</details>

<details>
<summary><strong>Module 4: AWS Cloud Security — AWS-Style Objective Test Preparation</strong></summary>

# Module 4: AWS Cloud Security — AWS-Style Objective Test Preparation

The current AWS Certified Cloud Practitioner exam uses:

* **Multiple choice:** one correct answer and three distractors.
* **Multiple response:** two or more correct answers from at least five options.

AWS describes distractors as plausible answers that candidates with incomplete knowledge might select. Security and Compliance currently represents **30% of scored CLF-C02 content**, so AWS takes this topic rather seriously. ([AWS Documentation][1])

This test stays within the eight objectives of **AWS Academy Cloud Foundations Module 4** rather than adding unrelated security services from the broader certification syllabus. 

---

# 1. What Module 4 expects you to know

The module objectives are to recognise:

1. The AWS shared responsibility model.
2. AWS and customer responsibilities.
3. IAM users, groups and roles.
4. IAM security credentials.
5. Steps for securing a new AWS account.
6. How IAM users and groups operate.
7. How AWS data is secured.
8. AWS compliance programs. 

---

# 2. High-priority concepts before attempting the test

## Shared responsibility

```text
AWS      → Security OF the cloud
Customer → Security IN the cloud
```

| AWS generally manages                 | Customer generally manages     |
| ------------------------------------- | ------------------------------ |
| Physical data centres                 | Customer data                  |
| Physical servers                      | IAM permissions                |
| AWS networking infrastructure         | EC2 guest operating system     |
| Virtualisation layer                  | EC2 operating-system patches   |
| Isolation between customers           | Security groups                |
| Hardware disposal                     | Application configuration      |
| Underlying AWS service infrastructure | S3 bucket access configuration |

The customer's responsibility changes according to the service. EC2 gives the customer more control and therefore more security work; managed services such as RDS and Lambda move more infrastructure responsibility to AWS. 

## IAM essentials

```text
IAM user   → Long-term identity
IAM group  → Collection of users
IAM policy → Permission document
IAM role   → Assumable permissions with temporary credentials
```

Permission evaluation:

```text
Explicit Deny > Explicit Allow > Implicit Deny
```

IAM follows implicit deny by default, and AWS recommends least privilege.

## Account-security sequence

```text
Protect root user
↓
Enable MFA
↓
Create individual IAM users
↓
Use groups and least privilege
↓
Use roles instead of shared credentials
↓
Configure password policy
↓
Monitor with CloudTrail
```

## Security-service map

| Requirement                        | Service                |
| ---------------------------------- | ---------------------- |
| Manage several AWS accounts        | AWS Organizations      |
| Set maximum account permissions    | Service control policy |
| Manage encryption keys             | AWS KMS                |
| Authenticate application customers | Amazon Cognito         |
| DDoS protection                    | AWS Shield             |
| Record API activity                | AWS CloudTrail         |
| Evaluate resource configurations   | AWS Config             |
| Retrieve AWS compliance reports    | AWS Artifact           |

---

# 3. Module 4 Mock Test

**Questions:** 40
**Suggested time:** 45 minutes
**Instructions:** Select one answer unless the question says **Select TWO**.

---

## Shared responsibility model

### 1. Which statement BEST describes the AWS shared responsibility model?

A. AWS is responsible for all security controls when a customer uses AWS
B. Customers are responsible only for physical security
C. AWS secures the cloud infrastructure, while customers secure their workloads and configurations
D. AWS and the customer are equally responsible for every individual security control

---

### 2. Which task is the responsibility of AWS?

A. Configuring an EC2 security group
B. Patching the operating system of an EC2 instance
C. Protecting the physical AWS data centre
D. Creating IAM password policies

---

### 3. A company launches a Linux EC2 instance. Who is responsible for applying security patches to its guest operating system?

A. AWS
B. The customer
C. The Linux distributor only
D. AWS Support

---

### 4. A company stores files in an Amazon S3 bucket. Who is responsible for configuring the bucket's access permissions?

A. AWS
B. The customer
C. The internet service provider
D. The AWS data-centre operator

---

### 5. Which task is AWS responsible for when a customer uses Amazon EC2?

A. Installing customer applications
B. Protecting the virtualisation infrastructure
C. Managing the customer's passwords
D. Configuring the customer's host firewall

---

### 6. A company runs Oracle directly on an EC2 instance. Who is responsible for installing Oracle database patches?

A. AWS
B. Oracle automatically
C. The customer
D. The Availability Zone

---

### 7. A company runs Oracle using Amazon RDS. Who generally manages the database software patches?

A. The customer
B. AWS
C. The company's internet provider
D. The IAM administrator

---

### 8. Which responsibilities belong to the customer when using EC2? **Select TWO.**

A. Physical security of AWS servers
B. EC2 guest operating-system patches
C. Virtualisation infrastructure
D. Security-group configuration
E. Disposal of physical storage devices

---

### 9. Which responsibilities belong to AWS? **Select TWO.**

A. Configuring customer IAM policies
B. Protecting AWS physical facilities
C. Maintaining the underlying network infrastructure
D. Selecting the customer's encryption settings
E. Protecting customer access keys

---

### 10. Why does a customer generally have more security responsibility with an IaaS service than with a managed platform service?

A. IaaS services do not use physical security
B. IaaS gives the customer more control over the operating system and configuration
C. Managed services cannot process confidential data
D. IaaS services do not use the shared responsibility model

---

### 11. Which service gives the customer the greatest responsibility for operating-system configuration?

A. AWS Lambda
B. Amazon RDS
C. Amazon EC2
D. AWS Shield

---

### 12. Which services are examples of managed platform services in Module 4? **Select TWO.**

A. Amazon EC2
B. Amazon EBS
C. Amazon RDS
D. AWS Lambda
E. Amazon VPC

---

## IAM identities and credentials

### 13. Which IAM component represents a person or application that can authenticate with an AWS account?

A. IAM policy
B. IAM user
C. IAM group
D. Service control policy

---

### 14. A company wants to assign the same permissions to 25 developers. Which IAM component should the company use?

A. IAM group
B. IAM access key
C. AWS Organizations
D. Resource-based policy attached separately to every EC2 instance

---

### 15. What is the purpose of an IAM policy?

A. To store application data
B. To define permissions to AWS actions and resources
C. To create a physical network connection
D. To encrypt all AWS traffic automatically

---

### 16. Which statement BEST describes an IAM role?

A. A permanent password shared by a department
B. A collection of IAM users
C. An assumable IAM identity that provides temporary credentials
D. An AWS account's root identity

---

### 17. An application running on EC2 must access an S3 bucket. Which solution follows AWS best practices?

A. Store the root-user password in the application
B. Embed a permanent IAM user's secret key in the code
C. Attach an IAM role with the required S3 permissions to the EC2 instance
D. Make the S3 bucket public

---

### 18. Which credentials are traditionally associated with IAM programmatic access?

A. Account ID and password
B. Access key ID and secret access key
C. Security-group ID and subnet ID
D. Private IP address and public IP address

---

### 19. Which information can be used by an IAM user to access the AWS Management Console?

A. Account ID or alias, IAM username and password
B. Access key ID only
C. Security-group name and private key
D. VPC ID and account number only

---

### 20. What additional information does MFA require in addition to normal sign-in credentials?

A. An AWS Region
B. A unique authentication code or security-device response
C. A new IAM policy
D. A public IP address

---

### 21. Which statement describes authentication?

A. Determining which S3 actions a user can perform
B. Confirming the identity of a user or application
C. Encrypting stored information
D. Recording AWS API activity

---

### 22. Which statement describes authorisation?

A. Proving a user's identity
B. Determining which actions an authenticated identity may perform
C. Creating an authentication code
D. Recording the user's password in CloudTrail

---

## IAM policy evaluation

### 23. An IAM user has no policies attached. What access does the user have by default?

A. Full access
B. Read-only access
C. No access because requests are implicitly denied
D. Access to services in the user's Region only

---

### 24. One policy allows an IAM user to delete an S3 object. Another policy explicitly denies the same action. What is the final result?

A. The action is allowed because one policy grants permission
B. The action is denied because explicit deny overrides allow
C. The policies cancel each other, so AWS asks the administrator
D. The most recently attached policy wins

---

### 25. Which permission has the highest priority during IAM policy evaluation?

A. Implicit deny
B. Explicit allow
C. Explicit deny
D. Group membership

---

### 26. What does the principle of least privilege require?

A. Give every user administrator access temporarily
B. Give identities only the permissions necessary to perform their work
C. Use only the root user for sensitive actions
D. Prevent users from belonging to groups

---

### 27. An IAM policy is attached to an IAM role. What type of policy is this?

A. Resource-based policy
B. Identity-based policy
C. Network policy
D. Service control policy

---

### 28. A policy is attached directly to an S3 bucket and specifies who may access the bucket. What type of policy is this?

A. Identity-based policy
B. Password policy
C. Resource-based policy
D. Billing policy

---

### 29. Which statements about IAM groups are correct? **Select TWO.**

A. Groups can contain IAM users
B. Groups can contain other groups
C. A user can belong to multiple groups
D. Every IAM user automatically belongs to a default group
E. Groups provide temporary security credentials

---

### 30. Which statements about IAM roles are correct? **Select TWO.**

A. A role must be permanently associated with one person
B. A role can be assumed by an AWS service
C. A role provides temporary security credentials
D. A role is a collection of IAM users
E. A role must contain a console password

---

# Securing a new AWS account

### 31. Which action should a company take FIRST to reduce routine use of the AWS account root user?

A. Share the root password with administrators
B. Create an administrative IAM identity for everyday administration
C. Delete the root user
D. Disable all AWS Regions

---

### 32. Which task normally requires the AWS account root user according to the module?

A. Starting an EC2 instance
B. Uploading an object to S3
C. Changing the AWS Support plan
D. Creating a standard IAM group

---

### 33. Which actions are recommended for protecting an AWS account? **Select TWO.**

A. Create one shared IAM user for the whole team
B. Enable MFA for the root user
C. Keep active root-user access keys for convenience
D. Create individual IAM identities
E. Give all users full administrator access

---

### 34. Which AWS service records user activity and API requests in an AWS account?

A. AWS Artifact
B. AWS CloudTrail
C. AWS Shield
D. Amazon Cognito

---

### 35. A security administrator needs to determine who changed an S3 bucket policy. Which service should the administrator use?

A. AWS CloudTrail
B. Amazon Cognito
C. AWS KMS
D. AWS Artifact

---

### 36. What is the purpose of the AWS Cost and Usage Report in the account-security steps discussed in the module?

A. It prevents all unexpected charges
B. It provides detailed information about resource usage and estimated charges
C. It replaces IAM permissions
D. It encrypts billing data

---

## Securing accounts and applications

### 37. A company wants to centrally manage multiple AWS accounts and group them into organisational units. Which service should it use?

A. Amazon Cognito
B. AWS Organizations
C. AWS Shield
D. AWS Artifact

---

### 38. What is the purpose of a service control policy?

A. To grant users permissions directly
B. To store temporary IAM credentials
C. To define the maximum available permissions for accounts in an organisation
D. To encrypt resources across every AWS account

---

### 39. An SCP allows the use of Amazon S3, but an IAM user has not been granted S3 permission. Can the user access S3?

A. Yes, because the SCP grants access
B. Yes, because S3 is allowed at the organisation level
C. No, because an SCP does not grant permissions
D. No, because SCPs apply only to the root user

---

### 40. Which AWS service enables a company to create and manage encryption keys?

A. AWS KMS
B. AWS Shield
C. Amazon Cognito
D. AWS Artifact

---

### 41. A web application needs sign-up, sign-in and access control for millions of customer accounts. Which service should be used?

A. IAM groups
B. Amazon Cognito
C. AWS Organizations
D. AWS Config

---

### 42. Which service helps protect an AWS application against distributed denial-of-service attacks?

A. AWS Artifact
B. AWS Shield
C. AWS Config
D. AWS KMS

---

### 43. Which statements about AWS Shield are correct? **Select TWO.**

A. It manages application-user passwords
B. It provides DDoS protection
C. Shield Standard is available without an additional charge
D. It evaluates resource configurations
E. It provides compliance reports

---

## Data protection and compliance

### 44. Which description refers to encryption at rest?

A. Encrypting information while it moves between a browser and a web server
B. Encrypting information stored on physical media
C. Encrypting an IAM username before login
D. Encrypting only CloudTrail logs

---

### 45. Which technology is commonly used to protect data in transit?

A. TLS
B. IAM group
C. SCP
D. AWS Artifact

---

### 46. A user connects securely to a website through HTTPS. What is being protected?

A. Data at rest only
B. Data moving across the network
C. Physical storage hardware
D. IAM group membership

---

### 47. Which AWS services can integrate with AWS KMS for encryption at rest according to the module? **Select TWO.**

A. Amazon EBS
B. Amazon EFS
C. Amazon Route 53
D. AWS Organizations
E. AWS Shield

---

### 48. A company wants to reduce the risk that an S3 bucket is accidentally made public. Which feature should it use?

A. Amazon S3 Block Public Access
B. AWS Shield Advanced
C. AWS Organizations consolidated billing
D. Amazon Cognito user pools

---

### 49. Which access-control mechanism is described in the module as a legacy S3 mechanism?

A. IAM role
B. S3 access control list
C. S3 Block Public Access
D. Bucket policy

---

### 50. Which AWS service continuously records resource configurations, evaluates them against desired configurations and maintains configuration history?

A. AWS CloudTrail
B. AWS Config
C. AWS Artifact
D. AWS Shield

---

### 51. Which AWS service provides access to reports such as ISO certifications, PCI reports and SOC reports?

A. AWS KMS
B. Amazon Cognito
C. AWS Artifact
D. AWS Organizations

---

### 52. Which statement about AWS compliance is correct?

A. Every workload becomes compliant merely by running on AWS
B. AWS provides compliance information and controls, while customers must configure workloads according to their requirements
C. AWS Artifact automatically changes non-compliant resources
D. AWS Config provides legal certification for the customer

---

# Stop before opening the answers

<details>
<summary><strong>Open answer key and explanations</strong></summary>

## Answer key

|  Q |  Answer  | Explanation                                                                                |
| -: | :------: | ------------------------------------------------------------------------------------------ |
|  1 |   **C**  | AWS secures the underlying cloud; the customer secures workloads, data and configurations. |
|  2 |   **C**  | AWS protects the physical data centres.                                                    |
|  3 |   **B**  | The customer patches the guest OS on EC2.                                                  |
|  4 |   **B**  | Customers configure access to their S3 buckets.                                            |
|  5 |   **B**  | AWS maintains the virtualisation layer.                                                    |
|  6 |   **C**  | A database on EC2 is customer-managed above the infrastructure layer.                      |
|  7 |   **B**  | RDS is managed, so AWS handles database software patching.                                 |
|  8 | **B, D** | EC2 OS patching and security-group rules belong to the customer.                           |
|  9 | **B, C** | AWS secures physical facilities and underlying network infrastructure.                     |
| 10 |   **B**  | More customer control means more customer security responsibility.                         |
| 11 |   **C**  | EC2 gives the customer guest-OS control.                                                   |
| 12 | **C, D** | RDS and Lambda are managed platform examples in the module.                                |

The shared-responsibility distinctions are shown in the module's responsibility model and IaaS/PaaS comparisons. 

|  Q | Answer | Explanation                                                                                    |
| -: | :----: | ---------------------------------------------------------------------------------------------- |
| 13 |  **B** | An IAM user can represent a person or application.                                             |
| 14 |  **A** | Groups simplify assigning identical permissions to several users.                              |
| 15 |  **B** | Policies define permitted or denied actions and resources.                                     |
| 16 |  **C** | A role is assumable and supplies temporary credentials.                                        |
| 17 |  **C** | An EC2 role avoids permanent credentials in application code.                                  |
| 18 |  **B** | Programmatic access traditionally uses an access key ID and secret access key.                 |
| 19 |  **A** | Console access uses the account ID or alias, IAM username and password, plus MFA when enabled. |
| 20 |  **B** | MFA adds a separate authentication code or device response.                                    |
| 21 |  **B** | Authentication verifies identity.                                                              |
| 22 |  **B** | Authorisation determines permitted actions.                                                    |

|  Q |  Answer  | Explanation                                                                            |
| -: | :------: | -------------------------------------------------------------------------------------- |
| 23 |   **C**  | Permissions begin as implicitly denied.                                                |
| 24 |   **B**  | Explicit deny overrides explicit allow.                                                |
| 25 |   **C**  | Explicit deny has the highest priority.                                                |
| 26 |   **B**  | Least privilege provides only the access required.                                     |
| 27 |   **B**  | A policy attached to a user, group or role is identity-based.                          |
| 28 |   **C**  | A policy attached directly to a resource is resource-based.                            |
| 29 | **A, C** | Groups contain users, and users can belong to several groups. Groups cannot be nested. |
| 30 | **B, C** | Services can assume roles, and roles provide temporary credentials.                    |

|  Q |  Answer  | Explanation                                                            |
| -: | :------: | ---------------------------------------------------------------------- |
| 31 |   **B**  | Create an administrative IAM identity, then avoid routine root use.    |
| 32 |   **C**  | Changing the AWS Support plan is listed as a root-user task.           |
| 33 | **B, D** | Protect root with MFA and create individual IAM identities.            |
| 34 |   **B**  | CloudTrail records API activity.                                       |
| 35 |   **A**  | CloudTrail can identify who changed the bucket policy.                 |
| 36 |   **B**  | The Cost and Usage Report provides usage and estimated-charge details. |

|  Q |  Answer  | Explanation                                                                                |
| -: | :------: | ------------------------------------------------------------------------------------------ |
| 37 |   **B**  | Organizations centrally manages multiple accounts and OUs.                                 |
| 38 |   **C**  | SCPs define maximum available permissions.                                                 |
| 39 |   **C**  | An SCP limits permissions but never grants them. IAM must still allow access.              |
| 40 |   **A**  | KMS creates and manages encryption keys.                                                   |
| 41 |   **B**  | Cognito provides customer sign-up, sign-in and application access control.                 |
| 42 |   **B**  | Shield protects against DDoS attacks.                                                      |
| 43 | **B, C** | Shield provides DDoS protection, and Shield Standard is available at no additional charge. |

|  Q |  Answer  | Explanation                                                                    |
| -: | :------: | ------------------------------------------------------------------------------ |
| 44 |   **B**  | At-rest data is stored physically on media.                                    |
| 45 |   **A**  | TLS protects network communication.                                            |
| 46 |   **B**  | HTTPS protects data in transit.                                                |
| 47 | **A, B** | EBS and EFS are among the KMS-supported examples in the module.                |
| 48 |   **A**  | S3 Block Public Access helps prevent unintended public access.                 |
| 49 |   **B**  | ACLs are described as a legacy S3 access-control mechanism.                    |
| 50 |   **B**  | Config evaluates and records resource configurations.                          |
| 51 |   **C**  | Artifact provides compliance reports and agreements.                           |
| 52 |   **B**  | AWS compliance does not remove the customer's own compliance responsibilities. |

</details>

---

# 4. Score interpretation

|        Score | Readiness                                                                          |
| -----------: | ---------------------------------------------------------------------------------- |
|    **47–52** | Strongly prepared                                                                  |
|    **41–46** | Nearly ready; revise specific mistakes                                             |
|    **33–40** | Basic understanding is present, but the distractors are still earning their salary |
| **Below 33** | Review shared responsibility and IAM before retesting                              |

---

# 5. The most dangerous exam confusions

## Multi-factor authentication versus permissions

```text
MFA → Helps prove identity
IAM policy → Determines permitted actions
```

MFA does not give a user permission to access S3.

## IAM role versus IAM group

```text
Group → Collection of users
Role  → Assumable permissions with temporary credentials
```

A role is not a group with a more impressive name.

## SCP versus IAM policy

```text
SCP        → Maximum permissions available
IAM policy → Actual permissions granted
```

SCPs do not grant access.

## CloudTrail versus Config versus Artifact

```text
CloudTrail → Who performed an action?
Config     → How was the resource configured?
Artifact   → Where are AWS compliance reports?
```

## Multi-AZ security responsibility trap

Using multiple Availability Zones may improve availability, but customers must still configure their workload to use them. AWS owns resilient infrastructure; it does not redesign a single-AZ customer application out of sympathy.

---

# 6. Final rapid-revision sheet

```text
SHARED RESPONSIBILITY

AWS:
- Physical facilities
- Hardware
- AWS networking
- Virtualisation
- Customer isolation

Customer:
- Data
- IAM
- EC2 guest OS
- Applications
- Security groups
- S3 permissions
- Encryption choices
```

```text
IAM

User   → Long-term identity
Group  → Users with common permissions
Policy → JSON permissions
Role   → Temporary assumable permissions

Explicit Deny > Explicit Allow > Implicit Deny
```

```text
NEW ACCOUNT

1. Avoid routine root use
2. Remove root access keys
3. Enable MFA
4. Create individual IAM identities
5. Use groups
6. Apply least privilege
7. Use roles
8. Configure password policy
9. Monitor with CloudTrail
```

```text
SECURITY SERVICES

Organizations → Multiple accounts
SCP           → Maximum permission boundary
KMS           → Encryption keys
Cognito       → Application users
Shield        → DDoS protection
CloudTrail    → API activity
Config        → Resource configurations
Artifact      → Compliance reports
```

```text
DATA SECURITY

At rest    → Stored data; encryption and KMS
In transit → Moving data; TLS and HTTPS

S3 controls:
- Block Public Access
- IAM policies
- Bucket policies
- ACLs
- Encryption
```

Send your answers in a format such as `1C, 2C, 3B...`, and I’ll grade them without using the answer key as a participation trophy.

[1]: https://docs.aws.amazon.com/aws-certification/latest/cloud-practitioner-02/cloud-practitioner-02.html "AWS Certified Cloud Practitioner (CLF-C02) - AWS Certified Cloud Practitioner"

---

</details>

<details>
<summary><strong>Module 5: Networking and Content Delivery — AWS-Style Objective Test Preparation</strong></summary>

# Module 5: Networking and Content Delivery — AWS-Style Objective Test Preparation

AWS certification questions use two formats:

* **Multiple choice:** one correct answer and three plausible distractors.
* **Multiple response:** two or more correct answers from five or more choices.

AWS deliberately makes distractors plausible, so questions usually test the **best solution**, not merely whether a statement sounds technically possible. ([AWS Documentation][1])

This mock test stays within the objectives of **AWS Academy Cloud Foundations Module 5**: networking basics, Amazon VPC, VPC architecture and connectivity, security groups, Route 53 and CloudFront. 

---

# 1. What to know before attempting the test

## Core network structure

```text
AWS Region
└── VPC
    ├── Public subnet in AZ A
    │   └── Public-facing resources
    └── Private subnet in AZ B
        └── Internal resources
```

* A **VPC** belongs to one Region but can span multiple Availability Zones.
* A **subnet** belongs to exactly one Availability Zone.
* A **route table** determines where subnet traffic is directed.
* A public subnet has a route to an **internet gateway**.
* A private resource can initiate outbound internet access through a **NAT gateway**. 

## High-priority comparisons

| Requirement                                        | Correct component |
| -------------------------------------------------- | ----------------- |
| Direct public internet connectivity                | Internet gateway  |
| Outbound internet from a private subnet            | NAT gateway       |
| Private access to supported AWS services           | VPC endpoint      |
| Connect two VPCs directly                          | VPC peering       |
| Encrypted on-premises connection over the internet | Site-to-Site VPN  |
| Dedicated connection to AWS                        | Direct Connect    |
| Centrally connect many VPCs and networks           | Transit Gateway   |

## Security controls

| Security group                       | Network ACL                        |
| ------------------------------------ | ---------------------------------- |
| Instance or ENI level                | Subnet level                       |
| Stateful                             | Stateless                          |
| Allow rules only                     | Allow and deny rules               |
| Automatically permits return traffic | Return traffic needs its own rule  |
| Evaluates all applicable rules       | Lowest-numbered matching rule wins |

## Route 53 versus CloudFront

```text
Route 53  → Finds the destination
CloudFront → Delivers content closer to users
```

* Route 53 is AWS’s scalable DNS service.
* CloudFront is AWS’s content delivery network.
* CloudFront uses edge locations and Regional edge caches to reduce latency.

---

# 2. Module 5 Mock Test

**Questions:** 50
**Suggested time:** 55 minutes
**Instructions:** Choose one answer unless the question says **Select TWO**.

---

## Networking basics

### 1. What is the primary purpose of a router?

A. To store website files
B. To forward traffic between networks
C. To assign IAM permissions
D. To encrypt stored data

---

### 2. How many bits are used in an IPv4 address?

A. 16 bits
B. 32 bits
C. 64 bits
D. 128 bits

---

### 3. How many bits are used in an IPv6 address?

A. 32 bits
B. 48 bits
C. 64 bits
D. 128 bits

---

### 4. What does the `/24` in `192.0.2.0/24` represent?

A. The network contains 24 devices
B. The first 24 bits identify the network
C. The final 24 bits identify hosts
D. The network supports only IPv6 traffic

---

### 5. Which CIDR block contains the largest number of addresses?

A. `/16`
B. `/20`
C. `/24`
D. `/28`

---

### 6. At which OSI layer do TCP and UDP operate?

A. Application layer
B. Transport layer
C. Network layer
D. Data-link layer

---

### 7. Which OSI layer handles routing and packet forwarding using IP addresses?

A. Physical layer
B. Data-link layer
C. Network layer
D. Presentation layer

---

### 8. Which protocol provides reliable, ordered delivery?

A. UDP
B. IP
C. TCP
D. MAC

---

## Amazon VPC and subnets

### 9. Which AWS service enables a company to create a logically isolated virtual network?

A. Amazon CloudFront
B. Amazon Route 53
C. Amazon VPC
D. AWS Direct Connect

---

### 10. Which statement correctly describes an Amazon VPC?

A. It spans every AWS Region automatically
B. It belongs to one Region and can span multiple Availability Zones
C. It belongs to one Availability Zone only
D. It is an edge-location resource

---

### 11. Which statement correctly describes a subnet?

A. It can span multiple Regions
B. It can span multiple Availability Zones
C. It belongs to one Availability Zone
D. It exists outside a VPC

---

### 12. A company creates two subnets in the same VPC. Which condition must be satisfied?

A. Their CIDR blocks must overlap
B. Their CIDR blocks must not overlap
C. They must exist in the same Availability Zone
D. They must use public IPv4 addresses

---

### 13. According to the module, what is the largest IPv4 CIDR block that can initially be assigned to a VPC?

A. `/8`
B. `/12`
C. `/16`
D. `/24`

---

### 14. According to the module, what is the smallest IPv4 CIDR block that can be assigned to a VPC?

A. `/16`
B. `/24`
C. `/28`
D. `/32`

---

### 15. A subnet has the CIDR block `10.0.1.0/24`. How many IPv4 addresses are usable by resources after AWS reserves five addresses?

A. 251
B. 252
C. 254
D. 256

---

### 16. Which addresses does AWS reserve in every IPv4 subnet? **Select TWO.**

A. The network address
B. Every even-numbered address
C. The VPC router address
D. Every address ending in `.10`
E. Every private IP address

---

### 17. A company requires a persistent public IPv4 address that can be remapped to another instance. Which resource should it use?

A. A private IP address
B. An Elastic IP address
C. A subnet CIDR block
D. A Route 53 health check

---

### 18. Which component acts as a virtual network card for an EC2 instance?

A. Internet gateway
B. Route table
C. Elastic network interface
D. NAT gateway

---

### 19. Which statements about an elastic network interface are correct? **Select TWO.**

A. It can be attached to an EC2 instance
B. It can contain a private IPv4 address
C. It replaces the VPC’s internet gateway
D. It automatically creates a new Availability Zone
E. It is a physical network cable

---

### 20. What information does a route contain?

A. A username and password
B. A source and security group
C. A destination and target
D. An Availability Zone and Region

---

### 21. What is the purpose of the built-in local route in a VPC route table?

A. To route traffic to the public internet
B. To enable communication within the VPC
C. To connect the VPC to an on-premises network
D. To cache content at an edge location

---

### 22. Which statement about route tables is correct?

A. A subnet can use several route tables simultaneously
B. Every subnet must be associated with a route table
C. Route tables contain IAM permissions
D. The local route should normally be deleted

---

## VPC internet connectivity

### 23. Which VPC component connects a VPC directly to the internet?

A. NAT gateway
B. Internet gateway
C. Virtual private gateway
D. Transit Gateway

---

### 24. Which route commonly makes a subnet public?

A. `10.0.0.0/16 → local`
B. `0.0.0.0/0 → internet gateway`
C. `0.0.0.0/0 → network ACL`
D. `10.0.0.0/16 → security group`

---

### 25. An EC2 instance must communicate directly with the internet. In addition to appropriate security rules, which configurations are needed? **Select TWO.**

A. A public IPv4 address
B. A route to an internet gateway
C. A route to an S3 gateway endpoint
D. A private-only DNS record
E. A network ACL that denies all traffic

---

### 26. A private EC2 instance must download operating-system updates from the internet without accepting unsolicited inbound internet connections. Which service should be used?

A. Internet gateway directly attached to the instance
B. NAT gateway
C. VPC peering
D. Route 53

---

### 27. In which subnet should a NAT gateway normally be deployed?

A. A public subnet
B. A private subnet with no internet route
C. A subnet in a different VPC
D. An edge-location subnet

---

### 28. Which route should a private subnet commonly use for outbound internet access?

A. `0.0.0.0/0 → NAT gateway`
B. `0.0.0.0/0 → local`
C. `10.0.0.0/16 → internet gateway`
D. `0.0.0.0/0 → security group`

---

## Connecting VPCs and external networks

### 29. A company wants to privately connect two VPCs directly. Which solution should it use?

A. Amazon CloudFront
B. VPC peering
C. Amazon Route 53
D. NAT gateway

---

### 30. Which restrictions apply to VPC peering? **Select TWO.**

A. The VPC CIDR ranges cannot overlap
B. VPC peering is transitive
C. Transitive peering is not supported
D. The VPCs must belong to the same Availability Zone
E. Peering can connect only public subnets

---

### 31. VPC A is peered with VPC B, and VPC B is peered with VPC C. What additional configuration is needed for VPC A to communicate with VPC C?

A. Nothing; peering is automatically transitive
B. A direct connection between VPC A and VPC C
C. A new security group in VPC B only
D. An edge location between the VPCs

---

### 32. A company requires an encrypted connection from its on-premises network to AWS over the public internet. Which solution should it use?

A. AWS Direct Connect
B. AWS Site-to-Site VPN
C. Amazon CloudFront
D. VPC sharing

---

### 33. Which components are involved in a Site-to-Site VPN connection? **Select TWO.**

A. Customer gateway
B. Regional edge cache
C. Virtual private gateway
D. NAT gateway
E. CloudFront origin

---

### 34. A company requires a dedicated network connection from its data centre to AWS with more consistent performance than an internet-based connection. Which service should it use?

A. AWS Direct Connect
B. AWS Site-to-Site VPN only
C. Amazon Route 53
D. Internet gateway

---

### 35. Which statement correctly compares Site-to-Site VPN and Direct Connect?

A. Both always use the ordinary public internet
B. VPN uses an encrypted internet connection, while Direct Connect provides dedicated connectivity
C. Direct Connect is a DNS service
D. VPN is used only between two VPCs

---

### 36. A private EC2 instance needs to access Amazon S3 without using a public IP address, NAT gateway or internet gateway. Which solution should be used?

A. VPC endpoint
B. Internet gateway
C. Elastic IP address
D. VPC peering

---

### 37. Which AWS services support gateway VPC endpoints in the module? **Select TWO.**

A. Amazon S3
B. Amazon DynamoDB
C. Amazon EC2
D. Amazon Route 53
E. Amazon CloudFront

---

### 38. A company must centrally connect dozens of VPCs, VPN connections and on-premises networks. Which service is the BEST fit?

A. A separate internet gateway for every connection
B. AWS Transit Gateway
C. Amazon CloudFront
D. One long chain of VPC peering connections

---

### 39. What is the main benefit of VPC sharing?

A. It allows several accounts to launch resources into centrally managed shared subnets
B. It automatically makes every subnet public
C. It replaces IAM and AWS Organizations
D. It replicates EC2 instances between Regions

---

## VPC security

### 40. At which level does a security group operate?

A. Region level
B. Subnet level
C. Instance or network-interface level
D. Edge-location level

---

### 41. Which statement about security-group rules is correct?

A. They support explicit allow and deny rules
B. They support allow rules only
C. They operate only at the subnet level
D. They are evaluated by rule number

---

### 42. What does it mean that security groups are stateful?

A. They remember allowed connections and automatically permit return traffic
B. They store the state of EC2 data volumes
C. They require separate inbound and outbound return rules
D. They deny all traffic permanently

---

### 43. A security-group inbound rule permits HTTPS traffic to an EC2 instance. What is required for the response traffic?

A. A separate outbound security-group rule is always required
B. The response is automatically allowed because the security group is stateful
C. A separate VPC must be created
D. A network ACL must be deleted

---

### 44. At which level does a network ACL operate?

A. Individual IAM-user level
B. Instance level
C. Subnet level
D. AWS-account level

---

### 45. Which statements about network ACLs are correct? **Select TWO.**

A. They are stateless
B. They support allow and deny rules
C. They automatically allow all return traffic
D. They operate only on individual EC2 instances
E. They contain IAM policies

---

### 46. How are network ACL rules evaluated?

A. The highest-numbered rule always wins
B. All rules are combined equally
C. Rules are evaluated from the lowest number until a match is found
D. The newest rule is evaluated first

---

### 47. A network ACL permits an inbound request. What must be done to permit the response?

A. Nothing, because network ACLs are stateful
B. Add an appropriate outbound rule
C. Attach an IAM role
D. Create an Elastic IP address

---

### 48. Which security control should be used to explicitly block traffic from a known malicious IP range at the subnet boundary?

A. Security group
B. Network ACL
C. IAM group
D. Route 53 weighted routing

---

## Amazon Route 53 and CloudFront

### 49. What is the primary function of Amazon Route 53?

A. To provide managed block storage
B. To translate domain names into IP addresses and route users
C. To cache website content
D. To create private EC2 instances

---

### 50. What is the primary function of Amazon CloudFront?

A. To create VPC route tables
B. To deliver cached content through locations closer to users
C. To assign private IP addresses
D. To provide a dedicated connection to AWS

---

### 51. A company wants to direct 90% of DNS traffic to version A and 10% to version B. Which Route 53 routing policy should it use?

A. Weighted routing
B. Failover routing
C. Latency-based routing
D. Simple routing

---

### 52. A global company wants users to be routed to the AWS Region that provides the lowest network delay. Which Route 53 policy should it use?

A. Geolocation routing
B. Latency-based routing
C. Weighted routing
D. Simple routing

---

### 53. A company wants Malaysian users to reach one application and European users to reach another based on geographic origin. Which policy should it use?

A. Failover routing
B. Weighted routing
C. Geolocation routing
D. Multivalue answer routing

---

### 54. A company wants Route 53 to send users to a backup website when the primary website becomes unhealthy. Which configuration should it use?

A. Weighted routing without health checks
B. Failover routing with health checks
C. Simple routing with a NAT gateway
D. Geolocation routing with an Elastic IP

---

### 55. Which service can register domain names, perform DNS resolution and support health checks?

A. Amazon Route 53
B. Amazon CloudFront
C. AWS Transit Gateway
D. Amazon VPC

---

### 56. What is a CloudFront origin?

A. The original location from which CloudFront retrieves content
B. The user’s nearest DNS resolver
C. A security-group rule
D. A CIDR block assigned to an edge location

---

### 57. A user requests an image that is already stored at the nearest CloudFront edge location. What occurs?

A. A cache hit
B. A cache miss
C. A DNS failover
D. VPC peering

---

### 58. A requested object is not available at the edge location. What can CloudFront do?

A. Permanently reject the request
B. Retrieve the object from a Regional edge cache or origin
C. Create a new VPC
D. Convert the object into an Elastic IP address

---

### 59. What is the purpose of a Regional edge cache?

A. To host EC2 instances
B. To retain less frequently accessed content between edge locations and the origin
C. To create private subnets
D. To replace Route 53

---

### 60. Which benefits are associated with CloudFront? **Select TWO.**

A. Lower content-delivery latency
B. Reduced load on the origin server
C. Automatic creation of VPC subnets
D. Dedicated physical connectivity to AWS
E. Operating-system patch management

---

# Stop before checking the answers

<details>
<summary><strong>Open answer key and explanations</strong></summary>

## Questions 1–8: Networking basics

|  Q | Answer | Explanation                                                            |
| -: | :----: | ---------------------------------------------------------------------- |
|  1 |  **B** | Routers forward traffic between networks or subnets.                   |
|  2 |  **B** | IPv4 addresses contain 32 bits.                                        |
|  3 |  **D** | IPv6 addresses contain 128 bits.                                       |
|  4 |  **B** | `/24` means the first 24 bits are fixed as the routing prefix.         |
|  5 |  **A** | A smaller prefix leaves more host bits, so `/16` is larger than `/28`. |
|  6 |  **B** | TCP and UDP operate at OSI Layer 4, the transport layer.               |
|  7 |  **C** | IP routing and packet forwarding occur at the network layer.           |
|  8 |  **C** | TCP provides reliable, ordered delivery.                               |

---

## Questions 9–22: VPC fundamentals

|  Q |  Answer  | Explanation                                                                                   |
| -: | :------: | --------------------------------------------------------------------------------------------- |
|  9 |   **C**  | Amazon VPC creates a logically isolated virtual network.                                      |
| 10 |   **B**  | A VPC belongs to one Region but can span several AZs.                                         |
| 11 |   **C**  | Each subnet exists in one Availability Zone.                                                  |
| 12 |   **B**  | Subnet address ranges cannot overlap.                                                         |
| 13 |   **C**  | The largest VPC IPv4 block stated in the module is `/16`.                                     |
| 14 |   **C**  | The smallest VPC IPv4 block stated in the module is `/28`.                                    |
| 15 |   **A**  | A `/24` contains 256 addresses; AWS reserves five, leaving 251.                               |
| 16 | **A, C** | AWS reserves the network address and VPC-router address, among five total reserved addresses. |
| 17 |   **B**  | An Elastic IP is persistent and can be remapped.                                              |
| 18 |   **C**  | An ENI acts as a virtual network interface.                                                   |
| 19 | **A, B** | An ENI can attach to an instance and carry private IP information.                            |
| 20 |   **C**  | Each route identifies a destination and target.                                               |
| 21 |   **B**  | The local route supports communication inside the VPC.                                        |
| 22 |   **B**  | Every subnet must be associated with one route table.                                         |

The module’s diagrams place the VPC at the Region level, subnets within individual Availability Zones and route tables at the centre of traffic control. 

---

## Questions 23–39: VPC connectivity

|  Q |  Answer  | Explanation                                                                            |
| -: | :------: | -------------------------------------------------------------------------------------- |
| 23 |   **B**  | An internet gateway connects a VPC to the internet.                                    |
| 24 |   **B**  | A default route targeting an internet gateway makes internet routing possible.         |
| 25 | **A, B** | Direct connectivity requires a public address and a route to the internet gateway.     |
| 26 |   **B**  | A NAT gateway provides outbound internet access for private resources.                 |
| 27 |   **A**  | A NAT gateway must be in a public subnet so it can reach the internet gateway.         |
| 28 |   **A**  | The private subnet sends default outbound traffic to the NAT gateway.                  |
| 29 |   **B**  | VPC peering privately connects two VPCs.                                               |
| 30 | **A, C** | Peered VPCs cannot have overlapping IP ranges, and peering is non-transitive.          |
| 31 |   **B**  | A direct A-to-C connection or another routing solution is required.                    |
| 32 |   **B**  | Site-to-Site VPN creates encrypted connectivity over the public internet.              |
| 33 | **A, C** | It uses a customer gateway and a virtual private gateway.                              |
| 34 |   **A**  | Direct Connect provides dedicated network connectivity.                                |
| 35 |   **B**  | VPN uses encrypted internet tunnels; Direct Connect provides a dedicated path.         |
| 36 |   **A**  | A VPC endpoint enables private access to supported AWS services.                       |
| 37 | **A, B** | Gateway endpoints are used for S3 and DynamoDB.                                        |
| 38 |   **B**  | Transit Gateway provides a central networking hub.                                     |
| 39 |   **A**  | VPC sharing lets participant accounts deploy resources into centrally managed subnets. |

The module lists internet gateways, NAT gateways, endpoints, peering, sharing, VPN, Direct Connect and Transit Gateway as its major VPC networking options.

---

## Questions 40–48: VPC security

|  Q |  Answer  | Explanation                                                             |
| -: | :------: | ----------------------------------------------------------------------- |
| 40 |   **C**  | Security groups protect instances and network interfaces.               |
| 41 |   **B**  | Security groups contain allow rules, not explicit deny rules.           |
| 42 |   **A**  | Stateful controls remember connections and permit response traffic.     |
| 43 |   **B**  | Return traffic is automatically allowed.                                |
| 44 |   **C**  | Network ACLs operate at the subnet boundary.                            |
| 45 | **A, B** | Network ACLs are stateless and support both allow and deny rules.       |
| 46 |   **C**  | The lowest-numbered matching rule is applied first.                     |
| 47 |   **B**  | Stateless ACLs require a suitable outbound response rule.               |
| 48 |   **B**  | A network ACL can explicitly deny the malicious source at subnet level. |

---

## Questions 49–60: Route 53 and CloudFront

|  Q |  Answer  | Explanation                                                                  |
| -: | :------: | ---------------------------------------------------------------------------- |
| 49 |   **B**  | Route 53 provides DNS resolution and traffic routing.                        |
| 50 |   **B**  | CloudFront is a CDN that serves content closer to users.                     |
| 51 |   **A**  | Weighted routing divides traffic according to assigned percentages.          |
| 52 |   **B**  | Latency-based routing chooses the lowest-latency destination.                |
| 53 |   **C**  | Geolocation routing uses the user’s geographic location.                     |
| 54 |   **B**  | Failover routing and health checks redirect traffic when the primary fails.  |
| 55 |   **A**  | Route 53 provides domain registration, DNS and health-check capabilities.    |
| 56 |   **A**  | The origin is the original source of the content.                            |
| 57 |   **A**  | Finding the content in the edge cache is a cache hit.                        |
| 58 |   **B**  | CloudFront requests missing content from a larger cache or the origin.       |
| 59 |   **B**  | Regional edge caches retain less popular content closer than the origin.     |
| 60 | **A, B** | Caching reduces user latency and the number of requests reaching the origin. |

</details>

---

# 3. Score interpretation

|        Score | Readiness                                                                       |
| -----------: | ------------------------------------------------------------------------------- |
|    **54–60** | Strongly prepared                                                               |
|    **47–53** | Nearly ready; revise the specific mistakes                                      |
|    **38–46** | Core understanding exists, but AWS distractors are still winning too often      |
| **Below 38** | Review VPC routing, security groups versus ACLs, and Route 53 versus CloudFront |

---

# 4. The most dangerous exam confusions

## Public subnet versus public instance

A public subnet has a route to an internet gateway.

An instance inside it still normally needs:

```text
Public IPv4 address
+
Security permission
+
Internet-gateway route
```

Merely placing something in a public subnet does not ceremonially expose it to the internet.

---

## Internet gateway versus NAT gateway

```text
Internet gateway → Direct public connectivity
NAT gateway      → Outbound connectivity for private resources
```

The NAT gateway belongs in a public subnet, while the private subnet routes traffic to it.

---

## Security group versus network ACL

```text
Security group:
- Instance level
- Stateful
- Allow only

Network ACL:
- Subnet level
- Stateless
- Allow and deny
```

---

## VPC peering versus Transit Gateway

```text
Few direct VPC connections → VPC peering
Many VPCs and networks     → Transit Gateway
```

Peering is non-transitive. A peering chain is not a network architecture; it is a future apology to whoever must maintain it.

---

## Route 53 versus CloudFront

```text
Route 53  → Resolves and routes
CloudFront → Caches and delivers
```

Route 53 tells users where to go. CloudFront reduces how far content must travel.

---

# 5. Rapid revision sheet

```text
NETWORK BASICS

IPv4 → 32 bits
IPv6 → 128 bits
CIDR → Number of fixed network bits
TCP  → Reliable
UDP  → Faster, no delivery guarantee
```

```text
VPC

VPC    → One Region
Subnet → One Availability Zone
Route  → Destination + target
Local route → Internal VPC traffic
```

```text
CONNECTIVITY

Internet gateway → Public internet
NAT gateway      → Private outbound internet
VPC endpoint     → Private AWS-service access
Peering          → Direct VPC-to-VPC
VPN              → Encrypted internet connection
Direct Connect   → Dedicated connection
Transit Gateway  → Central network hub
```

```text
SECURITY

Security group:
- Instance/ENI
- Stateful
- Allow only

Network ACL:
- Subnet
- Stateless
- Allow and deny
- Lowest rule number wins
```

```text
CONTENT DELIVERY

Route 53:
- DNS
- Routing policies
- Health checks
- Failover

CloudFront:
- CDN
- Edge locations
- Regional edge caches
- Lower latency
- Reduced origin load
```

Send your answers as `1B, 2B, 3D...`, and I’ll grade them while separating genuine misunderstandings from questions where AWS merely disguised the obvious answer in corporate vocabulary.

[1]: https://docs.aws.amazon.com/aws-certification/latest/cloud-practitioner-02/cloud-practitioner-02.html?utm_source=chatgpt.com "AWS Certified Cloud Practitioner (CLF-C02) - AWS Certified Cloud Practitioner"


---

</details>

<details>
<summary><strong>Module 6: Compute — AWS-Style Objective Test Preparation</strong></summary>

# Module 6: Compute — AWS-Style Objective Test Preparation

The current AWS Certified Cloud Practitioner exam uses:

* **Multiple choice:** one correct response and three plausible distractors.
* **Multiple response:** two or more correct responses from at least five options.

AWS states that distractors are deliberately written as plausible choices for candidates with incomplete knowledge. In other words, the test rarely asks whether a service *could* work; it asks which service **best** matches the requirement. ([AWS Documentation][1])

This mock test follows the uploaded Module 6 objectives: compute-service selection, Amazon EC2, EC2 cost optimisation, containers, AWS Lambda and AWS Elastic Beanstalk. 

---

# 1. What to know before attempting the test

## Compute-service selection

| Requirement                                              | Best starting service |
| -------------------------------------------------------- | --------------------- |
| Full control over a virtual machine and operating system | Amazon EC2            |
| Run short code in response to events                     | AWS Lambda            |
| Deploy a standard web application quickly                | AWS Elastic Beanstalk |
| AWS-native container orchestration                       | Amazon ECS            |
| Kubernetes on AWS                                        | Amazon EKS            |
| Run containers without managing servers                  | AWS Fargate           |
| Store container images                                   | Amazon ECR            |

```text
More infrastructure control                         Less infrastructure work

EC2 → ECS on EC2 → Fargate → Elastic Beanstalk/Lambda
```

The correct service depends on the application design, usage pattern and how much infrastructure the customer wants to manage. 

## EC2 launch decisions

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

## EC2 pricing

| Workload                                      | Pricing model      |
| --------------------------------------------- | ------------------ |
| Short-term or unpredictable                   | On-Demand          |
| Predictable and long-running                  | Reserved Instances |
| Flexible and interruption-tolerant            | Spot Instances     |
| Licensing or physical-server requirements     | Dedicated Host     |
| Dedicated hardware without host-level control | Dedicated Instance |

## Container-service map

```text
Docker  → Packages and runs containers
ECR     → Stores container images
ECS     → AWS-native container orchestration
EKS     → Kubernetes orchestration on AWS
Fargate → Serverless compute for containers
```

## Lambda versus Elastic Beanstalk

| AWS Lambda                            | Elastic Beanstalk                          |
| ------------------------------------- | ------------------------------------------ |
| Function-based                        | Application-based                          |
| Event-driven                          | Web-application environment                |
| Runs only when invoked                | Environment remains deployed               |
| No server management                  | AWS provisions underlying resources        |
| Maximum runtime in module: 15 minutes | Suitable for conventional web applications |

---

# 2. Module 6 Mock Test

**Questions:** 60
**Suggested time:** 65 minutes
**Instructions:** Select one answer unless the question says **Select TWO**.

---

## Compute-service overview

### 1. A company requires complete control over the operating system and installed software of a cloud-based virtual machine. Which AWS service should it use?

A. AWS Lambda
B. Amazon EC2
C. AWS Fargate
D. AWS Elastic Beanstalk

---

### 2. A company needs code to run automatically whenever a file is uploaded to Amazon S3. The company does not want to manage servers. Which service is the BEST fit?

A. Amazon EC2
B. Amazon EKS
C. AWS Lambda
D. Amazon ECR

---

### 3. A development team wants to upload its web-application code while AWS handles provisioning, deployment, load balancing and scaling. Which service should it use?

A. AWS Elastic Beanstalk
B. Amazon ECR
C. Amazon EC2 Instance Store
D. Amazon ECS on EC2

---

### 4. Which services are associated with container-based computing? **Select TWO.**

A. Amazon ECS
B. Amazon Route 53
C. Amazon EKS
D. Amazon RDS
E. Amazon CloudFront

---

### 5. Which AWS service provides a managed registry for storing container images?

A. Amazon ECR
B. Amazon ECS
C. Amazon EKS
D. AWS Lambda

---

### 6. A company already uses Kubernetes and wants to run Kubernetes-compatible workloads on AWS. Which service should it use?

A. AWS Elastic Beanstalk
B. Amazon EKS
C. Amazon ECR
D. Amazon EC2 Auto Scaling

---

### 7. Which factors should a company consider when choosing an AWS compute service? **Select TWO.**

A. Application design
B. The colour of the AWS service icon
C. Workload usage patterns
D. The number of IAM groups in the account
E. The number of CloudFront edge locations

---

## Amazon EC2 concepts and launch configuration

### 8. What is an Amazon Machine Image?

A. A running EC2 instance
B. A template used to launch EC2 instances
C. A physical server dedicated to one customer
D. A security rule attached to an instance

---

### 9. Which are valid sources of AMIs in the EC2 launch process? **Select TWO.**

A. Quick Start AMIs
B. Route 53 health checks
C. AWS Marketplace AMIs
D. Network ACLs
E. IAM groups

---

### 10. A company configures an EC2 instance with its required operating system, security tools and application software. It wants to launch identical instances later. What should it do?

A. Capture the configured instance as a custom AMI
B. Create a new security group for every launch
C. Convert the instance into an Elastic IP address
D. Store the instance metadata in Route 53

---

### 11. What does an EC2 instance type primarily determine?

A. The user's IAM permissions
B. CPU, memory, storage options and network performance
C. The selected AWS Support plan
D. The number of Availability Zones in a Region

---

### 12. In the instance type name `t3.large`, what does `large` represent?

A. The AWS Region
B. The operating-system version
C. The instance size
D. The storage encryption type

---

### 13. Which EC2 instance category is intended for CPU-intensive processing?

A. Compute optimised
B. Memory optimised
C. Storage optimised
D. General purpose only

---

### 14. Which instance category is most appropriate for a large in-memory database?

A. Accelerated computing
B. Memory optimised
C. General purpose
D. Storage optimised

---

### 15. A machine-learning workload requires specialised hardware such as GPUs. Which instance category is the BEST fit?

A. General purpose
B. Memory optimised
C. Accelerated computing
D. Storage optimised

---

### 16. Which settings determine where an EC2 instance is deployed? **Select TWO.**

A. VPC
B. Subnet
C. IAM group
D. AWS Artifact report
E. S3 lifecycle policy

---

### 17. An application on an EC2 instance needs permission to read objects from an S3 bucket. Which solution follows AWS best practices?

A. Store the root user's password on the EC2 instance
B. Attach an IAM role with the required S3 permissions
C. Open port 22 in the security group
D. Make the S3 bucket public

---

### 18. What is EC2 user data commonly used for?

A. Defining an instance's physical location
B. Running an initial configuration script when the instance launches
C. Creating AWS account users
D. Recording API activity

---

### 19. A company needs persistent block storage for an EC2 operating-system volume. Which storage should it use?

A. Amazon EBS
B. EC2 Instance Store
C. Amazon CloudFront
D. Amazon ECR

---

### 20. Which storage option is appropriate for temporary data that can be recreated if the instance is stopped or terminated?

A. Amazon EBS
B. Amazon S3 Glacier
C. EC2 Instance Store
D. Amazon EFS

---

### 21. What is the purpose of EC2 tags?

A. To define inbound network ports
B. To attach key-value metadata to resources
C. To replace IAM policies
D. To create operating systems

---

### 22. Which EC2 configuration controls allowed inbound and outbound network traffic?

A. IAM role
B. Security group
C. AMI
D. User data

---

### 23. What is the main purpose of an EC2 key pair?

A. To distribute application traffic
B. To provide secure administrative access to an instance
C. To automatically scale instances
D. To store container images

---

### 24. Which launch decisions are primarily related to EC2 security? **Select TWO.**

A. Security group
B. Key pair
C. Instance generation
D. Tag value
E. AMI description

---

### 25. Which EC2 instances can be stopped according to the module?

A. Only instances backed by Amazon EBS
B. Only instances using Instance Store
C. Only Spot Instances
D. Every EC2 instance regardless of storage

---

### 26. What happens when an EBS-backed EC2 instance is stopped?

A. The instance is permanently deleted
B. Its EBS data can remain available for a later start
C. The instance becomes an AMI automatically
D. Its security groups are deleted

---

### 27. Which action permanently removes an EC2 instance so that it cannot simply be started again?

A. Reboot
B. Stop
C. Hibernate
D. Terminate

---

### 28. An EC2 instance is rebooted. Which statement is correct?

A. It must be launched from a new AMI
B. It restarts and returns to the running state
C. Its EBS volumes are always deleted
D. It becomes a Reserved Instance

---

### 29. An EC2 instance uses an automatically assigned public IPv4 address. What can happen when the instance is stopped and started?

A. The public IPv4 address may change
B. The private IPv4 address must change
C. The instance type always changes
D. The security group is deleted

---

### 30. A company requires a persistent public IPv4 address for an EC2 instance. Which resource should it use?

A. Instance metadata
B. Elastic IP address
C. User data
D. AMI

---

### 31. An application needs to determine the ID and Availability Zone of the EC2 instance on which it is running. What should it use?

A. Instance metadata
B. AWS Artifact
C. An S3 lifecycle rule
D. Amazon ECR

---

### 32. Which AWS service collects metrics such as EC2 CPU utilisation and network activity?

A. AWS CloudTrail
B. Amazon CloudWatch
C. Amazon Cognito
D. AWS Artifact

---

### 33. According to the module, how often does basic EC2 monitoring provide metrics?

A. Every second
B. Every minute
C. Every five minutes
D. Every hour

---

### 34. According to the module, how often can detailed EC2 monitoring provide metrics?

A. Every minute
B. Every five minutes
C. Every 15 minutes
D. Once per day

---

## EC2 pricing and cost optimisation

### 35. A company needs an EC2 instance for a temporary workload with unpredictable usage. It does not want a long-term commitment. Which pricing model should it use?

A. Reserved Instances
B. On-Demand Instances
C. Dedicated Hosts
D. Scheduled Reserved Instances

---

### 36. A company expects to run a stable production workload continuously for three years. Which pricing model can provide a discount in exchange for commitment?

A. Spot Instances
B. On-Demand Instances
C. Reserved Instances
D. Instance Store pricing

---

### 37. A batch-processing job can be interrupted and restarted later. The company wants the lowest possible compute price. Which pricing model is the BEST fit?

A. Spot Instances
B. Dedicated Hosts
C. On-Demand Instances
D. Scheduled Reserved Instances

---

### 38. Which workload is LEAST suitable for Spot Instances?

A. Fault-tolerant batch processing
B. Flexible data analysis
C. A single critical database that cannot tolerate interruption
D. Image rendering that can resume later

---

### 39. A company has software licences that are bound to a physical server. Which EC2 purchasing option is the BEST fit?

A. Spot Instance
B. Dedicated Host
C. On-Demand Instance
D. Fargate task

---

### 40. Which statement correctly compares Dedicated Instances and Dedicated Hosts?

A. Dedicated Hosts provide an entire physical server, while Dedicated Instances run on hardware dedicated to one customer
B. Dedicated Instances are serverless, while Dedicated Hosts are virtual machines
C. Dedicated Hosts are used only for Lambda
D. They are identical services with different names

---

### 41. A workload runs every Monday from 8:00 a.m. until 5:00 p.m. and requires reserved capacity on that recurring schedule. Which option from the module is designed for this pattern?

A. Spot Instances
B. Scheduled Reserved Instances
C. Elastic IP addresses
D. General Purpose Instances

---

### 42. A company has a predictable baseline workload but sometimes receives unexpected traffic. Which pricing combination is sensible? **Select TWO.**

A. Reserved Instances for baseline demand
B. On-Demand Instances for unexpected demand
C. Dedicated Hosts for every temporary request
D. Spot Instances for a non-interruptible payment database
E. Terminated instances for baseline demand

---

### 43. An EC2 instance has 16 vCPUs but averages only 3% CPU utilisation. Which cost-optimisation action should the company consider first?

A. Move to a larger instance
B. Right-size to a smaller instance
C. Purchase a Dedicated Host immediately
D. Increase the EBS volume size

---

### 44. A development server is not required during nights and weekends. Which cost-optimisation approach should be used?

A. Leave it running for convenience
B. Stop it when it is not needed
C. Convert it into an edge location
D. Replace its security group

---

### 45. Which are pillars of EC2 cost optimisation in the module? **Select TWO.**

A. Right-size resources
B. Increase elasticity
C. Use the root user
D. Increase the number of unused volumes
E. Store permanent credentials in code

---

### 46. Which action supports storage cost optimisation?

A. Retain every unattached volume permanently
B. Delete unused volumes and unnecessary snapshots
C. Use the most expensive volume type for every workload
D. Store temporary cache data only on Provisioned IOPS volumes

---

## Container services

### 47. What does a container commonly package?

A. Application code and its dependencies
B. A complete AWS Region
C. Physical server hardware
D. IAM account credentials only

---

### 48. Which statement correctly compares containers and virtual machines?

A. Every container requires a complete guest operating system
B. Containers generally share the host operating-system kernel
C. Virtual machines cannot run applications
D. Containers are always larger than virtual machines

---

### 49. What is Docker primarily used for?

A. Building, packaging and running containers
B. Resolving domain names
C. Managing encryption keys
D. Providing block storage

---

### 50. What is the difference between a container image and a container?

A. An image is a running workload, while a container is a template
B. An image is a template, while a container is a running instance of that image
C. They are unrelated AWS services
D. A container image is an IAM policy

---

### 51. Why is container orchestration needed?

A. To coordinate deployment, scaling and replacement of many containers
B. To replace all application code
C. To provide physical data-centre security
D. To register internet domains

---

### 52. Which AWS service provides AWS-native orchestration for Docker containers?

A. Amazon ECS
B. Amazon ECR
C. Amazon S3
D. Amazon Route 53

---

### 53. A company wants to run ECS containers while retaining control of the underlying EC2 instances. Which launch approach should it use?

A. ECS backed by Amazon EC2
B. ECS backed by CloudFront
C. AWS Lambda
D. Amazon ECR only

---

### 54. A company wants to run containers without provisioning or managing the underlying servers. Which service should it use?

A. Amazon ECR
B. AWS Fargate
C. Amazon Machine Images
D. EC2 Instance Store

---

### 55. What is Kubernetes?

A. Open-source container-orchestration software
B. An EC2 purchasing model
C. A block-storage service
D. A DNS service

---

### 56. Which tasks can Kubernetes automate? **Select TWO.**

A. Container provisioning
B. Container scaling
C. Domain registration
D. Physical data-centre cooling
E. AWS account billing

---

### 57. Which AWS service enables customers to run Kubernetes on AWS?

A. Amazon ECS
B. Amazon EKS
C. Amazon ECR
D. AWS Elastic Beanstalk

---

### 58. What is the primary purpose of Amazon ECR?

A. Run Kubernetes clusters
B. Store, manage and deploy container images
C. Execute Lambda functions
D. Automatically patch EC2 operating systems

---

## AWS Lambda

### 59. What does “serverless” mean in the context of AWS Lambda?

A. No physical servers exist
B. AWS manages the underlying servers for the customer
C. The function cannot access other AWS services
D. The function runs permanently

---

### 60. Which services can act as Lambda event sources? **Select TWO.**

A. Amazon S3
B. Amazon SQS
C. EC2 key pairs
D. Dedicated Hosts
E. EBS snapshots only

---

### 61. A Lambda function must write a generated thumbnail to an S3 bucket. What grants the function permission to perform this action?

A. Lambda execution role
B. Security group only
C. Container image tag
D. Elastic IP address

---

### 62. A company wants to automatically stop development EC2 instances every night. Which solution from the module is appropriate?

A. A scheduled event that invokes a Lambda function
B. An S3 bucket policy
C. An Elastic IP address
D. A Dedicated Host

---

### 63. According to the module, what is the maximum execution time for one Lambda invocation?

A. 1 minute
B. 5 minutes
C. 15 minutes
D. Unlimited

---

### 64. According to the module, what is the maximum memory allocation for one Lambda function?

A. 512 MB
B. 1,024 MB
C. 5,120 MB
D. 10,240 MB

---

### 65. Which benefits are associated with AWS Lambda? **Select TWO.**

A. Automatic scaling
B. Built-in fault tolerance
C. Required operating-system patching by the customer
D. Permanently running virtual machines
E. Full physical-host control

---

## AWS Elastic Beanstalk

### 66. Which workload is the BEST fit for AWS Elastic Beanstalk?

A. A standard web application that developers want to deploy quickly
B. A physical-server licensing workload
C. A container-image registry
D. A function that runs for three seconds after an S3 upload

---

### 67. Which tasks can Elastic Beanstalk automatically handle? **Select TWO.**

A. Infrastructure provisioning
B. Load balancing
C. Creating IAM users for every application customer
D. Building AWS Regions
E. Replacing DNS with an EC2 key pair

---

### 68. What does the customer primarily manage when using Elastic Beanstalk?

A. Application code
B. Physical host hardware
C. AWS global networking
D. Data-centre power

---

### 69. Which application platforms are supported by Elastic Beanstalk according to the module? **Select TWO.**

A. Python
B. Node.js
C. Route 53
D. DynamoDB Query
E. Network ACL

---

### 70. How is AWS Elastic Beanstalk priced?

A. A fixed licence fee is charged for every application
B. There is no additional Beanstalk service charge; customers pay for underlying AWS resources
C. It is free, including all EC2 instances and load balancers
D. It is charged only according to the number of IAM users

---

# Stop before opening the answers

<details>
<summary><strong>Open answer key and explanations</strong></summary>

## Questions 1–7: Compute-service selection

|  Q |  Answer  | Explanation                                                                  |
| -: | :------: | ---------------------------------------------------------------------------- |
|  1 |   **B**  | EC2 provides virtual machines and guest-OS control.                          |
|  2 |   **C**  | Lambda is serverless and can run in response to events such as an S3 upload. |
|  3 |   **A**  | Elastic Beanstalk deploys and manages web-application environments.          |
|  4 | **A, C** | ECS and EKS are container-orchestration services.                            |
|  5 |   **A**  | ECR is the managed container-image registry.                                 |
|  6 |   **B**  | EKS runs Kubernetes-compatible workloads on AWS.                             |
|  7 | **A, C** | Application design and usage patterns affect the correct compute choice.     |

The module categorises EC2 as virtual-machine IaaS, Lambda as function-based serverless compute, ECS/EKS/Fargate/ECR as container services and Elastic Beanstalk as a web-application PaaS. 

---

## Questions 8–34: Amazon EC2

|  Q |  Answer  | Explanation                                                                     |
| -: | :------: | ------------------------------------------------------------------------------- |
|  8 |   **B**  | An AMI is the template used to create an instance.                              |
|  9 | **A, C** | Quick Start and AWS Marketplace are AMI sources.                                |
| 10 |   **A**  | A configured instance can be captured as a reusable custom AMI.                 |
| 11 |   **B**  | Instance type controls compute, memory, storage options and network capability. |
| 12 |   **C**  | `large` identifies the size.                                                    |
| 13 |   **A**  | Compute-optimised instances suit CPU-heavy workloads.                           |
| 14 |   **B**  | Memory-optimised instances suit large in-memory workloads.                      |
| 15 |   **C**  | Accelerated-computing instances provide specialised hardware such as GPUs.      |
| 16 | **A, B** | The VPC and subnet determine network placement.                                 |
| 17 |   **B**  | An IAM role supplies temporary AWS service permissions.                         |
| 18 |   **B**  | User data commonly runs an initial launch script.                               |
| 19 |   **A**  | EBS provides persistent block storage.                                          |
| 20 |   **C**  | Instance Store is appropriate for temporary, recreatable data.                  |
| 21 |   **B**  | Tags are key-value metadata used for organisation and automation.               |
| 22 |   **B**  | Security groups control allowed network traffic.                                |
| 23 |   **B**  | A key pair supports secure administrative login.                                |
| 24 | **A, B** | Security groups and key pairs are direct security-related launch choices.       |
| 25 |   **A**  | The module states that only EBS-backed instances can be stopped.                |
| 26 |   **B**  | Stopping preserves the EBS-backed instance for a later start.                   |
| 27 |   **D**  | Termination permanently removes the instance.                                   |
| 28 |   **B**  | Reboot restarts the instance and returns it to running.                         |
| 29 |   **A**  | An automatically assigned public IPv4 address may change after stop/start.      |
| 30 |   **B**  | An Elastic IP provides a persistent, remappable public address.                 |
| 31 |   **A**  | Instance metadata exposes information about the running instance.               |
| 32 |   **B**  | CloudWatch collects EC2 metrics.                                                |
| 33 |   **C**  | Basic monitoring uses five-minute intervals in the module.                      |
| 34 |   **A**  | Detailed monitoring uses one-minute intervals in the module.                    |

The module’s launch process covers AMIs, instance types, networking, IAM roles, user data, storage, tags, security groups and key pairs. It also distinguishes stop, reboot and termination and identifies CloudWatch as the EC2 metrics service.

---

## Questions 35–46: EC2 pricing and optimisation

|  Q |  Answer  | Explanation                                                                                                                        |
| -: | :------: | ---------------------------------------------------------------------------------------------------------------------------------- |
| 35 |   **B**  | On-Demand provides flexibility without long-term commitment.                                                                       |
| 36 |   **C**  | Reserved Instances suit stable usage over one- or three-year terms.                                                                |
| 37 |   **A**  | Spot is suitable for flexible, interruption-tolerant processing.                                                                   |
| 38 |   **C**  | A non-interruptible critical database is unsuitable for Spot.                                                                      |
| 39 |   **B**  | Dedicated Hosts expose dedicated physical-server capacity for licensing needs.                                                     |
| 40 |   **A**  | A Dedicated Host is an entire physical host; Dedicated Instances use single-customer hardware without the same host-level control. |
| 41 |   **B**  | Scheduled Reserved Instances cover recurring scheduled capacity in the module.                                                     |
| 42 | **A, B** | Reserved can cover baseline usage, while On-Demand covers unpredictable peaks.                                                     |
| 43 |   **B**  | Right-sizing reduces wasted compute capacity.                                                                                      |
| 44 |   **B**  | Stopping unused environments increases elasticity and reduces wasted running time.                                                 |
| 45 | **A, B** | Right-sizing and elasticity are two of the four pillars.                                                                           |
| 46 |   **B**  | Removing unused storage and snapshots reduces unnecessary cost.                                                                    |

The four cost-optimisation pillars are right-sizing, increasing elasticity, choosing the optimal pricing model and optimising storage choices.

---

## Questions 47–58: Containers

|  Q |  Answer  | Explanation                                                                     |
| -: | :------: | ------------------------------------------------------------------------------- |
| 47 |   **A**  | A container packages application code, libraries and dependencies.              |
| 48 |   **B**  | Containers share the host OS kernel and are lighter than full virtual machines. |
| 49 |   **A**  | Docker builds, packages and runs containers.                                    |
| 50 |   **B**  | The image is the template; the container is its running instance.               |
| 51 |   **A**  | Orchestration manages deployment, scaling, networking and replacement.          |
| 52 |   **A**  | ECS is AWS-native container orchestration.                                      |
| 53 |   **A**  | ECS on EC2 provides greater control over the underlying servers.                |
| 54 |   **B**  | Fargate runs containers without customers managing the servers.                 |
| 55 |   **A**  | Kubernetes is open-source container-orchestration software.                     |
| 56 | **A, B** | Kubernetes automates provisioning and scaling, among other container tasks.     |
| 57 |   **B**  | EKS is managed Kubernetes on AWS.                                               |
| 58 |   **B**  | ECR stores and manages container images.                                        |

The module distinguishes ECS on EC2 from ECS on Fargate and describes EKS as Kubernetes on AWS and ECR as the image registry.

---

## Questions 59–65: AWS Lambda

|  Q |  Answer  | Explanation                                                      |
| -: | :------: | ---------------------------------------------------------------- |
| 59 |   **B**  | Servers still exist, but AWS provisions and manages them.        |
| 60 | **A, B** | S3 and SQS can invoke Lambda functions.                          |
| 61 |   **A**  | The execution role authorises the function to call AWS services. |
| 62 |   **A**  | A scheduled event can trigger Lambda to start or stop instances. |
| 63 |   **C**  | The module gives a maximum execution time of 15 minutes.         |
| 64 |   **D**  | The module gives a maximum memory allocation of 10,240 MB.       |
| 65 | **A, B** | Lambda provides automatic scaling and built-in fault tolerance.  |

Lambda runs code only when invoked by an event or direct request, uses execution roles for AWS permissions and integrates with services such as S3, DynamoDB, SNS, SQS and API Gateway.

---

## Questions 66–70: AWS Elastic Beanstalk

|  Q |  Answer  | Explanation                                                                       |
| -: | :------: | --------------------------------------------------------------------------------- |
| 66 |   **A**  | Beanstalk is intended for quickly deploying conventional web applications.        |
| 67 | **A, B** | It can provision infrastructure and configure load balancing.                     |
| 68 |   **A**  | The customer mainly manages the application code.                                 |
| 69 | **A, B** | Python and Node.js are supported platforms.                                       |
| 70 |   **B**  | Beanstalk has no additional service charge; underlying resources remain billable. |

Elastic Beanstalk can handle provisioning, deployment, load balancing, Auto Scaling, health monitoring, logging and debugging for supported web platforms. 

</details>

---

# 3. Score interpretation

There are **70 questions**, including multiple-response questions.

|        Score | Readiness                                                              |
| -----------: | ---------------------------------------------------------------------- |
|    **63–70** | Strongly prepared                                                      |
|    **55–62** | Nearly ready; revise isolated weaknesses                               |
|    **44–54** | Core knowledge exists, but similar services are still getting mixed up |
| **Below 44** | Review EC2 launch decisions, pricing and container-service roles       |

For multiple-response questions, count the answer as correct only when **all required choices** are selected and no incorrect choice is added. AWS is not known for awarding marks because the candidate was spiritually close.

---

# 4. The most dangerous exam confusions

## AMI versus EC2 instance

```text
AMI          → Template
EC2 instance → Running virtual machine created from the template
```

---

## IAM role versus security group

```text
IAM role      → Permissions to call AWS services
Security group → Allowed network traffic
```

Giving an EC2 instance S3 permission does not open a network port. Opening port 443 does not grant permission to read S3.

---

## User data versus custom AMI

```text
Custom AMI → Prebuilt operating system and software configuration
User data  → Script that customises the instance during launch
```

---

## EBS versus Instance Store

```text
EBS            → Persistent block storage
Instance Store → Temporary storage tied to the host
```

---

## Stop versus terminate

```text
Stop      → Can be started again
Terminate → Permanently removed
```

---

## On-Demand versus Reserved versus Spot

```text
Unpredictable → On-Demand
Predictable   → Reserved
Interruptible → Spot
Licensing     → Dedicated Host
```

---

## ECS versus EKS versus ECR versus Fargate

```text
ECS     → AWS-native orchestration
EKS     → Kubernetes orchestration
ECR     → Container-image storage
Fargate → Compute without server management
```

ECR does not run containers. Apparently a warehouse and a delivery vehicle are still different things.

---

## Lambda versus Elastic Beanstalk

```text
Small event-driven function → Lambda
Conventional web application → Elastic Beanstalk
```

Lambda runs when triggered. Beanstalk deploys a continuously available application environment.

---

# 5. Rapid revision sheet

```text
AMAZON EC2

- Virtual machines
- Full guest-OS control
- Launched from AMIs
- Instance type determines resources
- Security group controls traffic
- IAM role grants service permissions
- User data runs launch scripts
- Key pair supports secure login
```

```text
EC2 LIFECYCLE

Reboot    → Restart
Stop      → Shut down and retain EBS-backed instance
Start     → Return stopped instance to running
Terminate → Permanently remove
```

```text
EC2 PRICING

On-Demand     → Flexible
Reserved      → Predictable long-term
Spot          → Flexible and interruptible
Dedicated Host → Licensing and compliance
```

```text
COST OPTIMISATION

1. Right-size
2. Increase elasticity
3. Choose the correct pricing model
4. Optimise storage
```

```text
CONTAINERS

Docker  → Package and run
ECS     → AWS orchestration
EKS     → Kubernetes
ECR     → Store images
Fargate → Run without managing servers
```

```text
AWS LAMBDA

- Serverless functions
- Event-driven
- Execution role
- Automatic scaling
- Built-in fault tolerance
- Maximum runtime: 15 minutes
- Maximum memory in module: 10,240 MB
```

```text
ELASTIC BEANSTALK

- Deploy web applications
- Upload application code
- AWS provisions infrastructure
- Load balancing
- Automatic scaling
- Health monitoring
- Pay for underlying resources
```

[1]: https://docs.aws.amazon.com/aws-certification/latest/cloud-practitioner-02/cloud-practitioner-02.html?utm_source=chatgpt.com "AWS Certified Cloud Practitioner (CLF-C02) - AWS Certified Cloud Practitioner"

---

</details>

<details>
<summary><strong>Module 7: Storage — AWS-Style Objective Test Preparation</strong></summary>

# Module 7: Storage — AWS-Style Objective Test Preparation

The current AWS Certified Cloud Practitioner exam uses:

* **Multiple choice:** one correct response and three plausible distractors.
* **Multiple response:** two or more correct responses from at least five options.

AWS describes distractors as believable options that someone with incomplete knowledge might select. Questions therefore usually ask for the service that **best** satisfies a scenario, not every service that could theoretically be forced into working. ([AWS Documentation][1])

This test stays within the uploaded Module 7 objectives: storage types, Amazon EBS, Amazon S3, Amazon EFS, Amazon S3 Glacier and choosing between them. 

---

# 1. What to know before attempting the test

## Storage-type comparison

| Storage type                | How data is organised                            | AWS service       |
| --------------------------- | ------------------------------------------------ | ----------------- |
| **Block storage**           | Data divided into blocks; behaves like a disk    | Amazon EBS        |
| **Object storage**          | Complete objects stored with keys and metadata   | Amazon S3         |
| **File storage**            | Files and folders accessed through a file system | Amazon EFS        |
| **Archival object storage** | Rarely accessed long-term objects                | Amazon S3 Glacier |

```text
Need a virtual hard disk?   → EBS
Need scalable objects?      → S3
Need a shared file system?  → EFS
Need long-term archives?    → S3 Glacier
```

The module’s block-versus-object example explains that changing one character in a large file requires updating only the relevant block with block storage, while object storage treats the entire object as one unit. 

## Amazon EBS volume selection

| Requirement                              | EBS volume type          |
| ---------------------------------------- | ------------------------ |
| Most ordinary workloads and boot volumes | General Purpose SSD      |
| Sustained high IOPS and large databases  | Provisioned IOPS SSD     |
| Big data, logs and sequential streaming  | Throughput-Optimised HDD |
| Infrequently accessed, low-cost HDD data | Cold HDD                 |

```text
IOPS       → Number of storage operations
Throughput → Amount of data transferred
```

Throughput-Optimised HDD and Cold HDD cannot be used as boot volumes in the module. 

## Amazon S3 storage-class selection

| Requirement                            | Storage class           |
| -------------------------------------- | ----------------------- |
| Frequently accessed objects            | S3 Standard             |
| Unknown or changing access patterns    | S3 Intelligent-Tiering  |
| Infrequent access but rapid retrieval  | S3 Standard-IA          |
| Infrequent, recreatable data in one AZ | S3 One Zone-IA          |
| Long-term archival                     | S3 Glacier              |
| Lowest-cost deep archival              | S3 Glacier Deep Archive |

The module lists all six of these storage classes. 

## Amazon EFS architecture

```text
EC2 instance A ─┐
EC2 instance B ─┼── Amazon EFS
EC2 instance C ─┘
```

EFS:

* provides shared file storage;
* supports NFS 4.0 and 4.1;
* works with Linux-based EC2 AMIs;
* grows and shrinks automatically;
* uses mount targets in VPC subnets;
* normally has one mount target per Availability Zone.

## Glacier retrieval choices

| Retrieval option | Time stated in module |
| ---------------- | --------------------: |
| Expedited        |           1–5 minutes |
| Standard         |             3–5 hours |
| Bulk             |            5–12 hours |

Faster retrieval generally costs more. AWS may provide cheap storage, but it has not made urgency free. 

---

# 2. Module 7 Mock Test

**Questions:** 65
**Suggested time:** 70 minutes
**Instructions:** Choose one answer unless the question says **Select TWO**.

---

## Storage fundamentals

### 1. An application frequently modifies small portions of a large database file. Which storage type is the BEST fit?

A. Object storage
B. Block storage
C. Archival storage
D. Content-delivery storage

---

### 2. Which storage type organises data as complete units containing data, metadata and a unique key?

A. Block storage
B. File storage
C. Object storage
D. Instance memory

---

### 3. Which storage type provides familiar directories and file names that applications can mount over a network?

A. File storage
B. Object storage
C. Block storage only
D. Archival storage

---

### 4. A company needs a persistent boot disk for an EC2 instance. Which service should it use?

A. Amazon S3
B. Amazon EBS
C. Amazon EFS
D. Amazon S3 Glacier

---

### 5. Several Linux EC2 instances must access the same directory and files simultaneously. Which service should be used?

A. Separate EBS boot volumes
B. Amazon S3 Glacier
C. Amazon EFS
D. EC2 Instance Store

---

### 6. A company must retain regulatory files for ten years and expects almost no retrieval. Which service is the BEST fit?

A. Amazon EBS
B. Amazon EFS
C. Amazon S3 Glacier
D. EC2 Instance Store

---

## Amazon EBS

### 7. What type of storage does Amazon EBS provide?

A. Object storage
B. Block storage
C. Shared NFS storage
D. DNS storage

---

### 8. Which resource commonly uses an EBS volume?

A. Amazon EC2 instance
B. CloudFront edge location
C. Route 53 hosted zone
D. IAM group

---

### 9. How does AWS protect an EBS volume against individual component failure?

A. It automatically stores the volume in every AWS Region
B. It replicates the volume within its Availability Zone
C. It copies the volume to every EC2 instance
D. It converts the volume to an S3 bucket

---

### 10. What happens to EBS data when an attached EC2 instance is stopped?

A. The data is always deleted
B. The data persists independently of the instance
C. The volume becomes an S3 object
D. The data is moved automatically to Glacier

---

### 11. An EBS volume is created in Availability Zone A. To which EC2 instance can it normally be directly attached?

A. An instance in any Region
B. An instance in Availability Zone A
C. An instance at any edge location
D. Only an instance in Availability Zone B

---

### 12. A company wants to recreate an EBS volume in another Availability Zone. Which process should it use?

A. Create a snapshot and create a new volume from it
B. Attach the volume directly across Availability Zones
C. Convert the volume to an IAM role
D. Move the entire Availability Zone

---

### 13. What is an EBS snapshot?

A. A continuously running EC2 instance
B. A point-in-time backup of an EBS volume
C. A shared file system
D. A route-table entry

---

### 14. How can a company use an EBS snapshot?

A. Attach the snapshot directly as a network interface
B. Create a new EBS volume from the snapshot
C. Use it as an IAM policy
D. Use it as a CloudFront origin without restoration

---

### 15. Which EBS feature enables a company to increase capacity or change the volume type?

A. Elasticity
B. DNS routing
C. Object versioning
D. VPC peering

---

### 16. Which EBS volume type is recommended for most ordinary workloads?

A. Cold HDD
B. General Purpose SSD
C. Throughput-Optimised HDD
D. Provisioned IOPS SSD exclusively

---

### 17. A critical production database requires sustained high numbers of input/output operations. Which EBS type is the BEST fit?

A. Cold HDD
B. Throughput-Optimised HDD
C. Provisioned IOPS SSD
D. S3 Standard-IA

---

### 18. A big-data application reads large log files sequentially and requires consistent throughput at low cost. Which volume type should it use?

A. General Purpose SSD
B. Provisioned IOPS SSD
C. Throughput-Optimised HDD
D. Cold HDD only

---

### 19. A company stores a large volume of infrequently accessed data and prioritises the lowest EBS storage cost. Which type should it use?

A. Provisioned IOPS SSD
B. General Purpose SSD
C. Cold HDD
D. S3 Standard

---

### 20. Which EBS volume types cannot be used as boot volumes according to the module? **Select TWO.**

A. General Purpose SSD
B. Provisioned IOPS SSD
C. Throughput-Optimised HDD
D. Cold HDD
E. All SSD volumes

---

### 21. Which metric measures the number of storage operations completed each second?

A. Throughput
B. IOPS
C. Latency zone
D. Durability

---

### 22. Which metric measures the quantity of data transferred during a period?

A. Throughput
B. IOPS
C. Availability
D. Object count

---

### 23. Which workload is more dependent on high IOPS than sequential throughput?

A. A transactional database performing many small reads and writes
B. Reading one large archive file sequentially
C. Transferring a long video stream
D. Processing one large log file from beginning to end

---

### 24. How are EBS volumes generally charged according to the module?

A. Only for data that applications read
B. According to provisioned capacity
C. According to the number of IAM users
D. Only when the attached EC2 instance is running

---

### 25. A company provisions a 500-GB EBS volume but stores only 100 GB. Which capacity is generally relevant for volume charges?

A. 100 GB only
B. 500 GB provisioned
C. No storage charges apply
D. The EC2 instance’s memory size

---

### 26. Which EBS items can create additional charges? **Select TWO.**

A. Stored EBS snapshots
B. Provisioned IOPS
C. IAM group membership
D. Security-group rules
E. EC2 tags

---

### 27. Which statement about EBS data transfer is correct according to the module?

A. Inbound transfer is charged at the highest rate
B. Inbound transfer is free, while outbound cross-Region transfer can incur charges
C. All data transfer is always free
D. Cross-Region transfer is impossible

---

### 28. Which statement about EBS encryption is correct according to the module?

A. Encryption is unavailable for EBS volumes
B. Encryption is supported without an additional encryption charge
C. Encryption requires converting EBS to EFS
D. Encryption works only on HDD volumes

---

## Amazon S3

### 29. What type of storage does Amazon S3 provide?

A. Block storage
B. Object storage
C. RAM storage
D. NFS file storage

---

### 30. How does Amazon S3 organise stored data?

A. Objects are stored inside buckets
B. Blocks are attached to IAM users
C. Files are stored only in mounted Linux directories
D. Volumes are attached to Availability Zones

---

### 31. What identifies an object within an S3 bucket?

A. An object key
B. An EC2 key pair
C. A security-group ID
D. A route-table target

---

### 32. What is the maximum size of one S3 object stated in the module?

A. 5 GB
B. 500 GB
C. 5 TB
D. Unlimited

---

### 33. Which statement BEST describes S3 storage capacity?

A. Each bucket must have a fixed capacity selected in advance
B. S3 can store a virtually unlimited number of objects
C. S3 is limited to one object per Availability Zone
D. S3 capacity equals the attached EC2 instance’s disk size

---

### 34. Amazon S3 is designed for how many nines of object durability?

A. Two nines
B. Four nines
C. Nine nines
D. Eleven nines

---

### 35. What does durability describe?

A. How quickly an object can be downloaded
B. The likelihood that stored data will not be lost
C. How many requests an IAM user can send
D. The number of hours a bucket remains public

---

### 36. Which statement correctly distinguishes durability from availability?

A. Durability concerns data survival; availability concerns whether data can currently be accessed
B. Durability concerns speed; availability concerns cost
C. They are identical terms
D. Availability concerns encryption only

---

### 37. Where is S3 data redundantly stored in the module’s architecture?

A. In several facilities within the selected Region
B. On only one EC2 instance
C. At every CloudFront edge location automatically
D. In every AWS Region automatically

---

### 38. When creating an S3 bucket, what location choice does the customer make?

A. An AWS Region
B. A physical server rack
C. A specific CloudFront edge server
D. An IAM group

---

### 39. Which statement about S3 access is correct?

A. Objects can be accessed only from the EC2 console
B. S3 objects can be accessed through URLs, APIs, the CLI and SDKs
C. An object must be mounted through NFS
D. S3 requires a Dedicated Host

---

### 40. Which workload is the BEST fit for Amazon S3?

A. A database boot disk requiring block-level updates
B. Millions of uploaded photos and videos
C. A mounted shared Linux home directory
D. Temporary processor cache

---

### 41. Which storage class is intended for frequently accessed objects?

A. S3 Standard
B. S3 Glacier Deep Archive
C. S3 One Zone-IA
D. S3 Glacier only

---

### 42. A company cannot predict whether its objects will be accessed frequently or rarely. Which storage class is the BEST fit?

A. S3 Intelligent-Tiering
B. S3 One Zone-IA
C. S3 Glacier Deep Archive
D. Amazon EBS Cold HDD

---

### 43. A company accesses backup objects rarely but requires rapid retrieval when needed. Which storage class should it use?

A. S3 Standard-IA
B. S3 Glacier Bulk
C. EBS Provisioned IOPS
D. EC2 Instance Store

---

### 44. A company stores an infrequently accessed secondary copy that can be recreated. It wants a lower cost and accepts storage in one Availability Zone. Which class should it use?

A. S3 Standard
B. S3 One Zone-IA
C. S3 Intelligent-Tiering
D. EFS

---

### 45. Which S3 classes are intended primarily for archival data? **Select TWO.**

A. S3 Standard
B. S3 Standard-IA
C. S3 Glacier
D. S3 Glacier Deep Archive
E. S3 Intelligent-Tiering

---

### 46. Which factors affect S3 cost? **Select TWO.**

A. Storage class
B. Number and type of requests
C. Number of IAM groups
D. Number of VPC route tables
E. EC2 key-pair type

---

### 47. Which operations can contribute to S3 request charges? **Select TWO.**

A. GET
B. PUT
C. Creating an IAM group
D. Starting an EC2 instance
E. Editing a security group

---

### 48. Which statement about transfer into Amazon S3 is correct according to the module?

A. Data transfer into S3 is free
B. Data transfer into S3 is charged twice
C. S3 cannot accept data from another Region
D. Transfer into S3 requires Glacier retrieval

---

### 49. Which transfer can incur S3 data-transfer charges?

A. Transfer out of the S3 Region
B. Transfer into S3
C. Transfer from S3 to EC2 in the same Region according to the module
D. Transfer from S3 to CloudFront according to the module

---

### 50. A company stores only 20 GB in S3 but performs millions of GET and PUT operations. Which statement is correct?

A. Only storage volume affects the bill
B. Request volume can also affect the bill
C. Requests are always free
D. The company must use EBS instead

---

## Amazon EFS

### 51. What type of storage does Amazon EFS provide?

A. Shared network file storage
B. Object storage
C. Archival object storage
D. EC2 instance memory

---

### 52. Which protocol does EFS support according to the module?

A. DNS
B. NFS 4.0 and 4.1
C. SMTP
D. BGP only

---

### 53. Which operating systems are primarily compatible with EFS in the module?

A. Linux-based EC2 AMIs
B. Only mobile operating systems
C. Only mainframe operating systems
D. No EC2 operating systems

---

### 54. A web application runs on several Linux EC2 instances. Every instance must read and write the same uploaded files. Which service is the BEST fit?

A. An independent EBS volume for every instance
B. Amazon EFS
C. Amazon S3 Glacier
D. EC2 Instance Store

---

### 55. What is an EFS mount target?

A. A network access point for the EFS file system in a subnet
B. A separate copy of the entire file system
C. An S3 lifecycle policy
D. An EC2 pricing model

---

### 56. Where is an EFS mount target created?

A. In a VPC subnet
B. At an edge location
C. Inside an IAM group
D. In an S3 bucket

---

### 57. Which statements about EFS mount targets are correct? **Select TWO.**

A. They must be in the same VPC as the file system’s clients
B. One is normally created per Availability Zone
C. Every mount target creates an independent file system
D. They can exist only outside a VPC
E. They replace EC2 network interfaces

---

### 58. Which control can be associated with an EFS mount target to regulate network access?

A. Security group
B. S3 object key
C. IAM password policy only
D. CloudFront cache behaviour

---

### 59. How does EFS handle storage capacity?

A. Capacity must be permanently provisioned in advance
B. It grows and shrinks as files are added and removed
C. Capacity is fixed to the EC2 instance’s memory
D. It stores only one file per mount target

---

### 60. Which are suitable EFS use cases? **Select TWO.**

A. Shared Linux home directories
B. Media-processing workflows
C. Long-term records that are never retrieved
D. EC2 boot volumes
E. Route 53 DNS records

---

## Amazon S3 Glacier and service selection

### 61. What is the primary purpose of Amazon S3 Glacier?

A. Frequently updated database blocks
B. Low-cost long-term data archiving
C. Shared Linux file storage
D. EC2 boot volumes

---

### 62. Which Glacier feature can enforce a compliance policy on archived data?

A. Vault Lock
B. Elastic IP
C. Auto Scaling
D. Route 53 health check

---

### 63. A company needs an archived file within approximately 1–5 minutes. Which Glacier retrieval option should it choose?

A. Bulk
B. Standard
C. Expedited
D. One Zone-IA

---

### 64. A company can wait approximately 3–5 hours for archived data. Which retrieval option should it use?

A. Expedited
B. Standard
C. Bulk
D. Intelligent-Tiering

---

### 65. A company needs to retrieve a large archive at the lowest retrieval cost and can wait approximately 5–12 hours. Which option should it choose?

A. Expedited
B. Standard
C. Bulk
D. General Purpose SSD

---

# Stop before checking the answers

<details>
<summary><strong>Open answer key and explanations</strong></summary>

## Questions 1–6: Storage fundamentals

|  Q | Answer | Explanation                                                                        |
| -: | :----: | ---------------------------------------------------------------------------------- |
|  1 |  **B** | Block storage can modify the affected block instead of replacing the whole object. |
|  2 |  **C** | Object storage treats data as complete objects with keys and metadata.             |
|  3 |  **A** | File storage provides files and directory structures over a file-system protocol.  |
|  4 |  **B** | EBS provides persistent block storage for EC2 boot volumes.                        |
|  5 |  **C** | EFS provides shared file storage for multiple Linux EC2 instances.                 |
|  6 |  **C** | Glacier is designed for low-cost, long-term archiving.                             |

---

## Questions 7–28: Amazon EBS

|  Q |  Answer  | Explanation                                                                          |
| -: | :------: | ------------------------------------------------------------------------------------ |
|  7 |   **B**  | EBS is block-level storage.                                                          |
|  8 |   **A**  | EBS volumes are normally attached to EC2 instances.                                  |
|  9 |   **B**  | EBS volumes are replicated inside their Availability Zone.                           |
| 10 |   **B**  | EBS persists independently from the instance.                                        |
| 11 |   **B**  | The volume and EC2 instance must normally be in the same AZ.                         |
| 12 |   **A**  | A snapshot can be used to create a new volume in another AZ.                         |
| 13 |   **B**  | A snapshot is a point-in-time backup.                                                |
| 14 |   **B**  | Snapshots are used to create restored EBS volumes.                                   |
| 15 |   **A**  | EBS elasticity supports increasing capacity and changing types.                      |
| 16 |   **B**  | General Purpose SSD is recommended for most workloads.                               |
| 17 |   **C**  | Provisioned IOPS SSD is intended for sustained high-performance workloads.           |
| 18 |   **C**  | Throughput-Optimised HDD suits large sequential workloads such as logs and big data. |
| 19 |   **C**  | Cold HDD prioritises low cost for infrequently accessed EBS data.                    |
| 20 | **C, D** | The module states that the HDD types cannot be boot volumes.                         |
| 21 |   **B**  | IOPS counts storage operations per second.                                           |
| 22 |   **A**  | Throughput measures data transferred over time.                                      |
| 23 |   **A**  | Transactional databases often perform many small independent operations.             |
| 24 |   **B**  | EBS volume charges are generally based on provisioned capacity.                      |
| 25 |   **B**  | Provisioning 500 GB generally means paying for 500 GB.                               |
| 26 | **A, B** | Snapshots and provisioned IOPS can add costs.                                        |
| 27 |   **B**  | Inbound transfer is free; outbound cross-Region transfer can be charged.             |
| 28 |   **B**  | The module states that encrypted EBS volumes do not add an encryption fee.           |

Amazon EBS provides AZ-based block storage, snapshots, encryption and adjustable capacity.

---

## Questions 29–50: Amazon S3

|  Q |  Answer  | Explanation                                                          |
| -: | :------: | -------------------------------------------------------------------- |
| 29 |   **B**  | S3 is object storage.                                                |
| 30 |   **A**  | S3 stores objects in buckets.                                        |
| 31 |   **A**  | The object key identifies the object in the bucket.                  |
| 32 |   **C**  | The module states a maximum of 5 TB per S3 object.                   |
| 33 |   **B**  | S3 supports a virtually unlimited number of objects.                 |
| 34 |   **D**  | S3 is designed for eleven nines of durability.                       |
| 35 |   **B**  | Durability concerns protection from data loss.                       |
| 36 |   **A**  | Availability concerns current access; durability concerns survival.  |
| 37 |   **A**  | S3 redundantly stores data within the selected Region.               |
| 38 |   **A**  | Customers select the bucket’s AWS Region.                            |
| 39 |   **B**  | S3 can be used through URLs, APIs, the CLI and SDKs.                 |
| 40 |   **B**  | Photos and videos are a typical object-storage workload.             |
| 41 |   **A**  | S3 Standard is intended for frequent access.                         |
| 42 |   **A**  | Intelligent-Tiering suits unknown or changing access patterns.       |
| 43 |   **A**  | Standard-IA provides lower-cost storage with rapid retrieval.        |
| 44 |   **B**  | One Zone-IA is suitable for recreatable, infrequently accessed data. |
| 45 | **C, D** | Glacier and Glacier Deep Archive are archival classes.               |
| 46 | **A, B** | Storage class and request activity affect S3 cost.                   |
| 47 | **A, B** | GET and PUT are among the billable request types.                    |
| 48 |   **A**  | The module states that data transfer into S3 is free.                |
| 49 |   **A**  | Transfer out of the S3 Region can incur charges.                     |
| 50 |   **B**  | S3 pricing includes requests, not merely stored gigabytes.           |

The module describes S3 as fully managed object storage with virtually unlimited object capacity, regional redundancy, several storage classes and pricing based on storage, requests and transfer.

---

## Questions 51–60: Amazon EFS

|  Q |  Answer  | Explanation                                                            |
| -: | :------: | ---------------------------------------------------------------------- |
| 51 |   **A**  | EFS is shared network file storage.                                    |
| 52 |   **B**  | The module lists NFS versions 4.0 and 4.1.                             |
| 53 |   **A**  | EFS is compatible with Linux-based EC2 AMIs.                           |
| 54 |   **B**  | EFS allows multiple instances to mount the same shared files.          |
| 55 |   **A**  | A mount target provides network access to the EFS file system.         |
| 56 |   **A**  | Mount targets are created in VPC subnets.                              |
| 57 | **A, B** | Mount targets must be in the same VPC and are normally created per AZ. |
| 58 |   **A**  | Security groups regulate mount-target network access.                  |
| 59 |   **B**  | EFS automatically expands and contracts with stored files.             |
| 60 | **A, B** | Shared directories and media processing are common EFS workloads.      |

---

## Questions 61–65: Amazon S3 Glacier

|  Q | Answer | Explanation                                                                           |
| -: | :----: | ------------------------------------------------------------------------------------- |
| 61 |  **B** | Glacier is low-cost archival storage.                                                 |
| 62 |  **A** | Vault Lock enforces archive compliance policies.                                      |
| 63 |  **C** | Expedited retrieval is listed as approximately 1–5 minutes.                           |
| 64 |  **B** | Standard retrieval is listed as approximately 3–5 hours.                              |
| 65 |  **C** | Bulk retrieval takes approximately 5–12 hours and suits large, non-urgent retrievals. |

</details>

---

# 3. Score interpretation

|        Score | Readiness                                                           |
| -----------: | ------------------------------------------------------------------- |
|    **59–65** | Strongly prepared                                                   |
|    **51–58** | Nearly ready; revise isolated weaknesses                            |
|    **41–50** | Core understanding exists, but similar storage choices remain mixed |
| **Below 41** | Review storage types, S3 classes and EBS volume selection           |

For multiple-response questions, count the answer as correct only when every required choice is selected and no incorrect choice is included. AWS does not award half a mark because one of the two selected services was emotionally appropriate.

---

# 4. The most dangerous exam confusions

## EBS versus S3

```text
EBS → Block storage attached to EC2
S3  → Objects stored in buckets
```

Use EBS for operating systems and databases. Use S3 for complete objects such as images, backups and videos.

---

## EBS versus EFS

```text
EBS → Disk for an EC2 workload
EFS → Shared file system for multiple EC2 instances
```

Creating three independent EBS volumes does not create shared storage. It creates three independent disks, which is impressively unhelpful when every server needs the same file.

---

## S3 Standard-IA versus Glacier

```text
Standard-IA → Rare access, rapid retrieval
Glacier     → Archive, slower retrieval
```

“Infrequently accessed” does not automatically mean Glacier. Retrieval-time requirements matter.

---

## General Purpose SSD versus Provisioned IOPS

```text
General Purpose → Most workloads
Provisioned IOPS → Sustained high-performance databases
```

Do not select Provisioned IOPS merely because “provisioned” sounds responsible and expensive.

---

## IOPS versus throughput

```text
IOPS       → How many operations?
Throughput → How much data?
```

Many small database requests require IOPS. Large sequential streams require throughput.

---

## Snapshot versus volume

```text
EBS volume   → Active storage used by EC2
EBS snapshot → Point-in-time backup
```

An instance uses a volume, not a photograph of the volume pretending to be a disk.

---

## Mount target versus EFS file system

```text
EFS file system → The shared stored data
Mount target    → Network entrance to that file system
```

Multiple mount targets do not mean multiple copies of the file system.

---

# 5. Rapid revision sheet

```text
STORAGE TYPES

Block  → EBS
Object → S3
File   → EFS
Archive → S3 Glacier
```

```text
AMAZON EBS

- Persistent block storage
- Attached to EC2
- Availability Zone-based
- Replicated within the AZ
- Snapshots are point-in-time backups
- Supports encryption
- Capacity and type can be changed
```

```text
EBS TYPES

General Purpose SSD
→ Most workloads and boot volumes

Provisioned IOPS SSD
→ Critical databases and sustained IOPS

Throughput-Optimised HDD
→ Logs, big data and sequential workloads

Cold HDD
→ Rarely accessed, lowest-cost HDD data
```

```text
AMAZON S3

- Object storage
- Buckets and objects
- Maximum object size in module: 5 TB
- Virtually unlimited objects
- Eleven nines durability
- Regional redundancy
- Storage, requests and transfer affect cost
```

```text
S3 CLASSES

Standard            → Frequent access
Intelligent-Tiering → Uncertain access
Standard-IA         → Rare but rapid access
One Zone-IA         → Re-creatable one-AZ data
Glacier             → Archive
Deep Archive        → Deep long-term archive
```

```text
AMAZON EFS

- Shared network file system
- NFS 4.0 and 4.1
- Linux EC2 workloads
- Mount targets in VPC subnets
- One mount target per AZ
- Automatically scales
- Pay for used storage
```

```text
S3 GLACIER

- Low-cost archive
- Eleven nines durability
- Vault Lock for compliance
- Expedited: 1–5 minutes
- Standard: 3–5 hours
- Bulk: 5–12 hours
- Lifecycle rules can archive S3 objects
```

[1]: https://docs.aws.amazon.com/aws-certification/latest/cloud-practitioner-02/cloud-practitioner-02.html?utm_source=chatgpt.com "AWS Certified Cloud Practitioner (CLF-C02) - AWS Certified Cloud Practitioner"

---

</details>

<details>
<summary><strong>Module 8: Databases — AWS-Style Objective Test Preparation</strong></summary>

# Module 8: Databases — AWS-Style Objective Test Preparation

The AWS Certified Cloud Practitioner exam currently uses:

* **Multiple choice:** one correct response and three distractors.
* **Multiple response:** two or more correct responses from at least five options.

AWS’s official practice sets are designed to demonstrate the wording and style of certification questions. The questions below are original, but they use the same scenario-based approach: identify the service that **BEST** meets the stated requirement. ([AWS Documentation][1])

Cloud Practitioner questions focus on recognising services and use cases rather than performing detailed database implementation or troubleshooting. Conveniently, nobody needs to memorise which console button sits three pixels to the left this week. ([AWS Documentation][2])

This test follows the Module 8 objectives:

* Explain Amazon RDS and its functionality.
* Explain Amazon DynamoDB and its functionality.
* Explain Amazon Redshift.
* Explain Amazon Aurora.
* Recognise appropriate database choices for different workloads. 

---

# 1. What to know before attempting the test

## Main database-selection map

| Requirement                                                      | Best starting service  |
| ---------------------------------------------------------------- | ---------------------- |
| Managed relational database                                      | Amazon RDS             |
| High-performance MySQL/PostgreSQL-compatible relational database | Amazon Aurora          |
| Fast, scalable NoSQL key-value or document database              | Amazon DynamoDB        |
| Large-scale historical analytics and data warehousing            | Amazon Redshift        |
| Full operating-system and database-level control                 | Database on Amazon EC2 |

```text
Transactions and relationships → RDS or Aurora
Simple key-based access        → DynamoDB
Historical analytics           → Redshift
Full OS control                → Database on EC2
```

The module’s final decision table recommends RDS for enterprise relational databases, DynamoDB for fast and flexible NoSQL workloads, EC2 when operating-system access is required, and purpose-built services for specialised requirements such as data warehousing. 

---

## RDS: the crucial distinction

```text
Multi-AZ deployment → High availability
Read replica        → Read scalability
```

| Multi-AZ                       | Read replica                |
| ------------------------------ | --------------------------- |
| Primary and standby            | Primary and readable copy   |
| Synchronous replication        | Asynchronous replication    |
| Automatic failover             | Offloads read traffic       |
| Standby is mainly for recovery | Replica serves read queries |
| Availability                   | Performance and scaling     |

The diagrams on pages 13–15 show synchronous replication to a standby in another Availability Zone and asynchronous replication to a read replica. 

---

## DynamoDB essentials

```text
Table
└── Item
    ├── Attribute
    ├── Attribute
    └── Attribute
```

* NoSQL database.
* Supports key-value and document models.
* Items can contain different attributes.
* Uses partition keys and optional sort keys.
* Designed for low-latency access and scalable throughput.
* Suitable for web, mobile, gaming, advertising and IoT workloads.

---

## Redshift essentials

```text
SQL or BI client
       ↓
Leader node
       ↓
Compute nodes working in parallel
```

Amazon Redshift is a managed data warehouse that uses:

* columnar storage;
* parallel processing;
* compute nodes;
* SQL and business-intelligence tools.

It is intended for analytics, not ordinary checkout transactions.

---

## Aurora essentials

Amazon Aurora is:

* an enterprise relational database;
* compatible with MySQL or PostgreSQL;
* managed through Amazon RDS;
* designed for high performance and availability;
* able to automate provisioning, patching, backup, recovery, failure detection and repair. 

---

# 2. Module 8 Mock Test

**Questions:** 70
**Suggested time:** 75 minutes
**Instructions:** Select one answer unless the question says **Select TWO**.

---

## Database fundamentals and service selection

### 1. Which characteristic is commonly associated with a relational database?

A. Data is stored only as unstructured objects
B. Data is organised into related tables
C. Every record must be retrieved using an object URL
D. Data cannot be queried

---

### 2. Which database type is generally most suitable when relationships, structured schemas and complex transactions are important?

A. Relational database
B. Key-value cache only
C. Content delivery network
D. Object-storage bucket

---

### 3. A company stores customers, orders, payments and invoices. The records have clear relationships and require transactional consistency. Which AWS service is the BEST starting choice?

A. Amazon CloudFront
B. Amazon RDS
C. Amazon S3 Glacier
D. Amazon Route 53

---

### 4. A mobile game retrieves player records by PlayerID and must scale rapidly to millions of users. Which database is the BEST fit?

A. Amazon Redshift
B. Amazon DynamoDB
C. Amazon EFS
D. Amazon RDS Multi-AZ standby only

---

### 5. A company wants to analyse ten years of sales data using business-intelligence dashboards. Which service should it use?

A. Amazon Redshift
B. Amazon DynamoDB
C. Amazon EC2 Instance Store
D. Amazon Cognito

---

### 6. A company requires direct operating-system access and unsupported custom database extensions. Which deployment should it use?

A. Amazon DynamoDB
B. Amazon Redshift
C. A database running on Amazon EC2
D. Amazon RDS Multi-AZ

---

### 7. Which database services are relational? **Select TWO.**

A. Amazon RDS
B. Amazon DynamoDB
C. Amazon Aurora
D. Amazon CloudFront
E. Amazon EFS

---

### 8. Which service is a NoSQL database?

A. Amazon Aurora
B. Amazon DynamoDB
C. Amazon Redshift
D. Amazon RDS for Oracle

---

## Amazon RDS: managed service and architecture

### 9. What is Amazon RDS?

A. A managed relational database service
B. A container-orchestration service
C. An object-storage service
D. A content delivery network

---

### 10. Which task is generally managed by AWS when a customer uses Amazon RDS?

A. Designing the application’s database schema
B. Optimising every customer SQL query
C. Installing and patching the database software
D. Deciding which data the application stores

---

### 11. Which task remains primarily the customer’s responsibility when using Amazon RDS?

A. Maintaining physical data-centre power
B. Replacing failed physical disks
C. Application and query optimisation
D. Installing the host operating system

---

### 12. Which responsibilities are generally handled by AWS for Amazon RDS? **Select TWO.**

A. Operating-system patching
B. Application code design
C. Database software patching
D. Choosing the customer’s table relationships
E. Writing customer SQL queries

---

### 13. Which database engines are supported by Amazon RDS in the module? **Select TWO.**

A. MySQL
B. PostgreSQL
C. Amazon S3
D. Amazon CloudFront
E. Amazon EFS

---

### 14. Which database engine is also listed as an Amazon RDS option?

A. Amazon Aurora
B. Amazon Route 53
C. AWS Lambda
D. Amazon CloudFront

---

### 15. Which components define an RDS DB instance? **Select TWO.**

A. DB instance class
B. Database engine
C. CloudFront edge location
D. IAM group membership
E. Route 53 routing policy

---

### 16. What does an RDS DB instance class primarily determine?

A. CPU, memory and network capacity
B. The database schema
C. The number of IAM users
D. The customer's AWS Support plan

---

### 17. Which storage choices are shown for an RDS DB instance in the module? **Select TWO.**

A. General Purpose SSD
B. Provisioned IOPS
C. CloudFront cache
D. Glacier vault
E. Route 53 hosted zone

---

### 18. An application server is publicly accessible, but its database should not accept connections directly from the internet. Where should the RDS database normally be placed?

A. In a private subnet
B. At a CloudFront edge location
C. In a public S3 bucket
D. Outside the VPC

---

### 19. In the architecture shown on page 12, how do users normally access the RDS database?

A. Users connect directly to the database through the internet gateway
B. Users communicate with an application server, which accesses RDS
C. Users retrieve the database through CloudFront
D. Users assume the database’s IAM role

---

### 20. Why is an RDS database commonly placed in a private subnet?

A. To make it easier for every internet user to access
B. To reduce direct exposure to the public internet
C. To turn the relational database into NoSQL
D. To create a CloudFront cache

---

### 21. A company wants a managed relational database but already uses Microsoft SQL Server. Which service can meet the requirement?

A. Amazon RDS
B. Amazon DynamoDB
C. Amazon Redshift only
D. Amazon S3

---

### 22. A company runs MySQL on EC2. Which responsibility does the company have that would normally be managed by AWS under RDS?

A. Database software installation and patching
B. AWS data-centre power
C. Physical rack installation
D. AWS network backbone maintenance

---

### 23. Which statement correctly compares a database on EC2 with Amazon RDS?

A. EC2 provides more database-management automation than RDS
B. RDS generally reduces operating-system and database-maintenance work
C. RDS gives the customer unrestricted host operating-system access
D. Databases on EC2 cannot use relational engines

---

### 24. A company must customise the operating system beneath its database. Why might it choose EC2 instead of RDS?

A. EC2 provides greater host-level control
B. EC2 automatically manages all backups and failover
C. EC2 is a NoSQL service
D. RDS cannot store data

---

## RDS Multi-AZ and read replicas

### 25. What is the primary purpose of an RDS Multi-AZ deployment?

A. Reduce DNS latency
B. Improve database high availability
C. Store container images
D. Analyse historical data

---

### 26. How is data replicated from the primary RDS instance to the Multi-AZ standby in the module?

A. Asynchronously
B. Synchronously
C. Through CloudFront
D. Through an S3 lifecycle rule

---

### 27. Where is the RDS Multi-AZ standby located?

A. On the same physical disk as the primary
B. In another Availability Zone
C. At an edge location
D. In every AWS Region

---

### 28. What occurs if the primary instance in an RDS Multi-AZ deployment fails?

A. AWS can fail over to the standby
B. The standby is deleted
C. All read replicas become S3 buckets
D. The application must permanently stop

---

### 29. Which statement about an RDS Multi-AZ standby is correct?

A. Its main purpose is to serve normal analytical queries
B. Its main purpose is failover and availability
C. It replaces Amazon Redshift
D. It is always deployed in the same Availability Zone

---

### 30. What is the main purpose of an RDS read replica?

A. Offload read queries from the primary database
B. Protect physical AWS data centres
C. Replace the database schema
D. Process CloudFront requests

---

### 31. How is data replicated to an RDS read replica in the module?

A. Synchronously
B. Asynchronously
C. Through an internet gateway
D. Through a network ACL

---

### 32. What is a possible result of asynchronous replication to a read replica?

A. The replica can temporarily lag behind the primary
B. The primary becomes an S3 object
C. The replica cannot process reads
D. The replica must always be in the same physical server

---

### 33. Which statements correctly compare Multi-AZ and read replicas? **Select TWO.**

A. Multi-AZ primarily supports availability
B. Read replicas primarily support read scaling
C. Multi-AZ uses asynchronous replication in the module
D. Read replicas cannot serve queries
E. Multi-AZ standby is mainly an analytics warehouse

---

### 34. An application performs significantly more reads than writes. Which RDS feature should be considered?

A. Read replicas
B. Multi-AZ standby only
C. S3 Glacier
D. Dedicated Host

---

### 35. A database must continue operating if one Availability Zone fails. Which RDS feature is the BEST fit?

A. Read replica only
B. Multi-AZ deployment
C. DynamoDB Scan
D. Redshift leader node

---

### 36. Which RDS resource can be promoted to become a primary database if necessary?

A. Read replica
B. Security group
C. DB subnet group
D. Internet gateway

---

## RDS suitability and pricing

### 37. Which workload is most suitable for Amazon RDS?

A. Complex relational transactions and SQL queries
B. Billions of simple key-value operations with no relational requirements
C. Delivering cached video files
D. Resolving domain names

---

### 38. Which requirement indicates that DynamoDB may be more appropriate than RDS?

A. Complex table joins
B. Simple GET and PUT requests at massive scale
C. Traditional relational transactions
D. Oracle compatibility

---

### 39. Which requirement may justify running a database on EC2 instead of RDS?

A. RDBMS customisation and host operating-system access
B. Automatic database patching
C. Reduced administration
D. No need for server control

---

### 40. Which factors can affect Amazon RDS cost? **Select TWO.**

A. DB instance class
B. Database storage
C. Number of CloudFront edge locations
D. Number of IAM groups
E. Route 53 domain name length

---

### 41. Which RDS purchasing option provides flexibility without a long-term commitment?

A. On-Demand DB instance
B. Reserved DB instance only
C. Spot database
D. CloudFront reservation

---

### 42. A company expects to run the same RDS database continuously for three years. Which purchasing option might reduce cost in exchange for commitment?

A. Reserved DB instance
B. Spot Instance
C. Glacier Deep Archive
D. S3 Intelligent-Tiering

---

### 43. Which deployment generally costs more because additional database infrastructure is maintained?

A. Multi-AZ
B. Single-AZ
C. DynamoDB table without items
D. An IAM group

---

### 44. Which statement about RDS data transfer is stated in the module?

A. Inbound data transfer has no charge, while outbound transfer can be charged
B. Every inbound request is charged twice
C. All outbound data transfer is always free
D. RDS cannot receive data from outside AWS

---

## Amazon DynamoDB

### 45. What is Amazon DynamoDB?

A. A managed NoSQL database service
B. A managed relational data warehouse
C. A network file system
D. A virtual machine

---

### 46. Which data models does DynamoDB support? **Select TWO.**

A. Key-value
B. Document
C. Block-storage volume
D. DNS zone
E. Shared NFS file system

---

### 47. Which terms describe the basic DynamoDB data structure? **Select TWO.**

A. Items
B. Attributes
C. EC2 volumes
D. Availability Zones
E. Edge caches

---

### 48. Which statement about DynamoDB items is correct?

A. Every item must contain exactly the same attributes
B. Items in the same table can contain different attributes
C. An item must be a relational join
D. Every item is stored as an EBS snapshot

---

### 49. What is the purpose of a DynamoDB partition key?

A. Help identify and distribute items
B. Encrypt an EC2 operating system
C. Select a CloudFront edge location
D. Create an RDS standby

---

### 50. A DynamoDB table uses `CustomerID` as the partition key and `OrderDate` as the sort key. What does this allow?

A. Multiple orders for one customer can be distinguished by date
B. Every customer can have only one order
C. The table becomes an RDS database
D. DynamoDB stops using partitions

---

### 51. Which DynamoDB operation is generally more efficient when the required key value is known?

A. Query
B. Scan
C. Full table export for every request
D. Multi-AZ failover

---

### 52. What does a DynamoDB Scan generally do?

A. Examines many or all table items
B. Creates an Aurora replica
C. Reads only one known partition key automatically
D. Converts NoSQL into SQL

---

### 53. Why is partition-key design important in DynamoDB?

A. It helps distribute data and requests across partitions
B. It determines the CloudFront origin
C. It installs the database operating system
D. It defines an RDS backup window

---

### 54. Which partition key would generally distribute requests more effectively?

A. A unique UserID with many possible values
B. A field containing only `Yes` or `No`
C. A field where every item has the value `Malaysia`
D. A field containing one constant value

---

### 55. Which workloads are good DynamoDB use cases? **Select TWO.**

A. Online game player state
B. Web-application user sessions
C. Large historical SQL warehouse queries
D. EC2 boot volumes
E. Shared Linux directories

---

### 56. Which feature is associated with DynamoDB in the module?

A. Consistent single-digit millisecond latency
B. Host operating-system access
C. Traditional block-storage attachment
D. Columnar data-warehouse storage

---

### 57. Which statement correctly compares DynamoDB and RDS?

A. DynamoDB is relational, while RDS is NoSQL
B. DynamoDB suits simple high-scale key access, while RDS suits relational queries and transactions
C. Both are content delivery networks
D. RDS does not support SQL

---

## Amazon Redshift

### 58. What is Amazon Redshift primarily designed for?

A. Data warehousing and analytics
B. Transactional shopping carts
C. EC2 boot storage
D. User authentication

---

### 59. Which workload is the BEST fit for Amazon Redshift?

A. Recording one customer’s current shopping cart
B. Analysing billions of historical sales records
C. Hosting a Linux operating system
D. Resolving a domain name

---

### 60. What is the purpose of the Redshift leader node?

A. Receive queries, coordinate work and combine results
B. Store IAM passwords
C. Provide DDoS protection
D. Act as an internet gateway

---

### 61. What is the purpose of Redshift compute nodes?

A. Process portions of data in parallel
B. Authenticate mobile users
C. Store container images
D. Patch EC2 operating systems

---

### 62. Which architecture helps Redshift process large analytical queries efficiently?

A. Massively parallel processing
B. One read replica performing all work
C. CloudFront edge caching
D. Single-threaded DNS resolution

---

### 63. What is a major benefit of Redshift columnar storage?

A. Analytical queries can read only the required columns
B. Every row requires a separate EC2 instance
C. It makes Redshift a NoSQL key-value database
D. It removes the need for SQL

---

### 64. Which tools commonly connect to Amazon Redshift?

A. SQL clients and business-intelligence tools
B. EC2 key pairs only
C. Internet gateways
D. EBS boot loaders

---

### 65. Which features are associated with Redshift? **Select TWO.**

A. Columnar storage
B. Parallel processing
C. Application-user authentication
D. EC2 operating-system access
E. DNS registration

---

## Amazon Aurora and final database selection

### 66. What is Amazon Aurora?

A. An AWS-designed enterprise relational database engine
B. A NoSQL document database
C. A content delivery network
D. A block-storage service

---

### 67. With which database engines is Aurora compatible? **Select TWO.**

A. MySQL
B. PostgreSQL
C. Microsoft Access
D. DynamoDB
E. Amazon S3

---

### 68. Through which AWS managed service is Aurora provided?

A. Amazon RDS
B. Amazon CloudFront
C. Amazon ECS
D. AWS Artifact

---

### 69. Which tasks can Aurora automate? **Select TWO.**

A. Database backup and recovery
B. Failure detection and repair
C. Application business-rule design
D. Customer table relationship design
E. Writing every SQL query

---

### 70. A company has an existing MySQL application and needs an enterprise relational database with stronger cloud-based performance and availability. Which service is the BEST fit?

A. Amazon Aurora MySQL-Compatible Edition
B. Amazon DynamoDB
C. Amazon Redshift
D. Amazon EFS

---

# Stop before opening the answers

<details>
<summary><strong>Open answer key and explanations</strong></summary>

## Questions 1–8: Database fundamentals

|  Q |  Answer  | Explanation                                                                   |
| -: | :------: | ----------------------------------------------------------------------------- |
|  1 |   **B**  | Relational databases organise structured data into related tables.            |
|  2 |   **A**  | Relational databases suit relationships, transactions and structured schemas. |
|  3 |   **B**  | RDS is a managed relational database service.                                 |
|  4 |   **B**  | DynamoDB suits key-based, rapidly scaling application data.                   |
|  5 |   **A**  | Redshift is intended for data warehousing and analytics.                      |
|  6 |   **C**  | A database on EC2 gives the customer host operating-system control.           |
|  7 | **A, C** | RDS and Aurora are relational database services.                              |
|  8 |   **B**  | DynamoDB is AWS’s NoSQL service in this module.                               |

The module’s service-selection section distinguishes enterprise relational, fast NoSQL, EC2-hosted and purpose-built database requirements. 

---

## Questions 9–24: Amazon RDS

|  Q |  Answer  | Explanation                                                                 |
| -: | :------: | --------------------------------------------------------------------------- |
|  9 |   **A**  | RDS is a managed relational database service.                               |
| 10 |   **C**  | AWS manages database software installation and patching.                    |
| 11 |   **C**  | Customers remain responsible for application optimisation.                  |
| 12 | **A, C** | AWS manages OS and database-software patching under RDS.                    |
| 13 | **A, B** | MySQL and PostgreSQL are supported RDS engines.                             |
| 14 |   **A**  | Aurora is listed as an RDS database engine.                                 |
| 15 | **A, B** | A DB instance includes an engine and an instance class, along with storage. |
| 16 |   **A**  | The class controls compute, memory and network resources.                   |
| 17 | **A, B** | General Purpose SSD and Provisioned IOPS are module storage options.        |
| 18 |   **A**  | Databases are normally placed in private subnets.                           |
| 19 |   **B**  | Users reach the application, and the application communicates with RDS.     |
| 20 |   **B**  | A private subnet reduces direct internet exposure.                          |
| 21 |   **A**  | RDS supports Microsoft SQL Server.                                          |
| 22 |   **A**  | A database on EC2 requires customer-managed installation and patches.       |
| 23 |   **B**  | RDS reduces infrastructure and database-administration work.                |
| 24 |   **A**  | EC2 gives greater operating-system and software control.                    |

Pages 6–12 contrast managed and unmanaged services, list RDS engines and show an EC2 application in a public subnet communicating with RDS in a private subnet. 

---

## Questions 25–36: Multi-AZ and read replicas

|  Q |  Answer  | Explanation                                                    |
| -: | :------: | -------------------------------------------------------------- |
| 25 |   **B**  | Multi-AZ primarily improves high availability.                 |
| 26 |   **B**  | The module shows synchronous replication.                      |
| 27 |   **B**  | The standby is placed in another Availability Zone.            |
| 28 |   **A**  | AWS can fail over to the standby.                              |
| 29 |   **B**  | Its main purpose is availability, not read scaling.            |
| 30 |   **A**  | Read replicas handle read queries.                             |
| 31 |   **B**  | Read replicas use asynchronous replication.                    |
| 32 |   **A**  | Asynchronous replication can introduce replication lag.        |
| 33 | **A, B** | Multi-AZ supports availability; replicas support read scaling. |
| 34 |   **A**  | Read replicas reduce read load on the primary.                 |
| 35 |   **B**  | Multi-AZ protects against AZ or primary failure.               |
| 36 |   **A**  | A read replica can be promoted if required.                    |



---

## Questions 37–44: RDS selection and pricing

|  Q |  Answer  | Explanation                                                                           |
| -: | :------: | ------------------------------------------------------------------------------------- |
| 37 |   **A**  | RDS suits complex transactions, relational data and SQL.                              |
| 38 |   **B**  | DynamoDB is better suited to massive simple key-based requests.                       |
| 39 |   **A**  | EC2 is appropriate when deep customisation is required.                               |
| 40 | **A, B** | Instance capacity and storage contribute to RDS cost.                                 |
| 41 |   **A**  | On-Demand does not require a long-term commitment.                                    |
| 42 |   **A**  | Reserved DB instances suit predictable long-term use.                                 |
| 43 |   **A**  | Multi-AZ maintains additional database infrastructure.                                |
| 44 |   **A**  | The module states that inbound transfer is free and outbound transfer can be charged. |

The module identifies RDS suitability, running time, database characteristics, purchasing options, storage, I/O, deployment type and transfer as pricing or selection considerations. 

---

## Questions 45–57: DynamoDB

|  Q |  Answer  | Explanation                                                                    |
| -: | :------: | ------------------------------------------------------------------------------ |
| 45 |   **A**  | DynamoDB is a fully managed NoSQL database.                                    |
| 46 | **A, B** | It supports key-value and document models.                                     |
| 47 | **A, B** | DynamoDB tables contain items and attributes.                                  |
| 48 |   **B**  | Items can have different attributes.                                           |
| 49 |   **A**  | The partition key identifies items and affects distribution.                   |
| 50 |   **A**  | A sort key distinguishes several records under one partition key.              |
| 51 |   **A**  | Query uses known key information efficiently.                                  |
| 52 |   **A**  | Scan examines many or all items.                                               |
| 53 |   **A**  | Good key design spreads data and traffic.                                      |
| 54 |   **A**  | Many well-distributed values reduce hot partitions.                            |
| 55 | **A, B** | Gaming state and user sessions are appropriate key-based workloads.            |
| 56 |   **A**  | The module highlights consistent single-digit millisecond latency.             |
| 57 |   **B**  | DynamoDB serves flexible, high-scale key access; RDS supports relational work. |

The module describes DynamoDB as a fast NoSQL service with flexible attributes, scalable throughput and suitability for mobile, web, gaming, advertising and IoT applications.

---

## Questions 58–65: Redshift

|  Q |  Answer  | Explanation                                                 |
| -: | :------: | ----------------------------------------------------------- |
| 58 |   **A**  | Redshift is a managed data warehouse.                       |
| 59 |   **B**  | It is designed for large historical analytical workloads.   |
| 60 |   **A**  | The leader coordinates and combines query processing.       |
| 61 |   **A**  | Compute nodes process distributed portions of the data.     |
| 62 |   **A**  | Redshift uses massively parallel processing.                |
| 63 |   **A**  | Columnar storage avoids reading irrelevant columns.         |
| 64 |   **A**  | Redshift supports SQL and BI clients.                       |
| 65 | **A, B** | Columnar storage and parallel processing are core features. |

The module’s Redshift architecture shows SQL and BI tools connecting to a leader node and multiple compute nodes, while its summary identifies columnar storage and parallel processing.

---

## Questions 66–70: Aurora

|  Q |  Answer  | Explanation                                                                                             |
| -: | :------: | ------------------------------------------------------------------------------------------------------- |
| 66 |   **A**  | Aurora is an AWS-designed enterprise relational database.                                               |
| 67 | **A, B** | Aurora supports MySQL- and PostgreSQL-compatible editions.                                              |
| 68 |   **A**  | Aurora is managed through Amazon RDS.                                                                   |
| 69 | **A, B** | Aurora automates backup, recovery, failure detection and repair.                                        |
| 70 |   **A**  | Aurora MySQL-Compatible fits an existing MySQL relational application requiring enterprise performance. |



</details>

---

# 3. Score interpretation

|        Score | Readiness                                                               |
| -----------: | ----------------------------------------------------------------------- |
|    **63–70** | Strongly prepared                                                       |
|    **55–62** | Nearly ready; revise isolated mistakes                                  |
|    **44–54** | Core understanding exists, but database use cases are still being mixed |
| **Below 44** | Review RDS versus DynamoDB and Multi-AZ versus read replicas            |

For multiple-response questions, mark the answer correct only when every correct option is selected and no incorrect option is added. AWS does not normally award half credit because one answer was correct and the other was selected through optimism.

---

# 4. The most dangerous exam confusions

## RDS versus Aurora

```text
RDS    → Managed relational database service
Aurora → AWS-designed relational engine provided through RDS
```

Aurora is not a competitor completely outside RDS. RDS is the managed service; Aurora is one of its database-engine options.

---

## Multi-AZ versus read replica

```text
Multi-AZ   → Availability and failover
Read replica → Read performance
```

The word **standby** points toward Multi-AZ.

The phrase **read-heavy** points toward read replicas.

---

## Synchronous versus asynchronous replication

```text
Multi-AZ     → Synchronous
Read replica → Asynchronous
```

A read replica may temporarily lag behind the primary.

---

## RDS versus DynamoDB

```text
RDS:
- Relational
- SQL
- Transactions
- Joins and structured relationships

DynamoDB:
- NoSQL
- Key-value and document
- Flexible attributes
- Large-scale simple access
```

Selecting DynamoDB merely because it sounds fast is not enough. A database can be fast and still be completely wrong for a complex accounting system.

---

## RDS versus Redshift

```text
RDS      → Operate the business
Redshift → Analyse the business
```

* Record one sale: RDS or Aurora.
* Analyse five years of sales: Redshift.

Both use SQL, but so do many tools. Sharing a language does not make two services interchangeable.

---

## Query versus Scan

```text
Query → Uses key information
Scan  → Examines many or all items
```

A repeated full-table Scan is generally not a clever substitute for designing the DynamoDB key properly.

---

## DynamoDB partition key versus sort key

```text
Partition key → Determines the item group and distribution
Sort key      → Organises multiple items within that partition key
```

Example:

```text
CustomerID + OrderDate
```

One customer can have several orders, each identified by a different date.

---

## Aurora versus DynamoDB

```text
Aurora   → Enterprise relational database
DynamoDB → High-scale NoSQL database
```

MySQL/PostgreSQL compatibility points strongly toward Aurora.

PlayerID, DeviceID or SessionID lookups point toward DynamoDB.

---

# 5. Rapid revision sheet

```text
AMAZON RDS

- Managed relational database
- Supports MySQL, PostgreSQL, MariaDB,
  Oracle, SQL Server and Aurora
- AWS manages OS and database patching
- Customer manages data and application optimisation
- Usually deployed in a private subnet
```

```text
RDS AVAILABILITY AND SCALING

Multi-AZ:
- Primary and standby
- Synchronous
- Different Availability Zones
- Automatic failover
- High availability

Read replica:
- Asynchronous
- Handles reads
- Reduces primary workload
- Can be promoted
```

```text
AMAZON DYNAMODB

- Fully managed NoSQL
- Key-value and document
- Tables, items and attributes
- Partition key
- Optional sort key
- Flexible attributes
- Low latency
- Horizontal scaling
```

```text
AMAZON REDSHIFT

- Managed data warehouse
- Large-scale analytics
- SQL and BI tools
- Leader node
- Compute nodes
- Columnar storage
- Parallel processing
```

```text
AMAZON AURORA

- Enterprise relational engine
- Managed through Amazon RDS
- MySQL compatible
- PostgreSQL compatible
- Automated backup and recovery
- High availability and performance
```

```text
FAST DECISION

Transactions and relationships? → RDS
Enterprise MySQL/PostgreSQL?    → Aurora
Simple key-based massive scale? → DynamoDB
Historical business analytics?  → Redshift
Full OS and database control?    → EC2
```

Send your answers in the format `1B, 2A, 3B...`; multiple-response answers can be written as `7AC`.

[1]: https://docs.aws.amazon.com/aws-certification/latest/cloud-practitioner-02/cloud-practitioner-02.html?utm_source=chatgpt.com "AWS Certified Cloud Practitioner (CLF-C02)"
[2]: https://docs.aws.amazon.com/pdfs/aws-certification/latest/cloud-practitioner-02/cloud-practitioner-02.pdf?utm_source=chatgpt.com "AWS Certified Cloud Practitioner - Exam Guide (CLF-C02)"

---
</details>
