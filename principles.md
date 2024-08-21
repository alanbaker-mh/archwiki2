---
title: "Architecture Principles"
date: 2023-03-31T16:41:02-05:00
draft: true
---
# Signify Health’s Architecture Principles

We at Signify Health strive to provide products and services that serve our clients and populations well. As technologists, so that we can experiment, learn, and scale our solutions effectively, we adhere to a set of principles that shape our thoughts and habits in system design.

This guidance is for all who design, develop, and implement technical solutions in our organization. It introduces our principles and provides some context to their benefits.

![The Principles](../images/principles.png)

## Products Over Projects

***Products Over Projects*** is a mindset of strategic software development. When we maintain a holistic and forward-thinking view of our organization’s needs and are considerate of our end users’ experience, we treat our systems as products. Though executing quick, tactical projects may sometimes serve our organization, we value the benefits of reusability, extension, and ease of use that a long-term focus on products provides more.

This principle of ***Products Over Projects*** is foundational to all of our other principles.


## Composable APIs

***Composable APIs*** are software assets with well-defined and slowly-changing contracts that are purpose-built for reuse. They are combinable in a modular way to quickly create new capabilities.

***Composable APIs*** come in many forms. They include endpoints accessible by HTTP calls, pre-compiled libraries, and standardized messages in streams (see ***Real-Time Events***).

 Many ideas found in Microservices Architecture also apply to ***Composable APIs***. A microservice application can serve as a ***Composable API***.

>- Maintainable and testable
>- Loosely coupled with other systems
>- Independently deployable
>- Organized around specific business capabilities
>- Owned by a small team


## ***Real-Time Events***

***Real-Time Events*** refers to the practice of continuously streaming facts about the business between systems. These facts are communicated as messages known as “events.” Between systems, events are shared with a firm contract (see Composable APIs) and become the factual record of what has happened. They are the source of truth in our enterprise.

Events reduce the communication friction between business experts and developers because they are directly related to business activities. We can speak one another’s language and also see that language in code. This language-in-code practice also reduces the cognitive load of reasoning about our business and processes.

With the addition of some common IT infrastructure, our streams of ***Real-Time Events*** become persistent and reliable. Systems run independently, producing and consuming events as they are able and in their own time. Because they run independently, systems are protected from computing errors or network failures that might otherwise cascade throughout the enterprise  (see Design for Failure). Applications are also more easily scaled to meet necessary demand (see ***Scale in the Cloud***).


## Scale in the Cloud

***Scale in the Cloud*** is the principle that guides us to design and develop systems specifically for cloud deployment and operation. It affects both the makeup of our systems and our shared infrastructure.

The ***Scale in the Cloud*** principle enables many development and operational efficiencies. It reduces costs while improving reliability. Tooling and deployment, monitoring, and auditing practices are standardized and simplified. The practice of this principle utilizes computing resources more efficiently and significantly improves the ability to scale. Issues surrounding the management of environments are also reduced, especially when the containerization of applications is utilized.

Because of the consistency cloud-based infrastructure provides, security is also improved (see ***Secure by Design***). We are relieved of patching and maintenance of physical machines. Logical infrastructure and configurations are immutable with application containerization.


## Design for Failure

***Design for Failure*** advocates the assumption that systems will inevitably fail. Instead of just trying to prevent these failures, the focus is on ensuring the system can handle them gracefully.

Failures are possible in any system, but complex distributed systems are particularly susceptible. An error or failure can occur due to network or power outages, hardware malfunctions, or human error. By adopting a ***Design for Failure*** mindset, developers can address the inherent challenges of distributed systems more robustly. Developers should consider the [Fallacies of Distributed Computing](https://en.wikipedia.org/wiki/Fallacies_of_distributed_computing) when designing a system.

Applying specific design patterns in applications can reduce the need for human intervention when failures inevitably occur, and systems become self-healing.


>- [Retries](https://learn.microsoft.com/en-us/azure/architecture/patterns/retry)
>- [Circuit Breaker](https://martinfowler.com/bliki/CircuitBreaker.html)
>- [Idempotent Receiver](https://martinfowler.com/articles/patterns-of-distributed-systems/idempotent-receiver.html)


## Secure by Design

***Secure by Design*** emphasizes building security into systems from the start rather than adding it later. We take our responsibility to protect the healthcare information of the people we serve seriously, and this approach makes systems inherently safer, reducing vulnerabilities and design flaws. We keep Secure by Design tenets in mind throughout our design process.


>- Least Privilege: Grant only essential permissions.
>- Defense in Depth: Implement security at multiple layers.
>- Fail Securely: Avoid revealing data during system failures.
>- Minimal Attack Surface: Minimize features and endpoints to limit system exposure.
>- Patching and Updating: Regularly update and fix vulnerabilities.
>- Education and Peer Review: Collaboratively ensure security through team efforts.


# Summary

The tools, patterns, and practices we utilize support these principles. As developers become familiar with the tooling in our enterprise, it is important to remember that the tools we use do not define them.

Signify Health has adopted these principles because of their proven benefits to enterprise software systems. These benefits allow our organization to create secure, effective, maintainable software for our business needs.
