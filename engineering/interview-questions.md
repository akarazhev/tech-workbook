# Interview Questions

## Q1: How do you manage the complexity when approaching large task?	

- Split into smaller chunks. Divide and Conquer approach.

## Q2: What architecture documents have you created? 	

- Solution design;
- Technical Design, Technical Concept, IT concept;
- Context diagram, Component diagram, sequence diagram, System landscape diagram.

## Q3: What are the most useful Architecture documents in your POV?	

- to get feedback if he has some meaning on this topic, no right answer here).

## Q4: How do you approach requirements analysis? To make sure that implementation does the right thing?	

- Requirements documentation;
- Sign off of requirements and solution with customer;
- Fixing all meeting notes and sigh off them with customer.

## Q5: From which chapters the solution design document should consist?	

- Stakeholders list;
- Functional Requirements;
- Non Functional Requirements;
- Tech stack;
- System contex;
- System components or landscape;
- Solution;
- Important technical solutions for specific requirements (if necessary);
- Decisions log.

## Q6: What are possible ways to integrate two systems? (the more the better)

- File share (ETL - extract transfer load);
- Through the memory on same server (shared memory);
- Messaging Middleware (MQ, JMS, Message BUS, ESB);
- Web Services (SOAP, REST, any other protocol for stateless or stateful web services);
- Shared Database;
- Remote Procedure invocation;
- direct TCP/IP connection, sockets, websockets;
- ...

## Q7: What is REST?	

- representational state transfer;
- more a concept or a philosophy on how to approach web services create web services;
- Main points from it:
    - everything is a 'Resource';
    - every resource has URI which defined it's name;
    - an operations are defined with actions on this resource. Based on HTTP protocol it is methods (GET, POST, PUT, DELETE, PATCH..).

## Q8: How to handle errors related to network in distributed systems? (you do not know if request is delivered if network got down)	

- Retry integration pattern;
- use communications with acknowledgements on app level;
- on DB use transactions;
- use MQ middleware for communication.

## Q9: What is idempotency? How it is related to REST?	

- in maths it is f(f(f(x))) = f(x) => means f is idempotent function;
- in programming means function brings same result in case you call it multiple times. no matter how many times. (it handles duplicates some idempotent way);
- in REST web services best practices - GET, PUT - should idempotent, POST, DELETE, PATCH - can be not idempotent.

## Q10: What integration enterprise patterns do you know?	

- Retry;
- Message Bug;
- Message Router;
- Splitter;
- Endpoint;
- Publish subscribe;
- ...

There are many of the here: https://www.enterpriseintegrationpatterns.com/patterns/messaging/toc.html

Can not just this reference. If he is aware what is that.

## Q11: What frameworks implementing integration patterns have you worked with/know?	

- Apache Camel;
- Spring integration;

## Q12: What is microservice?	

Microservices - also known as the microservice architecture - is an architectural style that structures an application as a collection of services that are

- Highly maintainable and testable;
- Loosely coupled;
- Independently deployable;
- Organized around business capabilities;
- Owned by a small team.

The microservice architecture enables the rapid, frequent and reliable delivery of large, complex applications. It also enables an organization to evolve its technology stack.

## Q13: What is preferred size of the microservice? Should it be really 'micro'	

- Micro does not relate to the size. More to the business value it brings;
- It is not the operation of the service. Not limited number of APIs. But just coupled and isolated business value.

## Q14: What than is a best practice for forming the microservices?	

- The best practice is to start with monolithic app and than split when necessary to more services;
- Services build around domain model. Coupled entities come together in same service;
- The smaller the service and the more of them you have - the more issues you have with:
    - consistency of the data;
    - operations management of the delivery;
    - debugging of the system;
    - full cost of operations and build of the system grows a lot with large number of services;
    - So all factors have to be compared with overhead of monolithic app to decide on splitting.

## Q15: What are main reasons for splitting the services into two instead of having one?	

- System performance requirements in order to scale and provide necessary performance;
- Different teams that are building different parts of the service;
- System complexity management;
- Delivery of the services separately;
- Different delivery cycles of the parts of the service together with complex delivery process (full testing, deployment efforts are high).

## Q16: What kind of estimations were you doing in your experience?	

