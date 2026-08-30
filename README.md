# Vishal Sharma — Backend Engineer

> **Currently thinking about:** If a job fails 5 times — first 4 due to heartbeat loss, last one due to timeout — should the DLQ store the final cause, or the full failure history? Does losing those 4 causes matter when logs have already rotated out?

---

### 🚀 Featured Projects

#### 💳 [Payflo — Event-Driven Payment Backbone](https://github.com/Vishal-Sharma87/payflo)

_Kafka-first payment event processing built for deep distributed-systems fluency — real Kafka, real Redis, real crash testing; payment execution itself is mocked._

- Event-driven backbone spans 8 Kafka topics and consumers with keyed-partition ordering, verified live across consumer-group rebalancing and producer/consumer restarts on a self-hosted KRaft cluster
- Redis Lua-based atomic ownership claims (CAS) eliminate race conditions across three competing termination consumers, guaranteeing exactly-once state transition per payment
- ~60ms average message redelivery verified via genuine `kill -9` crash simulation (not graceful shutdown) — measured from partition reassignment to consumer receipt, averaged across repeated trials
- Idempotent MySQL persistence + at-least-once notification delivery survive mid-transaction crashes across MySQL, Redis, and Kafka — partial-write recovery confirmed live, not just reasoned about
- 109 JUnit 5 + Mockito tests across three deliberate coverage tiers — caught and fixed a real `UpiValidator` bug (`split("@")` silently dropping trailing empty strings) before it ever ran against production logic
- **Real bug found via crash testing, not code review:** a duplicate-catch block written for `EntityExistsException` had never actually fired — `EntityManager.persist()` defers constraint violations to flush/commit, where Spring translates them to `DataIntegrityViolationException` instead. Only a genuine `kill -9` crash exposed it. Fixed and re-verified live.

---

---

#### 🚦 [Traffic Control Service — Distributed Async Job Processing](https://github.com/Vishal-Sharma87/traffic-control-service)

_Fault-tolerant job scheduling engine with Redis-backed priority queues, atomic recovery, and crash detection._

- Tier-based priority scheduling — PAID jobs always execute before UNPAID and PUBLIC, enforced atomically via Lua scripts on Redis ZSET
- Crash recovery complexity dropped from O(n) to O(log n) by switching from linear scan to ZSET range queries
- Distributed admission control via Redis atomic counters — enforced consistently across multiple instances
- Heartbeat monitor detects crashed workers within 500ms via atomic score updates on every pulse
- Terminal failures routed to MySQL Dead Letter Queue after exhausting max retries
- **Known gap identified post-build:** DLQ stores only the final failure cause — intermediate causes are permanently lost once logs rotate. Redesigning failure-cause tracking to persist per-attempt history for production diagnostics.

---

---

#### 🔗 [SmartLink — Verdict-Driven Link Security Platform](https://github.com/Vishal-Sharma87/SmartLink)

_Kafka-driven backend with JWT-secured link ownership, external threat scanning, and verdict-aware redirection — rebuilt and rebranded from an earlier URL-shortener MVP._

- Link creation stays sub-20ms — VirusTotal scanning across 90+ engines offloaded entirely to an async Kafka pipeline
- JWT-based stateless authentication with ownership-enforced authorization on every link and account operation — no cross-user access to link data
- Redirection enforces five safety verdicts — `SAFE` passes through instantly, `MALICIOUS` is permanently blocked, three states in between require explicit user confirmation
- Analytics fire during page unload via `keepalive: true` on an intermediate tracking page — redirection never waits, data never drops
- OTP validated and invalidated atomically in a single Redis Lua script — bound to signup and abuse-report flows only, closing the replay window without a database round trip
- Three community abuse reports auto-escalate a link to `PENDING_REVERIFICATION` — no admin intervention required
- Redirect hot-path reworked from a JSON-serialized cache DTO to direct Redis Hash field reads/writes — cut redirect-lookup overhead by removing a full object serialization/deserialization step
- **Real bug found via the caching refactor:** Lombok's `@ToString` on the `Verdict` enum silently produced `"Verdict.SAFE"` instead of `"SAFE"` when written to Redis. `Enum.valueOf()` couldn't reconstruct it on read, and `multiGet()` returned nulls that surfaced as an NPE several layers downstream. Fix: drop `@ToString` on all Redis-reconstructed enums and standardize on `.name()` as the persistence contract — `toString()` was never meant to be one.

---

### 📂 Other Repositories

| Repo                                                                              | What's inside                                                                                                                                                                       |
| --------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [dsa-solutions-java](https://github.com/Vishal-Sharma87/dsa-solutions-java)       | Problems across Arrays, Trees, Graphs, DP, and more — each with detailed problem breakdown, clean readable code, and documentation explaining the _why_ behind every logic decision |
| [low-level-design-java](https://github.com/Vishal-Sharma87/low-level-design-java) | OOP, SOLID, design patterns (Creational, Structural, Behavioral), and case studies — Parking Lot, Elevator System                                                                   |

---

### 🧰 Tech Stack

| Category                | Skills                                                  |
| ----------------------- | ------------------------------------------------------- |
| **Languages**           | Java • C++                                              |
| **Frameworks & Build**  | Spring Boot • Spring Security • JWT • Hibernate • Maven |
| **Databases**           | MySQL • MongoDB                                         |
| **Caching & Messaging** | Redis • Kafka                                           |
| **Tools**               | Docker • Git • Postman                                  |
| **Testing**             | JUnit5 • Mockito                                        |

---

### 📬 Connect With Me

🔗 LinkedIn: https://linkedin.com/in/vishal-sharma87

📧 Email: [vishal.sharma.dev.87@gmail.com](mailto:vishal.sharma.dev.87@gmail.com)
