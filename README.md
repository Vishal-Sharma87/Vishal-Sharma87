# Vishal Sharma — Backend Engineer

> **Currently thinking about:** How do distributed systems behave when failures happen between boundaries — Kafka redelivery, Redis state transitions, database commits, and worker crashes? The interesting part isn't avoiding failure; it's making recovery deterministic.

---

### 💼 Internship Experience

#### 🚦 [Traffic Control Service](https://github.com/Vishal-Sharma87/traffic-control-service)
**Backend Developer Intern @ Apana Time Tech Solutions** *(Jan. 2026 – July 2026)*

*Built during my Backend Developer internship at Apana Time Tech Solutions — a fault-tolerant job orchestration engine with Redis-backed priority queues, atomic recovery, worker heartbeat detection, and MySQL-backed failure handling.*

- Built a **Redis-backed priority job queue** in Java/Spring Boot using sorted sets (`ZSET`), atomic Lua scripts, and MySQL result and dead-letter tables
- Verified crash and stuck-job recovery with injected faults: **26 jobs dead-lettered within config-derived 14s and 30s bounds**, and stale-worker saves rejected
- Survived `kill -9` mid-run: **100/100 accepted jobs completed after restart**, verified by MySQL ID reconciliation and Redis `ZCARD`; **3 in-flight jobs re-executed** (at-least-once semantics)
- Diagnosed a **silent heartbeat failure and a worker-scheduler write race** from logs, fixing both via corrected Lua argument types (String conversion) and status guards

---

### 🚀 Featured Personal Projects

#### 💳 [Payflo — Event-Driven Payment Processing System](https://github.com/Vishal-Sharma87/payflo)

*An event-driven payment processing pipeline built to test distributed failure modes — focusing on idempotent state transitions, consumer redelivery, and crash recovery across Kafka, Redis, and MySQL (external payment gateway calls are mocked).*

- Built an event-driven payment processing system in **Java 21** with **Apache Kafka** as the messaging backbone, using **8 topics and multiple consumers** to model asynchronous payment workflows
- Verified **sub-60ms consumer redelivery** after simulated crash recovery, confirming idempotent recovery across MySQL, Redis, and Kafka boundaries
- Designed idempotent MySQL writes and deduplicated payment notifications across **3 race-prone termination consumers**, preventing duplicate customer-facing side effects
- Achieved **74.3% branch coverage with 108 focused JUnit 5/Mockito unit tests** across payment details validation, Kafka consumers, Redis script argument contracts, and exception handling
- **Real bug found through crash testing:** fixed a crash-recovery bug where Kafka redelivery triggered duplicate-key exceptions (`EntityManager.persist()` deferring constraint violations until flush/commit, translating into `DataIntegrityViolationException`), leaving transaction state inconsistent and risking delayed recovery or duplicate processing

---

#### 🔗 [SmartLink — Verdict-Driven URL Safety Platform](https://github.com/Vishal-Sharma87/SmartLink)

*A security-focused URL shortener engineered to keep slow third-party threat scans off the critical request path — combining Redis Hash caching, asynchronous Kafka pipelines, and automated abuse flagging*

- Cut URL-creation latency from **12–18s to under 20ms** by offloading **90+-engine VirusTotal scans** to an async Kafka pipeline
- Measured **3 ms median / 7 ms P95 cached link-resolution latency across 100 requests**, with asynchronous Kafka analytics publishing completing in **1 ms median**
- Implemented **two-stage OTP signup, JWT access tokens, and atomic refresh-token rotation** that replaces and revokes previous tokens using `HttpOnly` cookies
- Designed abuse reporting to enforce **one report per user per link** through query-based duplicate detection, automatically flagging links after **3 unique reports**
- Reworked the redirect hot path from JSON-serialized cache DTOs to **direct Redis Hash field reads/writes**, removing unnecessary object serialization/deserialization
- Deployed to a **self-hosted Azure VM** using Docker Compose and Nginx, resolving incorrect client IP analytics by configuring `X-Forwarded-For` forwarding and backend IP extraction
- **Real caching bug found during refactoring:** Lombok's `@ToString` on the `Verdict` enum produced `"Verdict.SAFE"` instead of `"SAFE"` when persisted to Redis. `Enum.valueOf()` consequently failed to reconstruct the value, with `multiGet()` returning null and the failure surfacing as an NPE downstream. The persistence contract was standardized on `.name()`.

---

### 📂 Other Repositories

| Repo | What's inside |
| :--- | :--- |
| [dsa-solutions-java](https://github.com/Vishal-Sharma87/dsa-solutions-java) | **300+ LeetCode problems solved** — Java DSA solutions across Arrays, Trees, Graphs, DP, and other problem-solving topics, with problem breakdowns, readable implementations, and reasoning-focused documentation |
| [low-level-design-java](https://github.com/Vishal-Sharma87/low-level-design-java) | OOP, SOLID principles, all 9 design patterns across Creational, Structural, and Behavioral categories, plus case studies such as Parking Lot |

---

### 🧰 Tech Stack

| Category | Skills |
| :--- | :--- |
| **Languages** | Java • C • C++ |
| **Frameworks & Libraries** | Spring Boot • Spring Security • Spring Data JPA • Hibernate |
| **Databases & Caching** | MySQL • MongoDB • Redis (Lua Scripting, ZSET, Atomic Ops) |
| **Messaging** | Apache Kafka |
| **Cloud / Infrastructure** | Docker • Docker Compose • Azure VM • Azure Key Vault • Linux • Nginx |
| **Testing & Tools** | JUnit 5 • Mockito • Maven • Git • GitHub Actions • Postman |
| **Core Concepts** | DSA (300+ LeetCode) • OOP • LLD • DBMS • OS • Computer Networks • REST APIs • JWT |

---

### 📬 Connect With Me

🔗 LinkedIn: [linkedin.com/in/vishal-sharma87](https://linkedin.com/in/vishal-sharma87)

📧 Email: [vishal.sharma.dev.87@gmail.com](mailto:vishal.sharma.dev.87@gmail.com)
