# 7 Microservices Tenets

1. Fine-grained, message-based remote APIs expose independently deployable, scalable and changeable services each having a single responsibility.
2. Business-driven development is applied (for instance, domain-driven design) so that each service represents and models a business capability.
3. Services encapsulate their own state, IDEALly in a loosely coupled fashion (which is a cloud application architecture design principle).
4. Programming and persistence are polyglot, and communication technologies are also chosen in a best-fit “polyglot protocols” manner (for instance, HTTP resources, asynchronous message queues, gRPC).
5. Services are deployed into lightweight containers.
6. Decentralized Continuous Integration and Delivery (CI/CD) is practiced.
7. More DevOps practices are applied, end-to-end service monitoring for business agility and domain observability in particular.