- Tasks efforts estimation;
- Project efforts estimation;
- Timeline/Duration of tasks estimation;
- Timeline/Duration of project estimation.

## Q17: What estimation approaches have you used or what you know? Plz describe step by step process.	

- T Shirts - S, M, L, XL, XXL;
- 3 points - optimistic, realistic, pessimistic;
- Expert - just putting number;
- With risks - putting numbers for risks separately;
- group estimations - planning poker, collecting numbers from all and than merging and discussing.

## Q18: What is largest estimtation (in MD) have you done?	

like 100 or 1000 or 10000 MDs projects. To understand experience here.

## Q19: What is the risks average rate have you put in your estimations? How you managed risks?	

on tasks if everything super clear risk 10%, if not clear can be 50%.
average - depends on ptoject. Just to understand how deep candidate managed this part.

## Q20: Have you worked with clouds? What cloud providers do you know?	

AWS, Azure, GCP, Heroku, OpenShift.

## Q21: What is the different between IAAS vs PAAS model?	

IAAS - just virtual machines.
PAAS - you get some platform components that are provided by cloud that you just use to run your software or inside your software.
i.e managed Kubernetes, or managed DB or MQ.

## Q22: What is Docker? Kubernetes?	

https://www.docker.com/why-docker
Docker - technology for process virtualization.
Kubernetes - docker orchestration platform. Manages runtime of docker images in clustered environment. auto-scales, manages health, logs, monitoring.

## Q23: Why docker?	

For development - portability and more control of the delivery.
For operations - easy deployment and scalability with Kubernetes or swarm. No pain with third party dependencies, security and updates of the dependencies. More efficient hardware usage (can be times more efficient for hardware usage for enterprise infrastructure).

## Q24: What is CI/CD?	

- https://en.wikipedia.org/wiki/CI/CD

## Q25: Have you used CI/CD on your projects?	

## Q26: What Quality gates did you use? or what Quality gates do you know? (related to CI/CD)	

- Static code analysis locally;
- SonarQube;
- Security analysis;
- Build of the software;
- Unit testing;
- Integration testing;
- E2E testing;
- Manual testing;
- Performance testing;
- Automated Smoke test after deployment;
- ...

## Q27: What is the technological trends do you see happening now and that could be useful for to be integrated?

- Possible points:
    - Containerization, Cloud;
    - CI/CD, automation;
    - QA automation;
    - Microservices architecture.

## Q28: What is the microservices architecture benefits for business?

Possible points:
- Easier and cheaper overcoming “growth” issues for business. Provides easier scalability to hold high load and high availability;
- Possible to build teams with clear responsibilities and ownership for the applications on production (same people write the code and run and support it, if have written shitty code than same guys are having sleepless nights fixing issues);
- Clear teams responsibilities gives ability to quickly integrate changes and quickly rollout new business features. This provides faster business reaction for new opportunities and time to market;
- In case some services are getting outdated – again possible to cut them off to save infrastructure costs and reduce system complexity easier;
- Impact for runtime is smaller in case of new services rollout;
- Easier to create and evaluate Business Continuity Plan.

## Q29: Do you think microservices architecture fit any organization? What would be the criteria to tell if the microservices is a good choice)

- For sure not. For small organization monolithic approach is very good. Best practice is to always start with monolith;
- The criteria would be non functional requirements: size of the business, number of users, expected system load, runtime environment (microservices without cloud is not good for operations), necessity for High availability, impact on business in case of downtime (what is possible downtimes), company organization structure, number of teams...

## Q30: What is the containerization benefits for business?

Possible points:
- Gives ability to cut costs on infrastructure (by evaluating hardware more efficiently);
- High portability in case of changes on infrastructure (i.e. somebody provides cheaper/more reliable cloud and you can think of moving services there);
- Independency on the development and operations (the platform that is running the containers);
- Nice features for implementing Highly Available systems in case of Kubernetes usage.

## Q31: What is the CI/CD approaches benefits for business?

Possible points:
- Gives ability to deliver features to production very fast if necessary;
- Provides higher quality for deliveries. No other option microservices since there are a lot of delivery artifacts;
- Gives ability for fast reaction for users feedback (to deploy new feature and see how users react, if metrics that should have changed are really changing);
- Gives ability to test features (business features) on production.