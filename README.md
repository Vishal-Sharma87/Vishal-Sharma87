# Vishal Sharma — Backend Engineer

> **Currently thinking about:** How do distributed systems behave when failures happen between boundaries — Kafka redelivery, Redis state transitions, database commits, and worker crashes? The interesting part isn't avoiding failure; it's making recovery deterministic.

---

### 🚀 Featured Projects

#### 💳 [Payflo — Event-Driven Payment Processing System](https://github.com/Vishal-Sharma87/payflo)

*Kafka-first payment event processing built to explore distributed-system failure modes — real Kafka, Redis, MySQL, and crash testing; payment execution itself is intentionally mocked.*

* Event-driven payment processing system built around **8 Kafka topics and multiple consumers**, modeling asynchronous payment workflows
* Designed idempotent MySQL writes and deduplicated payment notifications across **3 race-prone termination consumers**, preventing duplicate customer-facing side effects
* Verified **sub-60ms consumer redelivery** after simulated crash recovery, confirming idempotent recovery across MySQL, Redis, and Kafka boundaries
* Used Redis-based coordination to make competing termination consumers safe under concurrent processing and Kafka redelivery
* Wrote **109 JUnit 5 + Mockito unit tests** across three deliberate coverage tiers, catching a real input-validation bug before runtime
* **Real bug found through crash testing:** a duplicate-detection path targeting `EntityExistsException` did not fire because `EntityManager.persist()` can defer constraint violations until flush/commit, where Spring translates them into `DataIntegrityViolationException`. The failure was exposed through genuine crash testing and subsequently fixed.

---

#### 🚦 [Traffic Control Service — Distributed Job Orchestration](https://github.com/Vishal-Sharma87/traffic-control-service)

*Built during my Backend Developer internship at Apana Time Tech Solutions — a fault-tolerant job orchestration engine with Redis-backed priority queues, atomic recovery, worker heartbeat detection, and MySQL-backed failure handling.*

* Built a distributed job orchestration engine decoupling **job scheduling from execution** using Redis ZSET priority queues and atomic Lua scripts
* Sustained **33–37 jobs/sec** under **50–200 concurrent requests** using Redis atomic Lua scripts, with zero job loss during recovery
* Reduced crashed-worker recovery-scan complexity from **O(n) to O(log n)** using Redis ZSET range queries instead of linear scans
* Detected crashed workers within **500ms** through heartbeat-driven Redis ZSET range queries
* Implemented tier-specific retry budgets based on job priority, routing terminal failures to a **MySQL-backed Dead Letter Queue**
* Used atomic Redis operations to coordinate distributed job ownership and recovery across workers

---

#### 🔗 [SmartLink — Verdict-Driven URL Safety Platform](https://github.com/Vishal-Sharma87/SmartLink)

*Kafka-driven URL safety platform with external threat scanning, Redis-backed caching, JWT authentication, analytics, and verdict-aware redirection.*

* Reduced URL-creation latency from **12–18s to under 20ms** by offloading **90+ VirusTotal engine scans** to an asynchronous Kafka pipeline
* Measured **3 ms median / 7 ms P95 cached link-resolution latency across 100 requests**, with asynchronous Kafka analytics publishing completing in **1 ms median**
* Redesigned authentication with **two-stage OTP signup, JWT access tokens, and Redis-Lua-rotated HttpOnly refresh-token cookies**, closing refresh-token replay windows
* Designed abuse reporting to enforce **one report per user per link** through query-based duplicate detection, automatically flagging links after **3 unique reports**
* Built verdict-aware redirection around link safety states, integrating external threat analysis before allowing destinations to be reached
* Published click analytics asynchronously through Kafka so analytics processing does not block the redirect-resolution path
* Reworked the redirect hot path from JSON-serialized cache DTOs to **direct Redis Hash field reads/writes**, removing unnecessary object serialization/deserialization
* Deployed the application to a **self-hosted Azure VM** using Docker Compose behind Nginx, resolving a JDK build failure and an IP-forwarding issue
* **Real caching bug found during refactoring:** Lombok's `@ToString` on the `Verdict` enum produced `"Verdict.SAFE"` instead of `"SAFE"` when persisted to Redis. `Enum.valueOf()` consequently failed to reconstruct the value, with `multiGet()` returning null and the failure surfacing as an NPE downstream. The persistence contract was standardized on `.name()`.

---

### 📂 Other Repositories

| Repo                                                                              | What's inside                                                                                                                                                                 |
| --------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [dsa-solutions-java](https://github.com/Vishal-Sharma87/dsa-solutions-java)       | Java DSA solutions across Arrays, Trees, Graphs, DP, and other problem-solving topics, with problem breakdowns, readable implementations, and reasoning-focused documentation |
| [low-level-design-java](https://github.com/Vishal-Sharma87/low-level-design-java) | OOP, SOLID principles, design patterns across Creational, Structural, and Behavioral categories, plus case studies such as Parking Lot and Elevator System                    |

---

### 🧰 Tech Stack

| Category                   | Skills                                                               |
| -------------------------- | -------------------------------------------------------------------- |
| **Languages**              | Java                                                                 |
| **Frameworks & Libraries** | Spring Boot • Spring Security • Spring Data JPA • Hibernate          |
| **Databases & Caching**    | MySQL • MongoDB • Redis • Redis Lua Scripting • Redis ZSET           |
| **Messaging**              | Apache Kafka                                                         |
| **Cloud / Infrastructure** | Docker • Docker Compose • Azure VM • Azure Key Vault • Linux • Nginx |
| **Testing & Tools**        | JUnit 5 • Mockito • Maven • Git • GitHub Actions • Postman           |
| **Core Concepts**          | DSA • OOP • LLD • DBMS • OS • CN • REST APIs • JWT                   |

---

### 📬 Connect With Me

🔗 LinkedIn: https://linkedin.com/in/vishal-sharma87

📧 Email: [vishal.sharma.dev.87@gmail.com](mailto:vishal.sharma.dev.87@gmail.com)
