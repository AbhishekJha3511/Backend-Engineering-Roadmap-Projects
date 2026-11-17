Backend Engineering Roadmap: 30 Projects
Phase 1: Backend Fundamentals
Start here. These projects teach you how servers, HTTP, networking, and APIs work.
#	Project	What you'll learn
1	URL Shortener	REST APIs, database design, caching
2	Web Server	HTTP, TCP sockets, request-response lifecycle
3	Web Scraper	HTTP clients, HTML parsing, concurrency
4	Rate Limiter	Token bucket, sliding window, Redis
5	Reverse Proxy	HTTP forwarding, routing, middleware
6	API Gateway	Authentication, routing, request transformation
7	Load Balancer	Round-robin, least connections, health checks


What you should understand after this phase:
- How HTTP works internally.
- How TCP connections work.
- How requests travel from clients to servers.
- How reverse proxies operate.
- How backend services communicate.
- How to design and implement REST APIs.
Phase 2: Database Engineering
This is where you start understanding how databases work internally.
#	Project	What you'll learn
8	Redis Clone	In-memory storage, key-value architecture
9	Database Engine	B-trees, indexing, transactions
10	Search Engine	Inverted indexes, tokenization, ranking
11	Logging System	Structured logging, log aggregation
12	Metrics/Monitoring System	Time-series data, instrumentation


Important concepts to master:
- B-Trees and B+ Trees
- Hash tables
- Indexing
- Write-Ahead Logging (WAL)
- ACID properties
- Transactions
- Query execution
- Caching strategies
- Data persistence
A particularly valuable project here is building your own database engine.

Don't just create a database wrapper around SQLite or PostgreSQL. Implement a simplified storage engine yourself.
Phase 3: Distributed Systems
This is one of the most important phases for becoming a strong backend engineer.
#	Project	What you'll learn
13	Distributed Job Queue	Job distribution, retries, workers
14	Kafka Clone	Distributed messaging, partitions, offsets
15	Pub/Sub System	Event-driven architecture
16	Task Scheduler	Scheduling algorithms, distributed execution
17	Decentralized File System	Distributed storage, replication
18	BitTorrent Clone	Peer-to-peer networking
19	CDN	Distributed caching, edge delivery


Concepts to understand:
- CAP theorem
- Eventual consistency
- Replication
- Partitioning and sharding
- Leader election
- Consensus algorithms
- Message delivery guarantees
- Fault tolerance
- Horizontal scaling
- Distributed locking
Pay particular attention to Kafka and distributed job queues.

These concepts are widely applicable to real-world backend infrastructure.
Phase 4: Advanced Networking and Systems
Now explore lower-level systems engineering.
#	Project	What you'll learn
20	DNS Server	DNS protocol, UDP, caching
21	WebSocket Server	Persistent connections, real-time communication
22	DNS Resolver	Recursive resolution, caching
23	Interpreter	Lexing, parsing, AST, execution
24	Email Service	SMTP, queues, delivery
25	File Storage Service	Object storage, multipart uploads


One interesting distinction:

Building an interpreter isn't traditionally a backend project, but it teaches you how programming languages and execution engines work internally.

Similarly, DNS and BitTorrent will improve your networking knowledge significantly.
Phase 5: Production Backend Engineering
These projects bring everything together.
#	Project	What you'll learn
26	OAuth Server	OAuth 2.0, JWT, authorization
27	Payment Gateway Mock	Payment workflows, idempotency
28	Notification System	Async processing, retries
29	Feature Flag System	Configuration management, gradual rollouts
30	CI/CD Pipeline System	Build automation, deployment, orchestration


These projects teach you how production backend infrastructure is designed.
Which Programming Language Should You Use?
My recommendation:
Language	Best for
Go	Backend infrastructure, networking, distributed systems
Java	Enterprise backend, microservices, Kafka ecosystem
Rust	Systems programming, databases, networking
Python	APIs, automation, web scraping, interpreters
C++	Databases, networking, low-level systems


My recommendation: Choose Go as your primary language.

Why?
- Excellent concurrency support through goroutines.
- Strong networking and standard libraries.
- Excellent for building distributed systems.
- Widely used in cloud infrastructure.
- Good ecosystem for backend engineering.
- Relatively simple syntax.
You can eventually explore Rust for lower-level systems projects.
The Order I Would Actually Follow
Rather than treating all 30 projects equally, I'd prioritize them like this:
Priority	Project	Difficulty
1	URL Shortener	Beginner
2	Web Server	Beginner
3	Web Scraper	Beginner
4	Rate Limiter	Beginner–Intermediate
5	Redis Clone	Intermediate
6	Reverse Proxy	Intermediate
7	Load Balancer	Intermediate
8	API Gateway	Intermediate
9	Database Engine	Advanced
10	Distributed Job Queue	Advanced
11	Pub/Sub System	Advanced
12	Kafka Clone	Advanced
13	Search Engine	Advanced
14	DNS Server	Advanced
15	CDN	Advanced


After these, explore the remaining projects based on your interests.

You don't need to complete all 30 before applying for backend developer positions.
How to Build Each Project (Important)
There is a big difference between following a tutorial and actually understanding a system.

For every project, follow this process:

1. Understand the problem

Before coding, understand what problem the technology solves.

For example, before building Redis, understand:
- Why in-memory databases exist.
- Why caching is necessary.
- What key-value storage means.
- Why persistence matters.
2. Read about the internal architecture

Understand how the actual technology works.

For Redis, investigate:
- Data structures
- RESP protocol
- Event loop
- Persistence
- Replication
3. Implement a simplified version

Don't try to recreate the entire production system.

Build the smallest working implementation that demonstrates its core principles.

4. Add production-level features

For example, with your Redis clone:
- TCP server
- GET and SET commands
- Multiple data types
- TTL expiration
- Persistence
- RDB-style snapshots
- Concurrent clients
5. Test and benchmark

Every project should have:
- Unit tests
- Integration tests
- Error handling
- Performance benchmarks
- Documentation
6. Deploy it

Use Docker and deploy your project somewhere accessible.

Include architecture diagrams and examples in your GitHub README.
Recommended Technology Stack
If you choose Go, here's a practical stack:
Category	Technology
Language	Go
Backend Framework	Gin / Chi
Database	PostgreSQL
Caching	Redis
Messaging	Kafka / RabbitMQ
Containerization	Docker
Orchestration	Kubernetes
Reverse Proxy	Nginx
API Testing	Postman
Monitoring	Prometheus + Grafana
CI/CD	GitHub Actions
Cloud	AWS


Learn the underlying concepts before depending on these tools. For example, build a basic HTTP server using Go's standard library before using Gin.
My Final Advice
If your goal is to become a professional backend engineer, focus on these five pillars:
1. Networking: HTTP, TCP, DNS, sockets, WebSockets.
2. Databases: SQL, indexing, transactions, storage engines.
3. Distributed Systems: Kafka, queues, replication, consistency.
4. System Design: Caching, load balancing, scalability, fault tolerance.
5. Production Engineering: Docker, Linux, monitoring, CI/CD, cloud deployment.
The 30 projects you've listed cover almost all five pillars.